# Telehealth Platform

> Part of the [worlds-biggest-software-project](https://github.com/worlds-biggest-software-project) initiative.
>
> An AI-native, open-source telehealth platform delivering HIPAA-compliant video consultations, e-prescribing, and a virtual waiting room — with AI woven through triage, documentation, and care coordination.

Telehealth Platform is a virtual care platform for clinics, health systems, and independent providers who need a complete telehealth workflow rather than a thin video layer or a six-figure enterprise contract. It combines browser-based WebRTC video, scheduling, intake, documentation, and e-prescribing into a single deployable system, and uses AI to compress the work around each encounter — pre-visit triage, ambient documentation, no-show prediction, and asynchronous follow-up.

---

## Why Telehealth Platform?

- **The market is bifurcated.** Doxy.me's free tier is video-only with no scheduling, documentation, or billing, while enterprise platforms like Amwell and Teladoc charge USD 500K–5M+ per year — leaving independent and mid-size practices without an affordable, feature-complete option.
- **Twilio Programmable Video sunset in 2024**, forcing a migration of healthcare video apps and creating an opening for a modern, open alternative built on WebRTC and standards-based interoperability.
- **AI capabilities in incumbents are partial and proprietary.** HealthTap leads on consumer triage, Mend on no-show prediction, Daily.co on developer AI toolkits — no platform combines pre-visit triage, ambient documentation, and asynchronous AI care in one workflow.
- **Documentation tail drives provider burnout.** Few telehealth platforms ship native ambient documentation and coding; clinical notes, billing codes, and prescriptions remain manual after the video session ends.
- **Idle provider time is a major economic problem.** Telehealth no-shows directly damage unit economics; only Mend offers AI-driven prediction with proactive waitlist backfill, and it is enterprise-priced.

---

## Key Features

### Virtual Visits and Waiting Room

- HIPAA-compliant browser-based video sessions over WebRTC with DTLS-SRTP encryption and no patient app download
- Virtual waiting room with provider-controlled patient admission
- Visit recording with patient consent and HIPAA-compliant storage
- Mobile access for providers and patients on iOS and Android
- Phone fallback for low-bandwidth and rural users

### Scheduling, Intake, and Patient Engagement

- Online appointment booking with automated SMS and email reminders, confirmations, and cancellation workflow
- Digital pre-visit intake: questionnaires, consent documents, and structured symptom collection
- Secure HIPAA-compliant two-way patient messaging
- Insurance eligibility verification via clearinghouse integration
- Post-visit patient surveys and follow-up scheduling

### Clinical Documentation and E-Prescribing

- Post-visit SOAP note templates with provider editing and e-signature
- E-prescribing of non-controlled substances via NCPDP SCRIPT
- EPCS (Electronic Prescribing for Controlled Substances) capability with DEA-compliant identity verification
- Bi-directional EHR integration for appointment context and visit note transmission via HL7 FHIR R4 and HL7 v2.x ADT
- State-of-patient validation and provider licensure matching for multi-state telehealth compliance

### AI-Mediated Care Workflows

- AI pre-visit triage that gathers symptoms, assesses urgency, and pre-populates the clinical note
- Ambient documentation: real-time transcription of the video session into a SOAP note draft with suggested billing codes
- AI-powered no-show prediction with proactive waitlist backfill
- Asynchronous consultation mode for low-acuity conditions (text and photo submission with provider response within SLA)
- Intelligent routing across urgent care, primary care, behavioral health, and ED referral

### Remote Patient Monitoring and Chronic Care

- Patient-submitted vital readings (blood pressure, glucose, weight) with care-team alert thresholds
- Asynchronous AI follow-up for chronic conditions between synchronous visits: medication adherence check-ins and lab result review
- Escalation logic that promotes asynchronous encounters to synchronous video when clinical complexity warrants

---

## AI-Native Advantage

AI is a first-class layer of the platform rather than a bolt-on. A pre-visit AI agent conducts structured symptom gathering and urgency assessment before the provider joins, so the clinical note arrives partly written and the visit starts focused. During the session, ambient transcription generates a SOAP note draft and suggests billing codes, removing the documentation tail that drives physician burnout. Between visits, AI-mediated asynchronous pathways handle routine chronic-care follow-up — and a no-show prediction model proactively fills slots before they go idle.

---

## Tech Stack & Deployment

- **Video:** WebRTC (W3C/IETF) with DTLS-SRTP encryption; browser-based, no patient download
- **Standards:** HL7 FHIR R4 and HL7 v2.x ADT for EHR interoperability; NCPDP SCRIPT and EPCS for e-prescribing; IHE Virtual Consult Profile alignment
- **Compliance:** HIPAA Security Rule (45 CFR Part 164) — encryption in transit and at rest, access controls, audit logging; BAA with infrastructure providers
- **Deployment modes:** Self-hosted for health systems requiring data residency control; managed cloud for clinics and independent providers; white-label option for health-system-branded virtual care
- **Integrations:** Epic, Oracle Health (Cerner), MEDITECH, and other FHIR-capable EHRs; clearinghouses for eligibility; pharmacy networks via NCPDP SCRIPT

---

## Market Context

The global telehealth market was valued at approximately USD 146–178 billion in 2024–2025 and is projected to reach USD 851–858 billion by 2033–2035 at a CAGR of roughly 17–22% (Markets and Markets; Grand View Research). The US telemedicine market alone is projected to reach USD 160.45 billion by 2034 (Nova One Advisor). Primary buyers include hospital and health system CMOs, employer benefits directors, payer medical directors, mental and behavioral health practice owners, and direct-to-consumer patients — across pricing tiers ranging from USD 35–95 per visit and USD 5–20 PMPM up to enterprise contracts of USD 500K–5M+ per year.

---

## Project Status

> This project is in the **research and specification phase**.  
> Contributions, feedback, and domain expertise are welcome.

---

## Contributing

We welcome contributions from developers, domain experts, and potential users.
See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

**Important:** All contributions must be your own original work or clearly attributed
open-source material with a compatible licence. Copyright infringement and licence
violations will not be tolerated and will result in immediate removal of the offending
contribution. If you are unsure whether a piece of code, text, or other material is
safe to contribute, open an issue and ask before submitting.

---

## Licence

Licence to be determined. See [discussion](#) for context.
