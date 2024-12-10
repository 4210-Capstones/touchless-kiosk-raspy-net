Contributors
Jason Tyler Buras
Miguel A Sanchez
Kumar Pathak



Request Form Submission -> Admin Panel -> Approve/Reject
If Approved -> Move to front-end/images
If Rejected -> Delete
If directory setup is:
Project
├── touchless-kiosk-server/
│   ├── backend/
│   │   ├── All the backend code (API, database, etc)
│   │   ├── uploads
│   │   │   ├── img_requests
│   │   │   │   ├── {email (before@)}_request_{request #}
│   │   │   │   │   ├── Image Files
├── touchless-kiosk-front-end/
│   ├── images/
│   │   ├── slideshow pulls images from here
│   ├── src/
│   │   ├── home-interface
│   │   │   ├──image_slideshow_function.py*
│   │   ├── request-form


It  work with the current file paths in the code.
Included a script and sample images found on Discord for simulating form submissions on our branch (request-form in the touchless-kiosk-server repo) if you want to try it

Steps to Run:
( Used Anaconda to run local)
Navigate to touchless-kiosk-server/

[If you don't have the dependencies]:
pip install "fastapi[standard]"
pip install --upgrade -r requirements.txt


Launch App from project root: uvicorn backend.main:app --reload

Either:
Navigate to touchless-kiosk-front-end/src/request-form and open it with a web browser, submit a form
or
run py simulate_form_submission.py from the root of touchless-kiosk-server/

Then,
Navigate to touchless-kiosk-server/backend/docs/index.html and open it with a browser.
You should see a request in there.

Approve that request then navigate to
touchless-kiosk-front-end/src/home-interface/
install pygame: pip install pygame
and run py image_slideshow_function.py

