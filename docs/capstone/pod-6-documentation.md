# Pod 6 Research View Documentation

---

## Usage

This documentation contains instructions and overview of:
* Touchless-Kiosk-Partner-Dashboard
* Login-Authentication

This documentation will also consolidate the "next steps" and what should be implemented in the future.

---

## Research Labs GUI Features
A dashboard for UNO research labs to display previous and ongoing research as well as demonstrative videos that they may have made in their lab that they want available to every one, on demand without the use of a presenter to have to play the videos for them.

Includes a QR Code window that shows a tkinter view that would be linked to the UI team (pod 7) where an admin could click a button and get a QR code which they could scan with their phone and login via their device

### Prerequisites
1. Conda/Minconda (can be found at https://www.anaconda.com/download/)
2. Python 3.12 or above

### Installation and Setup
#### Step 1: Clone or download the project
1. Navigate to https://github.com/4210-Capstones/touchless-kiosk-front-end/tree/main/src/research-view/Touchless-Kiosk-Partner-Dashboard
2. Download or clone the repository

#### Step 2: Set up Conda Environment (OPTIONAL)
This step is optional but recommended. Allows you isolate dependencies from system Python environment
and allows you to easily switch between Python versions.
1. Head to "[download location]"/touchless-kiosk-front-end/tree/main/src/research-view/Touchless-Kiosk-Partnet-Dashboard
2. Use the following commands to set up your Conda environment.
```
conda create -n partner_dash python=3.12.7
conda init
```
3. Close and reopen terminal that was used to run previous commands then run the following:
```
conda activate partner_dash
```

#### Step 3: Install necessary Dependencies
1. Install the requirements included in the requirements.txt file which should exist in this directory:
```
pip install -r requirements.txt
```
2. Install tkinter using conda:
```
conda install tk
```


#### Step 4: Running program locally
1. Run the program using the following command:
```
python mvp-gui.py
```
This will launch the GUI which you can interact it using your mouse. Current version is a
placeholder "Main Menu" but in the future should only contain the Research Labs portion.

* You can also see the QR Image Window by running:
```
python qr-image-window.py
```

### Next Steps For Research Lab GUI
* Integration with UI team (pod 7) so that the user can click on the homescreen to get to
the research lab dashboard then select a research partnet that they wish to view.
* Integration with leap motion to use hand gestures instead of computer mouse.
* Persistent storage of images, PDFs, and videos. A suggesion may be to coordinate with
the image processing pod so they can provide a way to serve these videos, PDFs, and images
from their server and the database pod would save a string with the path to the location that the files
are stored. This implementation may also include API endpoints to retrieve the data.

---

## Admin Login-Authentication Portal
This is a simple Flask-based web application for user login, signup, and dashboard access. It interacts with a FastAPI backend for user authentication and management.

### Prerequisites
Before running the Flask app, ensure you have the following installed:

1. **Python** (3.8 or higher)
2. **Pip** (Python package installer)
3. **FastAPI Backend**: The FastAPI server must be running at `http://localhost:8000`.

### Installation and Setup
#### Step 1: Clone or download the project
1. Navigate to https://github.com/4210-Capstones/touchless-kiosk-front-end/tree/main/src/research-view/login-authentication
2. Download or clone the repository

#### Step 2: Set up a Virtual Environment (optional)
This step is optional but recommended. Allows you isolate dependencies from system Python environment.
1. Create and activate a virtual environment to isolate dependencies using the following commands:
```
python -m venv venv
source venv/bin/activate # For Linux/Mac
venv\Scripts\activate
```

#### Step 3: Install Dependencies
1. Use the following command to install the required Python packages.
```
pip install flask requests
```

#### Step 4: Set Up FastAPI Backend
1. Navigate to the FastAPI project directory
2. Start the FastAPI backend server using the following command:
```
uvicorn backend.main:app --reload
```
3. Confirm that the FastAPI server is available at http://localhost:8000.

#### Running Flask App locally
1. Navigate to the Flask Project Directory, should be in directory containing app.py
2. Start the Flask Server with the following command:
```
python app.py
```
3. You can now use a web browser to visit the login, signup and dashboard pages.
- Login Page: http://127.0.0.1:5000/login
- Signup Page: http://127.0.0.1:5000/signup
- Dashboard: Redirected here after a successful login.

#### Troubleshooting
Common Errors:
* jinja2.exceptions.TemplateNotFound:
    Ensure the templates folder exists and contains login.html, signup.html, and dashboard.html.
    Verify the templates folder is in the same directory as app.py.

* ConnectionError:
    Ensure the FastAPI backend is running and accessible at http://localhost:8000.

* Session Errors:
    Ensure app.secret_key in app.py is set to a secure random string.

* Debug Mode:
    To enable debug mode, run:

    FLASK_ENV=development python app.py

### Next Steps for Admin Login-Authentication
* QR code screen needs to be integrated with homescreen so that admins can scan and login.
* Implement a way for photos to be submitted and the photo submission pod could send and receive requests
with coordination with the API team so that these requests are made available
* Implementation of a GUI where the requests are shown as a list and provide approval or denial of each
individual request. Would need coordination with pod(s) in charge of backend.
* A way to host the Flask application non-locally and get a static IP so that the authentication
can be done from all kiosks but running on one server. (Currently running off a hardcoded IP)

---

## Contributors

* Nicholas Dobard
* Carlos Murillo
* Norman Cattles