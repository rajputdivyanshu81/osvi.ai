# DISCOVERY QUESTIONS FOR SHREERAKSHA PROJECT TEAM

These questions are designed to align on the technical and operational integrations needed to take the voice agent live.

## 1. Policy Database Integration
- **Question**: What API endpoints or database lookup services are available for the agent to retrieve policy details? 
- **Detail**: When the agent collects a vehicle registration number or mobile number, we need a fast, low-latency API to pull the policy status, owner name, and cover type to verify eligibility before proceeding with full intake.

## 2. Telephony and Queue Routing
- **Question**: How are the transfer actions (`transfer_to_claims_specialist` and `request_human_help`) mapped to your telephony (IVR) queues?
- **Detail**: We need to know if they route to separate human agents (e.g., a critical legal/claims team vs. a standard helpdesk). Additionally, how should the short context summary be passed to the human agent's CRM screen during the transfer (e.g., via SIP headers or API webhook)?

## 3. Factual Intake Data Schema
- **Question**: What are the strict data validations and formats required by your backend Claims CRM?
- **Detail**: We need to ensure the data captured by `record_fnol_field` (like date, time, vehicle registration format, or injury status) matches your CRM database schema exactly to avoid API submission failures.

## 4. SMS Dispatch & Location Capture
- **Question**: How does the `dispatch_network_garage_list` API determine proximity?
- **Detail**: Does it send the list based on the verbal "accident location" captured by the agent, or can we capture the caller's mobile network cell location (LBS) or send a link to request GPS coordinates from their device?

## 5. Callback and Outbound Follow-Up Protocol
- **Question**: What is the operational workflow for incomplete intakes (e.g., call drops, or calls cut short due to safety emergencies)?
- **Detail**: If a caller is rushed to the hospital and the agent registers a partial FNOL, should Osvi queue an automated outbound callback or alert a surveyor to contact them directly once their safety is secured?
