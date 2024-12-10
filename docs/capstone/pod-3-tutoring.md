# Current Pod: <3> – Tutoring Feature

## Usage

The Tutoring Feature allows for managing tutor records on the database and provides a REST API for handling tutoring availability. The Tutoring Feature is capable of adding, retrieving, updating, and deleting tutors. 

Functions:
- **Add a tutor**: Creates a new tutor to the database with details such as, name, email, time in, and time out.
- **Retrieve a tutor**: Gets a list of all tutors on the database.
- **Update a tutor**: Edits the details of an existing tutor.
- **Delete a tutor**: Removes a tutor from the database.

## Installation

1. Clone repository:
`git clone https://github.com/4210-Capstones/touchless-kiosk-server`
2. Create python environment:
`python -m venv venv`
`venv\Scripts\activate`
3. Install dependencies:
`pip install "fastapi[standard]"`
`pip install --upgrade -r requirements.txt`
4. Launch app from project root:
`uvicorn backend.main:app --reload`

## Contributors

* Amanda Nguyen
* Nicole Lonatro
* Trieu Huynh

## Suggestions/comments (optional)

To further build upon existing features, here are future implementation suggestions:

1. **Connect backend functionalities to a working frontend**
    - Collaborate with a UI team to design and implement an intuitive frontend.
    - Ensure seamless integration and improvement of existing API
2. **Develop a uniform scheduling system with other systems**
    - Simplify scheduling across services, like with room booking
    - Can integrate features like conflict detection, recurring session, time-slot filtering?
3. **Create QR Code for easy tutoring signup**
    - Generate QR code linking to a signup page
    - Display QR code on screen or at kiosk 
4. **Live Display Design**
    - Display live tutoring schedule on screens in common areas or outside of tutoring rooms
    - Include real-time queue system next to the live schedule where students can join and check availability.
    - Place QR code probably in the bottom-left corner of the screen. 
5. **Comments**
    - For any future tasks, it's good to consider how it might be utilized by faculty, students, and tutors to ensure wide usability and impact.
