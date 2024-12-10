# Current Pod: <5> – Leap Motion Integration 

## Usage

This document contains the following:
* Installation instructions on how to install the LeapMotion Camera SDK and its Python bindings for use on a personal machine
* Instructions on how to use the bindings with the simple call API made by Maag.
* Instructions on how to use the SWAMP Lab for setup, testing and integration.
* Raspberry Pi environment setup.
* Hardware requirements for the hallway system 

## Installation

### Step 1: Gemini SDK
The Gemini SDK is the SDK we will be using for Ultraleap Camera development, since it is compatable with Linux machines (our RaspPis)
1. Navigate to https://leap2.ultraleap.com/downloads/
2. Select Ultra Leap Controller 2
3. Select OS for your device
4. Install once finished downloading
- DO NOT change default location. This will cause issues with the Python Bindings later.

### Step 2: Pull Python Bindings
The Python bindings are what we are using to interface with the SDK for the camera for Python development.
1. Pull from the repo https://github.com/ultraleap/leapc-python-bindings into a safe place.

### Step 3: Setting Up the Virtual Environment
Setting up the virtual environment allows you to install the required Python packages later.
1. Open the folder in VSCode
2. Open VSCode terminal
3. Run `python -m venv venv`
4. Run `./venv/Scripts/activate`
5. Run `pip install leap`

#### If you have issues with activating the virtual environment, see here:
1. Open powershell as admin
2. Run `Get-ExecutionPolicy`
3. Run `Set-ExecutionPolicy RemoteSigned`
4. In VSCode terminal, run `./venv/Scripts/activate`

### Step 4: Building Python Bindings
1. Open VSCode terminal
2. Run `pip install -r .\leapc-python-bindings\requirements.txt`
3. Run `python -m build .\leapc-python-bindings\leapc-cffi`
4. Run `pip install .\leapc-python-bindings\leapc-cffi/dist/leapc_cffi-0.0.1.tar.gz`
5. Run `pip install -e .\leapc-python-bindings\leapc-python-api`


### Step 5: Running An Example
1. Take an example out of python bindings folder and place it in root
- If you don't have a camera, `print_current_time.py` will still work
2. Plug in Camera if you have one (grab one from the SWAMP lab temporarily)
3. Run example


## How to Use the Custom Simple API
There is a class Listener that handles events of many types. Most of them don't matter, but a reference for all of them if overriding them is wanted is at the [bottom of this section](#events-list). Each Listener class handles some user-defined overridden method for each of the event types, such as:
```python
class MyListener(leap.Listener):
	def on_connection_event(self, event):
		print("Connected")
	
	def on_device_event(self, event):
		try:
			with event.device.open():
				info = event.device.get_info()
		except:
			info = event.device.get_info()
		
		print(f"Found decide {info.serial}")
	
	def on_tracking_event(self, event):
		print("f"Frame {event.tracking_frame_id} with {len(event.hands)} hands.")
```
Each of the functions above are key functions named by the bindings that are overridden here with user-defined behavior that occurs when the corresponding event is captured. 99% of the time, `on_tracking_event` will be the one called. This is for all tracking events.

However, this can get complicated to keep track of, especially considering that the leap SDK has multiple custom ADTs to worry about and use. This, however, can *all be avoided* by using the methods given in `camera_bindings.py`.
### Maag's Simple Bindings
```python
import camera_bindings.py
from camera_bindings.py import MyListener as Listener
import leap

new_listener = Listener()
connection = leap.Connection()
connection.add_listener(new_listener)

with connection.open():
	while True:
		print(new_listener.get_palm_position())
		print(new_listener.is_pinching())		
```
A `Connection` must be instanced, hooked up with a `Listener` object, and `open()`ed. 

Inside of the `while True` loop could be something like a GUI that updates each cycle so that function calls can be made to the listener. 

### Exposed Functions
All of these should be called as a method of the `Listener` class instantiated.
- **`get_palm_position() -> [float, float, float]`**
-- Returns x, y, z of currently tracked palm. 
-- **Important**: Depending on the orientation of the camera, y could be height and z could be depth, or y could be depth and z height. If you are having issues with positioning, swap y and z and see if that fixes it.  

-  **`is_pinching() -> bool`**
-- Returns bool of whether or not the camera detects the user is pinching. This can be used for things like clicking, dragging, etc.
- `get_hand_type() -> ‘left’ || ‘right’`
-- Returns `"left"` or `"right"` depending on currently tracked hand.
- `get_pinching_vectors() -> [float, float, float]`
-- Returns the difference between the index & thumb positions in the x, y, z axes respectively ([0,0,0] if not tracking).
-- This is what is determining if the user is pinching or not (past a certain threshold).
- `get_tracking_frame_id() -> int`
-- Returns current tracking frame ID (goes up by one each tracking event).
- `get_tracking_frame_id_synced() -> int`
-- Returns current tracking frame ID (synced to current tracking event, **recommended**).
- `set_tracking_frame_size(int = 10)`
-- Sets interval of frames between each tracking event (does nothing if < 1).
-- Think of this as the granularity of tracking. A high number makes the camera track less often, choppier movement. A low number makes the tracking finer but more expensive. It's set to 10 by default. 
- `get_tracking_frame_size() -> int`
-- Gets tracking frame size. 
- `test_func()`
-- Prints `tested!!! \n\n\n`.

### Events List
Unless doing something manually within the bindings themselves, you should never have to use these. 
```python
on_none_event(self, event)
on_connection_event(self, event)
on_connection_lost_event(self, event)
on_device_event(self, event)
on_device_failure_event(self, event)
on_policy_event(self, event)
on_tracking_event(self, event)
on_image_request_error_event(self, event)
on_image_complete_event(self, event)
on_log_event(self, event)
on_device_lost_event(self, event)
on_config_response_event(self, event)
on_config_change_event(self, event)
on_device_status_change_event(self, event)
on_dropped_frame_event(self, event)
on_image_event(self, event)
on_point_mapping_change_event(self, event)
on_tracking_mode_event(self, event)
on_log_events(self, event)
on_head_pose_event(self, event)
on_eyes_event(self, event)
on_imu_event(self, event)
```

## SWAMP Lab Usage
## Raspberry PI environment setup
- **Follow steps 1-2 of the installation guide above to install gemini.**
- **A template .bashrc file is included at the end of this section**
1. Start a python virtual environment:
   1. `python3 -m venv venv`
   2. `source /path/to/you/venv/bin/activate`
2. Build Python bindings
   1.  Run `pip install -r /leapc-python-bindings/requirements.txt`
   2.  Run `python -m build /leapc-python-bindings/leapc-cffi`
   3.  Run `pip install /leapc-python-bindings/leapc-cffi/dist/leapc_cffi-0.0.1.tar.gz`
   4.   Run `pip install -e /leapc-python-bindings/leapc-python-api`
3. Create environment variables:
   1. `C_INCLUDE_PATH="/path/to your/LeapSDK/include/file":$C_INCLUDE_PATH`
   2. `LEAPSDK_INSTALL_LOCATION="/path/to your/ultraleap/LeapSDK"`
   3. `LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/path/to your/ultraleap/LeapSDK/lib/file`
   4. `QT_QPA_PLATFORM=xcb`
 
4. Enable systemctl and systemd so the services start automatically upon reboot.
   1. **Start the service** `sudo systemctl start libtrack_server`
   2. **Enable for auto restart** `sudo systemctl enable libtrack_server`

### Helpful Hints
- The leap motion controller only works when the python virtual environment is active. 

- The Raspberry Pi's have 4 usb A ports. If you need to use one of these for the camera stick to the blue 3.0 ports. 

- Pod <#> has a cursor driver in their directory. Also, there are several examples in “shared" in the touchless-kiosk directory. 

- PI USER INFO Username: sweng-lab Password: Touch!e5ski0sk 

- NETWORK SSID: SWENG Password: SWENG-L@b-0 

### Useful CLI Commands for Using the Leap Motion Controller With the SWAMP Lab Raspberry Pi's 
- pods Changes to and displays pod directories 

- ```leapa``` Activates python virtual environment "leap-env" (this can be called from anywhere) 

- `leapd` Deactivates python virtual environment "leap-env" 

- `py` Run python script 

- `pip` Use the python package manager 

- `leap-src` Access leap motion and python bindings source files 

- `volume` Volume adjustment for pulse audio controller 

### Example .bashrc file additions
***Append to end of exsisting .bashrc file.***
```Bash
export C_INCLUDE_PATH="/path/to your/LeapSDK/include/file":$C_INCLUDE_PATH
export LEAPSDK_INSTALL_LOCATION="/path/to your/ultraleap/LeapSDK"
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/path/to your/ultraleap/LeapSDK/lib/file #no quotes 
export QT_QPA_PLATFORM=xcb

alias py='python3'
alias pip='pip3'
alias leap-src='cd ~/ultraleap-hand-tracking-service_5.17.1.0-a9f25232-arm64'
alias leapa='source ~/ultraleap-hand-tracking-service_5.17.1.0-a9f25232-arm64/leap-env/bin/activate'
alias leapd='deactivate'
alias volume='alsamixer'
alias pods='cd ~/Desktop/touchless-kiosk/pods && ls'
```
## Hardware Requirements
### Hardware needed for basic hallway display functionality
- 4x Raspberry Pi's
- 4x PoE (power over ethernet) hats. 
- Either:
  - A PoE managed network switch capable of 30watts (w) per port with a total of 150W aggregate.
  - 4x power injectors capable of 30w output. one per Pi
- Virtual machine for backend server. This is housed in the CS Data Center.
## Contributors

* Mitchell Mennelle
* Dan Trethaway
* Nicholas Maag

## Suggestions/comments (optional)

Use this section to list comments and suggestions.


