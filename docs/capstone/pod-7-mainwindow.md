## LeapGUI.py Documentation

### Description:
This script creates a graphical user interface (GUI) to interact with Leap Motion and display upcoming events from a remote API. It uses Leap Motion hardware for input and supports mouse interactions on macOS.

---

### Prerequisites
1. **Python 3.x** installed on your system.
2. Install required libraries:
   - **Tkinter** (comes pre-installed with Python on most systems).
   - **requests**: For handling HTTP requests.
   - **camera_bindings**: Install or include the module if not available.
   - **leap**: Ensure the Leap Motion SDK is installed.
   - **macmouse**: Specifically for macOS systems (optional).

---

### Installation

1. Install Python libraries:
   ```bash
   pip install requests
   pip install macmouse  # Optional, only if on macOS
   ```

2. Include the `camera_bindings` module in the same directory or install if it is an external package.

3. Ensure that the Leap Motion SDK is properly configured:
   - Download and install from the [Leap Motion Developer Portal](https://developer.leapmotion.com/).

---

### Running the Script
1. Start the API server (if not already running):
   ```bash
   # Adjust the command based on your API implementation
   python api_server.py
   ```

2. Execute the GUI script:
   ```bash
   python LeapGUI.py
   ```

---

### Features
1. **Event Display**: Fetches and displays upcoming events from a RESTful API.
2. **Leap Motion Integration**: Allows control via Leap Motion gestures.
3. **Mouse Interaction (macOS)**: Interacts with macOS mouse events.

---

### Troubleshooting
1. **Leap Motion not detected**:
   - Ensure that the Leap Motion controller is connected and the software is running.
   - Verify that the Leap Motion SDK is correctly installed.

2. **API errors**:
   - Check if the API server is running on the specified `API_BASE_URL`.
   - Verify the network connection.

3. **Missing dependencies**:
   - Install all required Python libraries as mentioned in the **Prerequisites** section.

---

### Notes
- The script assumes the API endpoint for events is at `http://localhost:8000/events/upcoming`.
- Modify the `API_BASE_URL` in the script to match your server configuration.
- The `macmouse` library is optional and required only for macOS systems.

---

### License
Include the appropriate license information here.

---

For further assistance, refer to the official documentation of the Leap Motion SDK or the respective Python libraries.
