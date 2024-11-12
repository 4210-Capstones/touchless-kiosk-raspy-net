# Shared System Requirements Document

## 1. Functional Requirements
- **LEAP Motion Integration:** Gesture-based control system for all users
- **Authentication System:** Handles user authentication and role management
- **Phone Control:** User can connect phone to system to control it or input data

## 2. Non-Functional Requirements
- **Security:** The system's sign-in and authentication should be secure to protect
user data especially if UNO credentials are used to sign in.
- **Performance:** Performance when using gesture-based controls should not differ
from using phone-control.

## 3. Feature List, Prioritization, and Difficulty
### Critical Features (MVP)
- **LEAP Motion Integration:** All users are able to use gestures to control and navigate
the kiosk. (Priority: Critical, Difficulty: Hard)
- **Authentication System:** A backend that securely allows users to sign in and
authenticates the sign in and assigns users a role dependent on sign in which will
determine what they can do and access. (Priority: Critical, Difficulty: Hard)
- **Navigation:** Determine and document how navigation will work in the system
and the layout of the "pages". (Priority: Critical, Difficulty: Medium)

### High Priority Features
- **Phone Control:** Allows all users to use their phone to control the system rather
than the gesture-based control, preferably seamlessly switching back and forth.
(Priority: Critical, Difficulty: Hard)

## Medium Priority Features

## Low Priority Features
- **Time and Date Display:** Always display current time and date on UI, irregardless
of current "page". Preferably always current time and not just updated on page
switch or refresh. (Priority: Low, Difficulty: Easy)
- **Default View:** Decide and set up what is shown when kiosk is not in use/idle.
(Priority: Low, Difficulty: Medium)