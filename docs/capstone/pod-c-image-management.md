# Current Pod: <C> – Image Management

## Usage

This document goes over the following:
* Necessary libraries to install
* Instructions on how to use the slideshow function of Image Management system

## Installation

### Step 1: Getting the function file
1. Navigate to https://github.com/4210-Capstones/touchless-kiosk-front-end/blob/main/src/home-interface/image_slideshow_function.py
2. Download and move the Python file into a project folder for usage

### Step 2: Installing libraries
By default, when using Python, most of these libraries will be already installed but all libraries that are used will have installation instructions just in case:
1. Navigate to the project folder with the 'image_slideshow_function.py' file
2. Open up VSCode and well as its terminal
3. Run 'pip install pygame' to install the pygame library, if not already installed.
4. Run 'pip install sys' to install the sys library, if not already installed.
5. Run 'pip install time' to install the time library, if not already installed.
6. Run 'pip install os' to install the os library, if not already installed.
7. Run 'pip install datetime' to install the datetime library, if not already installed.
8. Run 'pip install json' to install the json library, if not already installed.

### Step 3: Setting up appropriate environment
Our system works by digging through a directory for images
1. Inside the project folder, create a folder named appropriately, our example has it named as 'Flyers'
2. Open up 'image_slideshow_function.py'
3. Navigate to the bottom of the file until you find the code block:

```python
if __name__ == "__main__":
    # Path to the folder containing the flyer images
    # THIS NEEDS TO BE CHANGED TO THE APPROPRIATE DIRECTORY FOR THE KIOSK
    folder_path = r"c:/Users/ace21/OneDrive/Pictures/Flyers"
    
    # THIS NEEDS TO BE CHANGED TO THE APPROPRIATE DIRECTORY FOR THE KIOSK
    metadata_file = r"c:/Users/ace21/OneDrive/Pictures/flyer_metadata.json"

    # Ensure the metadata file exists (create it if necessary)
    initialize_metadata_file(metadata_file)

    # Start the slideshow, displaying each image for 5 seconds and refreshing the flyer list every 30 seconds
    display_slideshow(folder_path, metadata_file, display_time=5, refresh_interval=30)
```
4. Change the directory in 'folder_path' to the one that was just created
5. Adjust the directory in 'metadata_file' to the project folder's directory, leaving flyer_metadata.json
6. As a test, place random images into your images folder

### Step 4: Running the code
1. Run 'py image_slideshow_function.py'
2. Your example images should be displayed in fullscreen, shifting after 5 seconds as per default
3. If you want to change the length the images are displayed, locate the code line:

```python
# Start the slideshow, displaying each image for 5 seconds and refreshing the flyer list every 30 seconds
    display_slideshow(folder_path, metadata_file, display_time=5, refresh_interval=30)
```
4. Change the 'display_time' parameter to however many seconds, you would like
5. To exit the slideshow, hit any key to leave

## Contributors

* Anthony Edenfield
* Eric Gonzalez
* Alex Tran

## Suggestions/comments (optional)

1. There's a particular issue when it comes to displaying the images, where the images will come out pixelated and not legible. Not having looked into it, we theorize there might be a Python library that can fix this issue by eithering enlarging the image and enhancing the quality. However, the quickest solution would be to hold a standard to images that are submitted, making sure they are quality-controlled and large enough to not look distorted.

2. We would probably ask that images that are being submitted are a large enough size that is close to the display size of the TVs to reduce as much 'pixelating' as possible.