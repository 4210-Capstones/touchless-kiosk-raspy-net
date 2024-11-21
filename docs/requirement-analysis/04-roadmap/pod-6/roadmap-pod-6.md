# Roadmap Document: Pod 6

## 1. Overview of Systems
### Shared Systems
- **Authentication System**: Enable secure login and session management
- **Leap Motion Integration**: Provides gestured-based interaction for users
- **Information Request/Feedback System**: Provides the user with an option to provide their email or use the one associated with their account to request more information from a list of parties or report any issues
### User-Specific Systems
- **Research Lab System**: Provides an interface for interested students, faculty, or other research partners to view and access the research and demoes of a UNO Partner

## 2. Systems Breakdown: Milestones & Tasks
### Shared Systems
#### Authentication System
- **Milestone 1**: Basic login functionality 
    - **Sprint 1**: Develop login API (priority: high, complexity: medium)
    - **Sprint 2**: Implement session managment (priority: high, complexity: high)
#### Leap Motion Integration
- **Milestone 1**: Basic gesture integration (priority: high, complexity: medium)
    - **Sprint 1**: Develop gesture recognition to interact with the research lab's dashboard/UI (priority: high, complexity: medium)
#### Information Request/Feedback System
- **Milestone 1**: Develop an information request/bug submittal process
    - **Sprint 1**: Create a database that users can select from for requesting information from specific parties associated with the kiosk (priority: high, complexity: medium)
    - **Sprint 2**: Develop automation process that allows the user to submit their email, or use the one associated with their login, to send a request-for-information form or submit-bug option to be sent to either the associated party or kiosk administrator. The kiosk should automatically send an email to either the UNO Partner or the kiosk administrator that a user, with the provided email address, has either requested more information from the UNO Partner or has submitted a bug with the kiosk system to the administrator (priority: high, complexity: medium)
### User-Specific Systems
#### Research Lab System
- **Milestone 1**: Design Research Lab/Partner Dashboard
    - **Sprint 1**: UI Mockups and Partner Logos/Branding (priority: high, complexity: low)
    - **Sprint 2**: Backend Setup for Dashboard (priority: medium, complexity: medium)
- **Milestone 2**: On-Demand Video Player
    - **Sprint 1**: Create a database of the Research Partner's demonstrative videos (priority: high, complexity: medium)
    - **Sprint 2**: Develop the API for fetching the videos from the database, and sending them over the network to the Raspberry PI, to be played on the televisions (priority: high, complexity: medium)
    - **Sprint 3**: Develop a sorting functionality that allows the user to sort by topic, recency, etc. (priority: low, complexity: low)
- **Milestone 3**: Research Catalog for Past and Present Research
    - **Sprint 1**: Create a database of the Research Partner's catalog for both ongoing and previous research with a built in sorting functionality for release date and topics (priority: medium, complexity: medium)
    - **Sprint 2**: Develop an API for fetching the research papers, presentations, etc. (priority: medium, complexity: medium)
- **Milestone 4**: User Data Input & Simulated Environment Integration
    - **Sprint 1**: Develop an API that can pass data between the user's input and a simulated environment provided by the research lab (priority: low, complexity: high)

## 3. Incremental Cycles
### Cycle 1: Minimum Viable Product (MVP)
- **Authentication System**:
    - Milestone 1, Sprint 1 (priority: high)
    - Milestone 1, Sprint 2 (priority: high)
- **Research Lab System**: 
    - Milestone 1, Sprint 1 (priority: high)
    - Milestone 1, Sprint 2 (priority: medium)
### Cycle 2: High Priority Features
- **Leap Motion Integration**:
    - Milestone 1, Sprint 1 (priority: high)
- **Information Request/Feedback System**: 
    - Milestone 1, Sprint 1 (priority: high)
    - Milestone 1, Sprint 2 (priority: high)
- **Research Lab System**:
    - Milestone 2, Sprint 1 (priority: high)
    - Milestone 2, Sprint 2 (priority: high)
### Cycle 3: Medium and Low Priority Features
- **Research Lab System**:
    - Milestone 3, Sprint 1 (priority: medium)
    - Milestone 3, Sprint 2 (priority: medium)
    - Milestone 2, Sprint 3 (priority: low)
    - Milestone 4, Sprint 1 (priority: low)
