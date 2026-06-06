# Design Rationale: ShreeRaksha Motor FNOL Voice Agent

This document explains the design decisions made for the ShreeRaksha Motor First Notice of Loss (FNOL) voice agent.

## 1. Persona and Language (Hinglish)
We selected a Hindi-first, conversational Hinglish tone. Policyholders calling from an accident site or hospital are under high stress. Forcing them to navigate formal, Sanskritized Hindi (like using "पंजीकरण संख्या" for registration number) increases frustration. Using common English terms (policy, claim, garage, surveyor, cashless) matches standard spoken language in India, ensuring the agent sounds human and empathetic.

## 2. Safety Triage Integration
Following the claims manager's guidelines, safety check is positioned at the start of the call. If a caller is injured or stranded, the agent is instructed to ask "108 / 112 ko call kiya kya?" immediately before gathering any policy or vehicle details. In active emergencies, the agent is configured to skip the standard checklist and transfer the call to the emergency desk.

## 3. Neutral Logging & Legal Liability
To protect the claims process, the agent is trained to record accident descriptions factually and neutrally. If a caller admits fault or blames third parties, the agent filters these subjective statements. The database records are kept strictly factual (e.g. "two vehicles collided") and avoid mentions of alcohol or intoxication, leaving fault assessment entirely to the surveyor and subsequent claims investigations.

## 4. Operational Realism for Garages
The agent does not promise specific network garages or guarantee their availability. Instead, it explains that a curated list is sent via SMS and that the dispatch team confirms the closest open location. This prevents sending policyholders to full or closed repair centers.

## 5. Settlement Timeline Management
When callers ask "paisa kab milega," the agent redirects them to the standard cashless claim workflow without providing specific dates or figures. This manages expectations without legally binding the company to a verbal estimate.

## 6. Strict SLA Adherence
The agent is explicitly instructed not to promise specific timeframes like "by next morning" for surveyor assignment or garage arrangements. All expectations are strictly managed according to the 24-working-hours SLA constraint to prevent policyholder dissatisfaction and avoid violating internal service level agreements.

## 7. Concise Communication
To prevent unnecessary repetition and improve the caller's experience, the system prompt directs the agent to be concise. Long explanations are trimmed, and the agent avoids over-explaining the next steps, keeping the focus on efficiency and empathetic handling.

## 8. Escalation Matrix
The system uses a two-tier handoff system:
- High-priority claims specialist transfer: Triggered for third-party injuries, active emergency support, or hostile interactions.
- General human assistance transfer: Triggered for general assistance queries the automated flow cannot handle.
This optimizes human resource allocation by directing legal and safety escalations to claims managers while resolving standard claims automatically.
