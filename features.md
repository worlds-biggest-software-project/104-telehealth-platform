# Telehealth Platform — Feature & Functionality Survey

> Candidate #104 · Researched: 2026-05-01

## Solutions Analysed

| Tool | Type | Licence / Model | URL |
|------|------|-----------------|-----|
| Teladoc Health | Direct-to-consumer + enterprise telehealth (full clinical service) | Proprietary SaaS | https://www.teladochealth.com |
| Amwell (American Well) | Enterprise telehealth platform (health systems + payers) | Proprietary SaaS | https://business.amwell.com |
| Doxy.me | Browser-based HIPAA video visit platform (solo / small practice) | Proprietary SaaS (free tier) | https://doxy.me |
| MDLive (Evernorth / Cigna) | Telehealth service (urgent care, behavioral health, dermatology) | Proprietary SaaS | https://www.mdlive.com |
| Zoom for Healthcare | HIPAA-compliant video conferencing (not a full telehealth platform) | Proprietary SaaS | https://zoom.us/healthcare |
| Daily.co | WebRTC video infrastructure SDK (developer-first) | Proprietary SaaS (Apache-2.0 client SDK) | https://www.daily.co |
| Twilio Video (deprecated) | Video SDK for telehealth app development | Proprietary SaaS (sunset 2024) | https://www.twilio.com/healthcare |
| Mend | Enterprise patient engagement + telehealth (AI no-show prediction) | Proprietary SaaS | https://mend.com |
| Spruce Health | HIPAA-compliant patient communication + basic telehealth | Proprietary SaaS | https://sprucehealth.com |
| HealthTap | AI-powered triage + virtual primary care | Proprietary SaaS | https://www.healthtap.com |

## Feature Analysis by Solution

### Teladoc Health

**Core features**
- Virtual care across multiple specialties: general medicine, mental health (BetterHelp), dermatology, chronic care, nutrition, and preventive health
- Video, phone, and landline consultation options (broadens access for low-bandwidth/rural users)
- Remote patient monitoring (RPM): unified device data aggregation and alert management for care teams
- MyStrength Complete mental health program: digital mental health tools and therapist-matching
- Chronic care management: diabetes (Livongo heritage), hypertension, and weight management programs
- Population-scale program management: PMPM employer and payer contracts
- Catapult Health integration (acquired February 2025): preventive health screening and biometrics

**Differentiating features**
- Largest US telehealth provider by revenue: 50+ million members across 130+ countries
- Population-scale RPM unified within a single care-team dashboard (unique depth at scale)
- Excels in document management, mobile capabilities, and tele-consultation scheduling per independent surveys
- Mental health program breadth (BetterHelp acquisition) with therapy-matching for consumers
- Strong for employer and payer PMPM arrangements with outcomes reporting

**UX patterns**
- Consumer app: symptom description → specialty routing → provider match → synchronous visit
- Care manager dashboard for population health monitoring with device-integrated alerts
- PMPM program enrollment and engagement tracking for employer benefit administrators

**Integration points**
- EHR integration via HL7 FHIR R4 and HL7 v2.x ADT for visit note transmission
- Health plan benefit eligibility API for real-time member coverage validation
- RPM device APIs: glucose meters, blood pressure cuffs, weight scales via Livongo platform
- Employer benefits platforms (Benefitfocus, Darwin, Businessolver)

**Known gaps**
- Consumer-facing model creates tension with health systems that want white-label or provider-branded telehealth
- EHR integration less tight than Amwell for health system workflows
- Behavioral health provider supply constraints create wait times despite large network
- Financial performance challenged: Teladoc reported significant goodwill impairments ($6.6B write-down in 2022) reflecting over-payment for Livongo; ongoing restructuring

**Licence / IP notes**
- Proprietary SaaS; Teladoc Health Inc. (NYSE: TDOC)
- HIPAA BAA provided; SOC 2 certified
- No open-source components

---

### Amwell (American Well)

**Core features**
- Enterprise telehealth platform deployable as health-system-branded virtual care
- Seamless EHR integration: chart launch, context sharing, documentation, orders, and billing handoffs (Cerner / Oracle Health partnership March 2025; Epic integration available)
- Specialty coverage: urgent care, primary care, behavioral health, specialty consult
- Automated Symptom Checker before visit routing
- Digital front door: unified patient-facing entry point for scheduling, triage, and virtual visits
- Hybrid care support: virtual visits can transition to in-person appointments within the health system

**Differentiating features**
- Health system and payer focus: Amwell is a technology vendor enabling health systems to deliver branded telehealth — not competing directly with them for patients
- Deep EHR integration (84.3% of typical requirements supported out-of-the-box including integrations, mobile, and scheduling)
- White-label deployment: health system branding throughout the patient experience
- Converge platform (launched 2021): unified care platform merging virtual and in-person workflows

**UX patterns**
- Provider-facing: virtual care appears as a native appointment type within the EHR workflow
- Patient-facing: health system's branded app or portal for virtual visit access
- Scheduling: integrated with health system's existing appointment booking infrastructure

**Integration points**
- Epic, Oracle Health (Cerner), and MEDITECH EHR integrations
- HL7 FHIR R4 for patient data exchange
- SSO integration with health system identity providers
- Insurance eligibility verification via clearinghouse

**Known gaps**
- Limited direct-to-consumer presence; depends on health system partners to acquire patients
- Enterprise pricing ($500K–$5M+/year) excludes small practices
- Platform complexity requires significant health system IT involvement for deployment
- Amwell has faced financial pressures (stock price decline since 2020 IPO) raising questions about long-term investment capacity

**Licence / IP notes**
- Proprietary SaaS; American Well Corporation (Nasdaq: AMWL)
- HIPAA BAA provided; SOC 2 and ISO 27001 certified
- No open-source components

---

### Doxy.me

**Core features**
- Browser-based HIPAA-compliant video visit platform: no download required for patient or provider
- Free tier: unlimited video sessions, virtual waiting room, one-to-one video, and meeting history
- Pro tier ($35–$50/provider/month): group video, custom branding, advanced waiting room, and analytics
- Clinic tier: multi-provider management, staff roles, and reporting
- Patient check-in: patients join via a waiting room link without creating an account
- HIPAA BAA provided for all tiers including free

**Differentiating features**
- Only major telehealth platform in this comparison with a fully functional, unlimited free tier
- Zero patient friction: no app download, no account creation — patient clicks a link, enters their name, and waits
- Ideal for solo practitioners, community clinics, and home-bound patient populations
- Transparent pricing model: fixed per-provider monthly fee vs. per-visit or percentage-of-collections models

**UX patterns**
- Provider: sends a single waiting room link (or waiting room page URL) to all patients; manages the queue from a provider dashboard
- Patient: click link → enter name → virtual waiting room → provider admits to video session
- No scheduling or EHR features in the core product; purely the video visit layer

**Integration points**
- API and webhooks for integration with EHR, scheduling, and patient communication tools
- Not deeply embedded in any EHR natively; integrates via URL-passing or iframe embedding
- Integration partners for scheduling and intake (OpenTable health, AdvancedMD)

**Known gaps**
- Not a full telehealth platform: no scheduling, clinical documentation, billing, or e-prescribing
- No AI features (ambient documentation, triage, no-show prediction)
- Group session limits and advanced features require paid tier
- No native EHR chart integration; note-writing is manual

**Licence / IP notes**
- Proprietary SaaS; Doxy.me Inc.
- HIPAA BAA provided (including free tier — notable differentiator)
- No open-source components; infrastructure is proprietary

---

### MDLive (Evernorth / Cigna)

**Core features**
- Telehealth services: urgent care, behavioral health (therapy and psychiatry), and dermatology
- Per-visit or insurance-based access (Cigna members access at reduced or no cost)
- Board-certified provider network: 24/7 urgent care, same-day behavioral health appointments
- Prescription capability: non-controlled substances via telehealth visit
- Visit summary and follow-up care coordination

**Differentiating features**
- Owned by Evernorth (Cigna's health services division) — deep payer integration enabling no-cost access for Cigna members
- Focus on virtual behavioral health supply: psychiatry and therapy appointment access is faster than competitors in many markets
- Dermatology asynchronous (store-and-forward) consultation available

**UX patterns**
- Consumer app: select specialty → symptom description → provider match → video or phone visit
- Employer/health plan enrollment: accessed via benefits portal

**Integration points**
- Cigna/Evernorth plan eligibility natively integrated
- External payer integrations via benefits administration platforms
- Limited public API for third-party integration

**Known gaps**
- Limited to Evernorth/Cigna distribution; smaller reach outside Cigna-covered populations
- No white-label or health-system deployment model
- No AI triage beyond symptom routing; basic intake compared to HealthTap
- Documentation and clinical data not routinely shared with PCP; care coordination gaps

**Licence / IP notes**
- Proprietary SaaS; Evernorth Health Services (Cigna subsidiary)
- HIPAA BAA provided
- No open-source components

---

### Zoom for Healthcare

**Core features**
- HIPAA-compliant video conferencing with signed BAA for healthcare customers
- Zoom Rooms: dedicated video room hardware for telehealth suite configuration
- Breakout rooms for multi-participant care team consultations
- Waiting room controls with provider-managed patient admission
- Recording: session recording with patient consent (HIPAA-compliant storage option)
- Integration with EHR scheduling via API for appointment link generation

**Differentiating features**
- Familiar Zoom UX for patients who already use Zoom: zero learning curve
- Provider and patient support across all devices (desktop, mobile, browser)
- Large meeting capacity: useful for group therapy, patient education classes, and care conferences
- Zoom AI Companion for Healthcare: meeting summaries, follow-up action items (clinical use requires BAA verification)

**UX patterns**
- Standard Zoom meeting UX with healthcare-specific waiting room and consent features
- Not a telehealth platform: no scheduling, clinical notes, billing, or clinical decision support
- EHR integration generates Zoom meeting links at appointment creation; provider and patient click the link at visit time

**Integration points**
- EHR scheduling integrations (Epic, Oracle, Athenahealth) via Zoom Developer API
- Zoom Marketplace: 1,500+ app integrations including clinical and administrative tools
- Zoom AI Companion API for meeting summaries and transcript processing

**Known gaps**
- Not a telehealth platform: scheduling, clinical documentation, billing, and e-prescribing all require separate systems
- Zoom's general consumer reputation creates confusion about HIPAA eligibility (only Zoom for Healthcare with signed BAA qualifies)
- At ~$200/provider/month, more expensive than Doxy.me for a tool that provides only video conferencing
- No native clinical decision support, ambient documentation, or triage features

**Licence / IP notes**
- Proprietary SaaS; Zoom Video Communications Inc. (Nasdaq: ZM)
- Zoom for Healthcare BAA is separate from standard Zoom agreement; must be explicitly executed
- No open-source client SDK

---

### Daily.co

**Core features**
- WebRTC video and audio infrastructure API for building custom telehealth applications
- HIPAA-eligible deployment plans with BAA available
- SDKs: Web (JS), iOS, Android, React Native, Python, Linux, macOS, Flutter, Windows (beta)
- AI toolkit: speech-to-text, LLM integration, automated clinical note generation, RAG video search
- Prebuilt UI components (daily-react, CallObject API) for rapid front-end development
- SFU (Selective Forwarding Unit) cloud infrastructure for scalable group calls
- Recording: cloud recording with HIPAA-compliant storage
- Network adaptivity: dynamic quality adjustment for low-bandwidth environments

**Differentiating features**
- Developer-first video infrastructure: embed custom telehealth video in any application
- AI toolkits natively integrated for voice, video, and vision — enabling ambient documentation, voice LLM agents, and video analysis within the video call
- After Twilio Programmable Video sunset (2024), Daily.co is the leading migration destination for healthcare video apps
- Python and Linux SDKs for server-side AI agents in the video session — unique in this comparison
- SOC 2 Type II and HIPAA-eligible; strongest developer security posture in video infrastructure category

**UX patterns**
- No end-user UI out of the box; developer builds the patient and provider interfaces
- Prebuilt UI components (callbox, participant tiles, controls) accelerate custom development
- CallObject API for programmatic session management: mute, admit from waiting room, record, transcribe

**Integration points**
- REST API for session management and room creation
- Webhook events for session lifecycle (join, leave, recording ready, error)
- AI pipeline integration: Daily transcription → LLM for note generation → EHR via FHIR API
- Any EHR, PMS, or scheduling system via API

**Known gaps**
- No end-user product: customers must build the full patient and provider UI and workflow
- No scheduling, EHR, billing, or clinical documentation native to the platform
- Developer expertise required; not suitable for organizations without engineering capacity
- Pricing based on video minutes used — costs can grow unpredictably at scale without usage optimization

**Licence / IP notes**
- **Daily.co server infrastructure**: Proprietary SaaS; Daily.co Inc.
- **daily-js client SDK**: The open-source portions of the Daily client library are published under **Apache-2.0** on GitHub — permissive, no copyleft, embeddable in proprietary products.
- HIPAA BAA available on HIPAA-eligible plans (requires paid tier; free tier not HIPAA eligible)
- Note: The video server infrastructure and AI processing remain proprietary SaaS regardless of the client SDK licence

---

### Twilio Video (Deprecated)

**Core features**
- WebRTC-based video SDK for building custom telehealth applications (historical)
- HIPAA-eligible BAA available during active period
- Twilio's health communication tools (messaging, voice) continue but Programmable Video is sunset

**Differentiating features**
- Twilio's healthcare communication suite (SMS, voice, messaging) continues and remains relevant for patient engagement, appointment reminders, and asynchronous messaging
- Twilio Flex can be used for healthcare contact center use cases

**UX patterns**
- SDK-based: developers built UIs on top of Twilio Video APIs

**Integration points**
- Twilio Super Network for SMS/voice patient communications
- API-first integration with any healthcare application

**Known gaps**
- **Programmable Video is sunset (2024)**: existing Twilio Video integrations required migration. Daily.co is the recommended migration path per Twilio's own documentation.
- New telehealth builds should not use Twilio Video

**Licence / IP notes**
- Proprietary SaaS; Twilio Inc. (NYSE: TWLO)
- Video SDK is now deprecated; no ongoing investment

---

### Mend

**Core features**
- AI-powered no-show prediction: analyzes patient behavior signals and historical data to predict cancellation likelihood per appointment
- Virtual visits: HIPAA-compliant video, audio, and chat sessions
- Patient engagement: automated appointment reminders, intake forms, and consent collection
- Digital patient intake: pre-visit questionnaires and consent documents via patient portal
- Multi-specialty support: 100+ specialties, 5+ million patients, 400,000+ telehealth visits per month
- Insurance eligibility verification and financial counseling integration
- Two-way patient messaging (SMS and in-app)

**Differentiating features**
- AI no-show prediction is the primary differentiator: reduces idle provider time (a major telehealth economic problem)
- Enterprise-grade patient engagement combined with telehealth — more complete than Doxy.me for practices with scheduling workflows
- Fill logic: when a no-show is predicted, system proactively messages waitlisted patients to fill the slot
- Clinical questionnaire library for structured pre-visit symptom collection

**UX patterns**
- Appointment lifecycle: book → automated reminders → pre-visit intake forms → video visit → post-visit survey
- No-show risk score displayed per appointment on provider/admin calendar
- Waitlist management with automated outreach when high no-show risk is detected

**Integration points**
- EHR integration: HL7 HL7 v2.x and FHIR for appointment and patient data synchronization
- PMS integration for scheduling and charge capture
- Clearinghouse for insurance eligibility
- NCPDP SCRIPT for e-prescribing (via integration)

**Known gaps**
- No clinical documentation (notes, SOAP) native to the platform; clinical workflow requires EHR
- AI no-show prediction requires sufficient historical data per practice to reach meaningful accuracy
- Pricing is custom and enterprise-oriented; small practices may find it expensive relative to Doxy.me
- E-prescribing not native; requires EHR integration

**Licence / IP notes**
- Proprietary SaaS; Mend (Mend VIP Inc.)
- HIPAA BAA provided; SOC 2 certified
- No open-source components

---

### Spruce Health

**Core features**
- HIPAA-compliant patient communication: secure two-way messaging, voice calls, video visits, e-fax
- Shared team inbox for care team collaboration: routing, assignment, templates
- Workflow automation: auto-responses, clinical questionnaire triggers, after-hours routing
- Digital payments: invoice and copay collection via messaging thread
- Basic telehealth: HIPAA-compliant video visits via the Spruce platform

**Differentiating features**
- Communication-first platform: consolidates patient messaging, voice, video, fax, and internal team communication in one unified inbox
- Designed for outpatient clinic and specialty practice communication workflows (not a full telehealth replacement)
- Workflow automation for high-volume patient messaging: routing rules, templates, auto-replies
- Strong for practices that need secure HIPAA messaging as a primary use case with video as a secondary feature

**UX patterns**
- Unified inbox: all patient-facing and internal messages in a single view
- Shared team inbox with routing: messages assigned to specific staff members or care teams
- Patient-facing: patients communicate via SMS link; no app download required

**Integration points**
- HL7 FHIR and EHR integration for patient demographics and appointment context
- E-fax integration for inbound and outbound fax workflows
- Slack-like internal team messaging with patient record context

**Known gaps**
- Telehealth video is a feature, not the primary use case; no scheduling, billing, or clinical documentation
- No AI ambient documentation or clinical decision support
- No no-show prediction or proactive patient engagement AI
- Not suitable as a standalone telehealth platform for high-volume virtual care

**Licence / IP notes**
- Proprietary SaaS; Spruce Health Inc.
- HIPAA BAA provided
- No open-source components

---

### HealthTap

**Core features**
- AI-powered pre-visit triage: structured symptom assessment by AI agent before connecting to physician
- Virtual primary care: on-demand and scheduled video visits with US-licensed physicians
- AI symptom checker: assesses urgency and routes patient to appropriate care level (urgent care, primary care, ED referral)
- Prescription capability via telehealth visit
- EHR-lite patient record: maintains ongoing patient health history for continuity
- Consumer subscription model (~$15/month) for unlimited access

**Differentiating features**
- Most AI-forward consumer telehealth platform in this comparison: AI handles pre-visit triage and assessment before physician involvement
- Consumer subscription pricing ($15/month) offers the lowest per-visit cost for frequent users
- Reduces appointment time by pre-populating clinical note from AI-gathered symptom data
- Asynchronous consultation option for low-acuity conditions (text-based, no video required)

**UX patterns**
- Consumer app: AI triage first → urgency determination → provider match → video or async consultation
- Pre-visit note pre-populated from AI symptom assessment: provider reviews AI-gathered data rather than repeating intake
- Subscription portal showing past visits, prescriptions, and ongoing care plans

**Integration points**
- Consumer app; limited EHR or health system integration
- Prescription transmission via NCPDP SCRIPT to pharmacy

**Known gaps**
- Consumer-only model; no white-label or health-system deployment
- Limited specialty depth compared to Teladoc; primarily primary care and urgent care
- No RPM or chronic care management programs
- Clinical continuity limited; not a replacement for a primary care practice with longitudinal records

**Licence / IP notes**
- Proprietary SaaS; HealthTap Inc.
- HIPAA BAA provided
- No open-source components

---

## Cross-Cutting Feature Themes

### Table-Stakes Features
- HIPAA-compliant video sessions with BAA: encrypted transport (DTLS-SRTP), access controls, audit logging
- Browser-based patient access: no app download required (WebRTC standard; all major platforms)
- Virtual waiting room with provider-controlled patient admission
- Appointment reminders (SMS, email) with confirmation and cancellation workflow
- Secure patient-provider messaging (HIPAA compliant)
- Visit recording with patient consent and compliant storage
- EHR integration for visit note transmission and appointment context (at minimum via HL7 or FHIR)
- Mobile access: iOS and Android for provider and patient

### Differentiating Features
- AI-powered pre-visit triage and symptom assessment reducing provider intake burden (HealthTap — leading; Mend structured questionnaires)
- AI no-show prediction with proactive waitlist backfill (Mend — unique)
- AI ambient documentation: real-time transcript → SOAP note draft post-visit (Daily.co AI toolkit enables this; Teladoc building toward)
- RPM integration with unified care-team alert dashboard at population scale (Teladoc Livongo — unique depth)
- Developer-first video infrastructure with AI toolkits for custom telehealth app building (Daily.co — unique)
- White-label health-system branded telehealth deployment with EHR-native workflow (Amwell — unique positioning)
- Asynchronous (store-and-forward) telehealth for low-acuity conditions avoiding synchronous video (HealthTap, MDLive dermatology)
- Unified patient communication hub (messaging, voice, fax, video) for clinical team coordination (Spruce Health — unique)

### Underserved Areas / Opportunities
- Seamless hybrid care: AI-mediated triage that fluidly moves patients between async AI assessment, synchronous video, and in-person referral in a single encounter workflow — no platform does this end-to-end well
- AI chronic disease care pathways at scale: AI handles routine asynchronous follow-up for diabetes, hypertension, and mental health between synchronous visits — reducing cost per episode dramatically
- Post-visit AI automation: clinical note generation + billing code suggestion + prescription transmission + follow-up scheduling triggered automatically after the video session ends
- Affordable enterprise-grade telehealth for independent practices (gap between Doxy.me's feature-poor free tier and enterprise platforms' $500K+ contracts)
- AI-powered real-time clinical decision support surfaced to the provider during the video consultation without disrupting the patient encounter

### AI-Augmentation Candidates
- Pre-visit AI triage: structured symptom gathering and urgency assessment before provider involvement, pre-populating the clinical note
- Real-time clinical decision support during the video session: surface relevant guidelines, drug interactions, and differential diagnoses to the provider unobtrusively
- Ambient documentation: real-time transcription of the video consultation → SOAP note draft → billing code suggestion → auto-routed for provider signature
- No-show prediction and waitlist backfill: ML model per patient type and appointment context, proactive slot-filling
- Asynchronous AI care: AI handles follow-up for chronic conditions between synchronous visits (lab result review, medication adherence, symptom check-in)
- Intelligent routing: AI assesses symptom urgency and routes to correct care level (urgent care, primary care, behavioral health, ED referral) without clinician triage step

## Legal & IP Summary

- **No GPL or AGPL tools** in this comparison present embedding concerns. All evaluated platforms are either proprietary SaaS or use permissive open-source components.
- **Daily.co client SDK (Apache-2.0)**: Permissive licence; the daily-js open-source portions can be embedded in a proprietary telehealth application without any open-source obligation. The Daily server infrastructure remains proprietary SaaS.
- **Twilio Programmable Video**: Sunset in 2024. Do not build new telehealth video on Twilio Video. Twilio's messaging and voice services remain active and relevant for patient communication.
- **WebRTC standard (W3C/IETF)**: Open standard; implementing WebRTC in any application is unrestricted. The standard itself carries no IP obligations.
- **HIPAA BAA requirement**: Any US-market telehealth platform that handles PHI in video transmissions must execute a Business Associate Agreement with the video infrastructure provider. Doxy.me (including free tier), Daily.co (HIPAA-eligible plans), Zoom for Healthcare, and Amwell all provide BAAs. Standard Zoom does not qualify.
- **DEA EPCS (Electronic Prescribing of Controlled Substances)**: Remote prescribing of Schedule II–V controlled substances via telehealth became legal nationally during COVID; the DEA finalized rules in 2024 requiring identity verification and at least one in-person encounter for ongoing controlled substance prescriptions. Any telehealth platform enabling controlled substance prescribing must comply.
- **State telehealth licensure parity laws**: Providers must be licensed in the patient's state. A US telehealth platform must enforce state-of-patient validation and provider licensure matching — a significant compliance engineering requirement.

## Recommended Feature Scope

**Must-have (MVP)**:
- HIPAA-compliant browser-based video session (WebRTC, no patient download required) with virtual waiting room and provider admission control
- Appointment scheduling with automated SMS and email reminders, online booking, and cancellation workflow
- Secure HIPAA-compliant patient messaging and pre-visit digital intake forms
- EHR integration: bi-directional FHIR R4 for appointment context and visit note transmission
- Visit documentation: post-visit SOAP note template with provider editing and e-signature
- E-prescribing (non-controlled substances via NCPDP SCRIPT; EPCS capability planned)

**Should-have (v1.1)**:
- AI ambient documentation: real-time transcription of video session → SOAP note draft → billing code suggestions → routed to provider for signature
- AI no-show prediction per patient with proactive waitlist backfill notification
- AI pre-visit triage: structured symptom gathering before the video session, pre-populating the clinical note
- Asynchronous consultation mode: patient submits symptoms / photos; provider responds within defined SLA without synchronous video
- RPM-lite: patient-submitted vital readings (blood pressure, glucose, weight) reviewed asynchronously by care team with alert thresholds

**Nice-to-have (backlog)**:
- Real-time AI clinical decision support during the video session: relevant guidelines, drug interaction alerts, differential diagnosis suggestions surfaced to provider
- AI-mediated chronic care management between synchronous visits: automated follow-up, medication adherence check-ins, and lab result review with escalation logic
- White-label deployment option: health system branding with EHR-native scheduling integration
- Multi-language video interpretation integration for LEP (Limited English Proficient) patient populations
- Group therapy and care conference support: multi-participant video with breakout rooms and provider-moderated participant management
