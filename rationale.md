# DESIGN RATIONALE — SHREERAKSHA MOTOR FNOL HELPLINE

## 1. Persona and Language Choice (Hinglish-First)
- **Decision**: Hindi-first, conversational Hinglish tone.
- **Why**: Policyholders calling after an accident are highly stressed. Using formal, Sanskritized Hindi (e.g., "पंजीकरण संख्या" for registration number) increases cognitive load. Hinglish terms like *policy*, *claim*, *garage*, and *surveyor* are universally understood in India and make the agent sound like a helpful, natural human.

## 2. Safety-First Triage Priority
- **Decision**: Immediate check for injuries/danger (*"108 / 112 ko call kiya?"*) before asking for a policy number or vehicle number.
- **Why**: Reconciles the Claims Manager's bulletin (Artifact 2). Distressed callers require immediate empathy and safety validation. A rigid data-collection checklist during a medical emergency is poor customer service and a safety risk. 

## 3. Factual Logging and Legal Compliance
- **Decision**: Neutral description capture using verbatim transcriptions of the accident, with strict filters against recording fault allocation, intoxication, or counter-blame.
- **Why**: Reconciles the Compliance Memo (Artifact 3). Recorded statements about fault or intoxication can prejudice subsequent insurance investigations, surveyor findings, or Motor Accident Claims Tribunal (MACT) proceedings. The agent registers the notice of loss neutrally and leaves fault determination to the surveyor.

## 4. Operational Realism in Next Steps
- **Decision**: Triggering a network garage list by SMS without promising a specific garage location or availability.
- **Why**: Reconciles the Surveyor Desk note (Artifact 4). Real-time garage occupancy and proximity cannot be determined reliably by a static prompt. Letting dispatch confirm availability via SMS ensures we do not send a caller to a closed or full garage.

## 5. Settlement Query Handling
- **Decision**: Politely redirecting payment timeline/amount questions ("kab paisa milega") to the standard cashless workflow, without providing concrete numbers or dates.
- **Why**: Prevents the company from being legally bound to verbal promises, while easing the caller's anxiety by highlighting the cashless convenience.

## 6. Escalation Triggers
- **Decision**: Clear triggers for `[ACTION: transfer_to_claims_specialist]` (third-party injuries/fatalities, active emergency, suspected fraud, hostile caller) vs. `[ACTION: request_human_help]` (general human request).
- **Why**: Optimizes human agent utilization by reserving specialists for high-priority legal, medical, or complex situations, while automated flows handle standard intakes.
