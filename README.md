# OpenAI GDPR Evidence

Technical documentation of GDPR violations discovered through Data Subject Access Request (DSAR) forensic analysis.

**Case Reference:** #06328903  
**Status:** Filed March 4, 2026 | OpenAI Support responded  
**Complainant:** UK data subject  

## What This Is

Evidence from OpenAI's own DSAR response proving undisclosed multi-company processing of personal data, including Article 9 special category health data.

## Evidence Source

All evidence derived from:
- `conversations.json` (OpenAI's DSAR export)
- HTTP Archive (HAR) files from ChatGPT sessions
- JWT token cryptographic analysis
- OpenAI public statements

## Key Findings

### Irrefutable Evidence (Tier 1)

**1. Anthropic Classifier Integration**
- Model: `snc-pg-sw-3cls-ev3`
- Found in: conversations.json (OpenAI's own data)
- Never disclosed in privacy policy
- Processes every message before GPT-4 response

**2. Architectural Concealment**
- Flag: `"is_visually_hidden_from_conversation": true`
- Found in: conversations.json metadata
- Proves intentional hiding of processing from users

**3. Persistent Tracking**
- Identifier: `conduit_uuid: 0e32b14107204627b3fddaf0c6031ce8`
- Duration: 19.17 hours across 1,140 JWT tokens
- Server-side logs exist (mathematically provable) but not provided in DSAR

**4. Paid Feature Sabotage**
- Flag: `"remove_memory": true`
- ChatGPT Plus memory disabled before external classification
- Paid feature stripped for third-party processing

**5. OpenAI Public Admission**
- Blog post: "limited historical April–September 2025 user data" retained
- My memoir: July 2025
- Never notified of extended retention

### Strong Evidence (Tier 2)

**6. Statsig Behavioral Profiling**
- 196 transmissions to ab.chatgpt.com in 19 minutes
- Data: email, IP, payment status
- Third-party not specifically disclosed

**7. Device Fingerprinting**
- Device ID: `5f24f186-f145-43e2-8feb-bbb498499f28`
- Persistent across sessions
- Zero cookies (cookieless tracking)

**8. Telemetry Extent**
- 321 requests to Datadog
- 440 unique data points collected
- Includes keystroke timing, mouse movements

## GDPR Articles Violated

- **Article 9(1)** - Processing of health data (30,000-word mental health memoir) without legal basis
- **Article 13(1)(e)** - Recipients not disclosed (Anthropic, Microsoft, Statsig)
- **Article 15** - Incomplete DSAR (92% of processing architecture omitted)
- **Article 22** - Automated decision-making without meaningful information
- **Article 26** - Joint controllers not identified (Anthropic determines routing)

## What I'm Not Claiming

- No fine amount predictions
- No "strongest case" claims
- No speculation about outcomes
- No legal conclusions

## What The Evidence Shows

OpenAI maintains multi-company processing architecture involving Anthropic, Microsoft, Statsig, and possibly Scale AI. None specifically disclosed. Processing includes Article 9 special category health data. Architectural flags prove intentional concealment.

## Files

- `/evidence/` - Evidence breakdown by tier
- `/technical/` - JWT analysis, HAR files documentation
- `/legal/` - GDPR article references

## Verification

All evidence reproducible. Any ChatGPT user can:
1. Request DSAR under Article 15
2. Search conversations.json for `snc-pg-sw-3cls-ev3`
3. Verify Anthropic classifier exists
4. Confirm `is_visually_hidden_from_conversation` flag

## Contact

Email: fchaudhry86@googlemail.com  
Case: #06328903

---

This is technical documentation, not legal advice. I am not a lawyer.
