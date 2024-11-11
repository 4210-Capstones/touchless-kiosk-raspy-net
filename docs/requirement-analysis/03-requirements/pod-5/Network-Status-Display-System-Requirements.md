
# Network Status Display System Requirements Document

## 1. Functional Requirements
- **Integration with LibreNMS:** System must fetch and display various network graphs and status updates from LibreNMS.
- **Selection Menu:** A dropdown menu that allows users to select specific apps, services, or network segments to view their status.
- **Real-time Updates:** Display updates in real-time or near-real-time to reflect the current status of the network.

## 2. Non-Functional Requirements
- **Accessibility:** The interface must be accessible and easy to use for all users, with clear labeling and intuitive navigation.
- **Performance:** System must handle concurrent data fetching and display without delays, ensuring a smooth user experience.
- **Security:** Must securely access network data without exposing sensitive information or access credentials.

## 3. Feature List; Priority; Difficulty
### Critical Features (MVP):
- **Network Graph Display:** Capability to display network status graphs directly fetched from LibreNMS. (Priority: Critical, Difficulty: Medium)
- **Service Selection Interface:** A dropdown menu integrated into the display interface for selecting specific network services or segments. (Priority: Critical, Difficulty: Low)

### High Priority Features:
- **Interactive Graphs:** Users can interact with the graphs to view more detailed information or historical data. (Priority: High, Difficulty: Medium)

### Medium Priority Features:
- **Customizable Views:** Allow users to customize which data points are shown by default when they access the display. (Priority: Medium, Difficulty: Medium)
- **Alert Notifications:** Display alerts or warnings when network anomalies or downtime is detected. (Priority: Medium, Difficulty: Medium)
