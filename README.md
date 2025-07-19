# CST8917 Lab 3: Implementing a Teams Chat Content Moderation Service

## Overview
This project implements a Microsoft Teams chat content moderation service using Azure Logic Apps. The service monitors Teams chat messages for inappropriate content and automatically triggers email notifications when a policy violation is detected. This implementation uses only Logic Apps, without Azure Functions or Cognitive Services.

---


## Moderation Workflow Flowchart    
<img width="636" height="701" alt="Logic App Flowchart" src="https://github.com/user-attachments/assets/b7fc6240-46b2-464e-9715-9852f69b87ac" />

---

## How the Moderation Workflow Works

1. **Trigger: New Teams Message**
   - The Logic App is triggered automatically whenever a new message is added to a specific Microsoft Teams group chat or channel.

2. **For Each Message**
   - The workflow iterates over each new message received in the trigger event.

3. **Get Message Details**
   - For every message, the Logic App retrieves detailed information, including the message content, sender, and timestamp.

4. **Check for Policy Violations**
   - The workflow checks if the message content contains any prohibited words (e.g., “bro” or “assignment”).
   - This is done using a condition that searches for these keywords in the message content.

5. **Send Email Notification (If Violation Detected)**
   - If a violation is found, the Logic App sends a high-importance email to the administrator (e.g., khadkan1023@gmail.com).
   - The email includes:
     - The offending message content
     - The sender’s display name
     - The time the message was sent

6. **No Action (If No Violation)**
   - If no violation is detected, the workflow does nothing and ends for that message.
---

## Testing the Workflow
- Simulated Teams messages with and without violations
- Verified that email notifications are sent only for violations

---

## Challenges and Resolutions
- **Challenge:** Configuring Teams trigger permissions
  - **Resolution:** Ensured Logic App has required permissions in Teams

---

## Recommendations for Future Improvement
- Add logging and monitoring for workflow actions
- Expand content moderation to include images or files
- Integrate with additional notification channels (e.g., SMS)

---
