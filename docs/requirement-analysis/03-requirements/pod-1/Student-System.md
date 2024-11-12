# [AI] Requirements Document
## 1. Functional Requirements
- **AI assitant:** Intergate AI functionality
- **Training data:** Should be able to get UNO-based query q&a's.
- **Hardware:** We need to choose a local-trained model ie:ChatRTX or 
    using a cloud-based/ pre-existing model. 

## 2. Non-Functional Requirements
- **Hardware aquistion:** If local-training, hardwar must be allocated
    for training, if with ChatRTX, an RTX GPu will be required. 
- **query injection prevention:** Prevent the malicous use of     
    existing data (should not exist in data set anyway).
- **API intigration:** If possible enable the use of API's to collect
    the most relevant, up-to-date information for potential queries.
- **Reliability and uptime:** How acurate the information is, and how much
    down time for trainin is necessary.

## 3. Feature List, Prioritization, and Difficulty
### Critical Features (MVP)
- **AI assistant**: Assistant for increased chances of kiosk utility
    (Priority: Critical, Difficulty: High)
- **Training data:** Provides the relevant information. (Priority: Critical, Difficulty: Hard)
    
### High Priority Features
-  **Hardware:**: The decision needs to be made to train locally or use an existing model. (Priority: High, Difficulty: Hard)
- **Reliability and uptime:** Find a way to schedule the training, if the 
local computer is used by others, it must be down during use-time to not 
impact device performance. (Priority: High, Difficulty: Medium)

### Medium Priority Features
- **query injection prevention:** Nice-to-have functionality. (Priority: Medium, Difficulty: Medium)

### Low Priority Features
- **API intigration:** Intigration may help with other tasks. ei:maps, menues, and school info.  (Priority: Low, Difficulty: Hard)