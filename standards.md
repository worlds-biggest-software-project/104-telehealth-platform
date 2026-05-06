# Standards & API Reference

> Project: Telehealth Platform · Generated: 2026-05-06

## Industry Standards & Specifications

### ISO Standards

**ISO/TS 6268-1:2025 — Health Informatics: Cybersecurity Framework for Telehealth Environments — Part 1: Overview and Concepts**
- URL: https://www.iso.org/standard/82154.html
- Published February 2025. Provides foundational concepts, definitions, actors, activities, environments, and security variables for telehealth cybersecurity. Part 1 of a new three-part series specifically targeting telehealth — the most directly applicable ISO standard for a telehealth platform architecture.

**ISO/TS 6268-2:2025 — Health Informatics: Cybersecurity Framework for Telehealth Environments — Part 2: Cybersecurity Reference Model of Telehealth**
- URL: https://www.iso.org/standard/85110.html
- Published May 2025. Describes the threat landscape, security-risk/safety-risk relationships, and methodologies for defining security levels specific to telehealth service delivery. Use when designing the security architecture and risk classification for a telehealth platform.

**ISO/DTS 6268-3 — Health Informatics: Cybersecurity Framework for Telehealth Environments — Part 3: Cybersecurity Controls of Telehealth**
- URL: https://www.iso.org/standard/85111.html
- Draft standard (under development as of 2026). Will specify the cybersecurity control requirements uniquely applicable to telehealth systems; general healthcare security controls should be drawn from ISO 27799. Monitor for publication.

**ISO 27799:2025 — Health Informatics: Information Security Controls in Health Based on ISO/IEC 27002**
- URL: https://www.iso.org/standard/84647.html
- Provides healthcare-specific guidance for implementing ISO/IEC 27002 information security controls across all healthcare IT systems, including EHR systems, telehealth platforms, and medical devices with embedded software. Applicable to all data-handling components of a telehealth platform.

### W3C & IETF Standards

**W3C WebRTC 1.0: Real-Time Communication in Browsers**
- URL: https://www.w3.org/TR/webrtc/
- W3C Recommendation (January 2021). Defines the RTCPeerConnection API, data channel API, and media capture browser APIs that enable browser-based peer-to-peer audio and video communication. The foundational web API for browser-based telehealth video sessions — implemented natively in all major browsers.

**RFC 8825 — Overview: Real-Time Protocols for Browser-Based Applications**
- URL: https://datatracker.ietf.org/doc/html/rfc8825
- IETF standard providing a high-level overview of the real-time protocol suite used in WebRTC, contextualising how the 50+ individual WebRTC RFCs fit together. Essential reading for telehealth platform architects designing the video call layer.

**RFC 9429 — JavaScript Session Establishment Protocol (JSEP)** *(obsoletes RFC 8829)*
- URL: https://datatracker.ietf.org/doc/rfc9429/
- Published April 2024. Defines the signalling state machine and SDP offer/answer mechanisms used by RTCPeerConnection. Governs how WebRTC sessions are negotiated between browsers — directly relevant when building custom telehealth video clients without relying on a managed WebRTC SDK.

**RFC 7742 — WebRTC Video Processing and Codec Requirements**
- URL: https://datatracker.ietf.org/doc/html/rfc7742
- Specifies mandatory video codecs (VP8, H.264) and processing requirements for WebRTC implementations. Relevant when selecting video codecs for interoperability across patient devices (mobile, desktop, legacy browsers) in a telehealth context.

**RFC 5764 — DTLS Extension to Establish Keys for SRTP (DTLS-SRTP)**
- URL: https://datatracker.ietf.org/doc/html/rfc5764
- Defines the key exchange mechanism that MUST be used to encrypt all WebRTC media streams. DTLS-SRTP is mandatory in all WebRTC implementations per the security architecture (RFC 8827) and is the technical basis for HIPAA-compliant encrypted video transport. All telehealth video platforms using WebRTC rely on this RFC.

**RFC 8827 — WebRTC Security Architecture**
- URL: https://datatracker.ietf.org/doc/html/rfc8827
- Specifies the security architecture for WebRTC, mandating DTLS-SRTP for media and requiring browser-enforced identity model. Directly informs the security design of any telehealth video component built on WebRTC.

### Data Model & API Specifications

**HL7 FHIR R4 (v4.0.1)**
- URL: https://www.hl7.org/fhir/R4/
- The current required interoperability standard for US healthcare data exchange, mandated by CMS and ONC for certified health IT. Key FHIR resources for telehealth include: `Appointment`, `Encounter`, `Patient`, `Practitioner`, `HealthcareService` (which supports virtual/telehealth service descriptions), `Communication`, `DiagnosticReport`, and `MedicationRequest`. Bi-directional FHIR R4 integration with EHR systems is table-stakes for health-system-facing telehealth platforms.

**SMART on FHIR App Launch (v2.2.0)**
- URL: https://build.fhir.org/ig/HL7/smart-app-launch/
- HL7 implementation guide specifying how OAuth 2.0 and OpenID Connect are layered on FHIR to enable context-aware application launch from within an EHR. Required for telehealth applications that launch within Epic, Oracle Health, or other EHR patient/provider portals. Defines the scopes and launch context (e.g., current patient ID, encounter ID) passed to the telehealth app at launch time.

**NCPDP SCRIPT Standard (v2023011)**
- URL: https://www.ncpdp.org/Resources/ePrescribing-Industry-Information
- ANSI-approved January 2023. The mandatory standard for transmitting new prescription requests, refills, cancellations, and medication history between prescribers and pharmacies. Required for any telehealth platform offering e-prescribing. Regulated by CMS under 42 CFR § 423.160 for Medicare Part D. Two formats: XML (v10.6+) and legacy EDIFACT (v4.x).

**OpenAPI Specification 3.1**
- URL: https://spec.openapis.org/oas/v3.1.0
- De-facto standard for documenting and versioning RESTful APIs. Relevant for designing and publishing the telehealth platform's own REST API (for EHR integrations, scheduling systems, and third-party telehealth app developers). All major EHR vendors publish OpenAPI-compliant FHIR endpoint descriptions.

### Security & Authentication Standards

**HIPAA Security Rule (45 CFR Part 164, Subpart C)**
- URL: https://www.ecfr.gov/current/title-45/subtitle-A/subchapter-C/part-164/subpart-C
- Federal regulation mandating administrative, physical, and technical safeguards for electronic protected health information (ePHI). Technical safeguards (§ 164.312) require access controls, audit controls, integrity controls, and transmission security (encryption). All telehealth video sessions, messaging, and clinical data must comply. A signed Business Associate Agreement (BAA) is required from every sub-processor handling ePHI (video infrastructure, storage, AI transcription, etc.).

**HIPAA Security Rule NPRM (January 2025) — Proposed Strengthening**
- URL: https://www.federalregister.gov/documents/2025/01/06/2024-30983/hipaa-security-rule-to-strengthen-the-cybersecurity-of-electronic-protected-health-information
- HHS proposed rulemaking published January 2025 proposing to eliminate the "required vs. addressable" distinction and make all security specifications mandatory. Final rule expected May 2026. Telehealth platform teams should design to the proposed requirements now, as the final rule will tighten obligations around encryption, MFA, vulnerability scanning, and incident response.

**OAuth 2.0 (RFC 6749) and OpenID Connect 1.0**
- URL: https://datatracker.ietf.org/doc/html/rfc6749 | https://openid.net/connect/
- OAuth 2.0 is the authorization framework underlying SMART on FHIR and all major EHR API access. OpenID Connect adds identity verification on top of OAuth 2.0, enabling secure patient and provider authentication in telehealth apps. Required for SSO integration with health system identity providers (Epic, Oracle Health, Azure AD, Okta in healthcare).

**DEA Electronic Prescribing for Controlled Substances (EPCS) — Special Registration Rules (January 2025)**
- URL: https://www.federalregister.gov/documents/2025/01/17/2025-01099/special-registrations-for-telemedicine-and-limited-state-telemedicine-registrations
- DEA rules finalized January 2025 create a special registration framework allowing DEA-registered practitioners to prescribe Schedule III–V controlled substances via telehealth, with mandatory EPCS (electronic transmission), patient photo ID verification, and nationwide PDMP check requirements. Telehealth platforms enabling controlled substance prescribing must implement EPCS-compliant workflows and integrate with state PDMP systems.

**DEA Telemedicine Flexibilities Extension (through December 2025)**
- URL: https://www.dea.gov/documents/2024/2024-11/2024-11-15/dea-and-hhs-extend-telemedicine-flexibilities-through-2025
- DEA and HHS extended COVID-era telemedicine prescribing flexibilities (permitting Schedule II–V prescriptions via telehealth without a prior in-person visit) through December 31, 2025. Monitor for the 2026 regulatory position on Schedule II substances, which remains unsettled.

### MCP Server Specifications

MCP (Model Context Protocol) is relevant for AI-augmented telehealth where an AI agent needs real-time access to clinical context (patient records, appointment data, clinical guidelines) during a telehealth session.

**Model Context Protocol (MCP)**
- URL: https://modelcontextprotocol.io/
- Anthropic's open protocol for connecting AI assistants to external data sources and tools. For a telehealth platform, MCP servers could expose: FHIR patient records (for pre-visit AI triage), clinical guidelines (for real-time decision support during video calls), and appointment/scheduling context (for AI no-show prediction). Relevant when building the AI-native features described in the product roadmap.

---

## Similar Products — Developer Documentation & APIs

### Daily.co

- **Description:** WebRTC-based real-time video and audio infrastructure API for building custom telehealth applications. HIPAA-eligible with BAA. Includes AI toolkit for transcription, clinical note generation, and LLM integration within video sessions.
- **API Documentation:** https://docs.daily.co/
- **Reference Docs:** https://docs.daily.co/reference
- **SDKs/Libraries:** daily-js (Web), @daily-co/daily-react (React), iOS SDK, Android SDK, React Native SDK, Python SDK (server-side AI agents), Linux SDK
- **GitHub:** https://github.com/daily-co
- **Developer Guide (Telehealth):** https://www.daily.co/use-cases/telehealth/
- **AI Clinical Notes API:** https://www.daily.co/blog/introducing-ai-powered-clinical-notes-api-for-telehealth/
- **Standards:** WebRTC (W3C/IETF), REST/JSON API, DTLS-SRTP media encryption, SFU architecture
- **Authentication:** API key for room/session management; DTLS certificate for media; HIPAA-eligible plans with BAA
- **Notes:** After Twilio Programmable Video sunset (2024), Daily.co is the leading WebRTC infrastructure option for new telehealth builds. Python and Linux SDKs are unique for server-side AI agent integration within live video sessions. Apache-2.0 client SDK portions are permissively licensed.

---

### Epic on FHIR

- **Description:** Epic's FHIR API platform providing 800+ APIs for patient and provider data exchange, scheduling, clinical documentation, and telehealth launch workflows. The primary EHR integration target for US health-system-facing telehealth platforms (Epic is installed at ~65% of US hospital beds).
- **API Documentation:** https://fhir.epic.com/Documentation
- **Developer Portal:** https://open.epic.com/
- **Developer Playbooks:** https://fhir.epic.com/ (40+ use-case-specific integration guides)
- **Standards:** HL7 FHIR R4, SMART on FHIR v2 (OAuth 2.0 + OpenID Connect + PKCE), RESTful JSON/XML
- **Authentication:** SMART on FHIR OAuth 2.0 with PKCE; backend service JWT authentication for server-to-server; API key for sandbox access
- **Telehealth Relevance:** Epic supports telehealth app launch via SMART on FHIR context (current patient, encounter, provider), scheduling integration via FHIR `Appointment` resources, and write-back of visit notes via `DocumentReference`. Epic MyChart provides the patient-facing portal where telehealth visit links are surfaced.

---

### Oracle Health (Cerner) Millennium Platform APIs

- **Description:** Oracle Health's FHIR R4 API platform for Cerner Millennium EHR. The second-largest EHR in the US (installed at major academic medical centres and VA system). Amwell's March 2025 partnership prioritises Oracle Health integration.
- **API Documentation:** https://docs.oracle.com/en/industries/health/millennium-platform-apis/mfrap/r4_overview.html
- **Developer Portal:** https://www.oracle.com/health/developer/
- **SDKs/Libraries:** REST/JSON FHIR R4 APIs; SMART on FHIR app framework; no dedicated language SDKs — clients use standard HTTP libraries
- **Standards:** HL7 FHIR R4 (DSTU 2 deprecated as of December 2025), SMART on FHIR v1 and v2, OAuth 2.0
- **Authentication:** OAuth 2.0; SMART on FHIR scopes (SMART v1 and v2 supported); sandbox access via Oracle Health Developer Program registration
- **Telehealth Relevance:** FHIR R4 Appointment and Encounter resources for scheduling integration; DocumentReference write-back for visit notes; HealthcareService resource for virtual care service configuration.

---

### Twilio (Healthcare Communications)

- **Description:** Cloud communications platform providing HIPAA-eligible APIs for SMS, voice, and messaging for patient engagement workflows (appointment reminders, two-way messaging, automated outreach). Note: Twilio Programmable Video was sunset in 2024 — do not use for new video builds.
- **API Documentation:** https://www.twilio.com/docs
- **Healthcare Solutions:** https://www.twilio.com/en-us/solutions/healthcare
- **SDKs/Libraries:** Python, Node.js, Java, C#, PHP, Ruby, Go; Twilio CLI
- **Standards:** REST/JSON API; TwiML (XML dialect for call control); HIPAA-eligible services with BAA
- **Authentication:** API Key + Secret (account SID); OAuth 2.0 for some products
- **Telehealth Relevance:** SMS appointment reminders with two-way confirmation; voice IVR for appointment management; HIPAA-compliant messaging. Relevant for the patient engagement and notification layer of a telehealth platform. Twilio Flex can support healthcare contact centre use cases (e.g., nurse triage lines).

---

### Zoom for Healthcare

- **Description:** HIPAA-compliant video conferencing platform for telehealth, providing standard Zoom UX with a signed BAA. Not a full telehealth platform — scheduling, clinical documentation, and billing require separate systems.
- **API Documentation:** https://developers.zoom.us/docs/api/
- **Marketplace / Integration Hub:** https://marketplace.zoom.us/
- **SDKs/Libraries:** Zoom Video SDK (Web, iOS, Android, Windows, macOS, Linux); Zoom Meeting SDK; REST API client libraries in multiple languages
- **Standards:** REST/JSON API; OAuth 2.0 for Marketplace app authentication; DTLS-SRTP media encryption; WebRTC transport
- **Authentication:** OAuth 2.0 (user-managed apps); Server-to-Server OAuth (machine-to-machine); JWT (legacy, being deprecated); API Key for Video SDK
- **Telehealth Relevance:** EHR scheduling integrations (Epic, Oracle, Athenahealth) can generate Zoom meeting links via Zoom API at appointment creation time. Zoom AI Companion API can generate meeting summaries (requires BAA verification for clinical use). Zoom for Healthcare BAA must be explicitly executed — standard Zoom does not qualify for PHI handling.

---

### Doxy.me

- **Description:** Browser-based HIPAA-compliant video visit platform for solo practitioners and small practices. Notable for its free tier with unlimited video sessions. Offers an Embeddable SDK and webhook events for integration with EHR and scheduling tools.
- **API Documentation / Help Centre:** https://help.doxy.me/en/collections/1950767-integrations
- **Embeddable SDK:** https://help.doxy.me/en/articles/12757252-doxy-me-embeddable-sdk
- **Integration Contact:** integrations@doxy.me
- **SDKs/Libraries:** JavaScript Embeddable SDK (iframe-based integration); Webhook events (patient check-in, call start, call end, patient leaves queue)
- **Standards:** REST/JSON; WebRTC transport; DTLS-SRTP media encryption; HIPAA BAA provided including free tier
- **Authentication:** API key; webhook signature verification
- **Telehealth Relevance:** The Embeddable SDK allows telehealth platform builders to embed Doxy.me video sessions within a custom patient portal or provider dashboard. Webhook events enable external workflows (e.g., trigger EHR check-in, start session timer) based on patient arrival and session lifecycle events.

---

### HealthTap Developer Platform (HealthTap Cloud)

- **Description:** HealthTap's microservices-based developer API platform providing AI-powered triage, virtual primary care consultation, symptom checking, and prescription management capabilities that can be embedded into third-party health applications.
- **Developer Portal:** https://developers.healthtap.com/
- **Standards:** REST/JSON API; HL7 FHIR and HL7 standards compatibility noted; NCPDP SCRIPT for prescription transmission
- **Authentication:** API Key; OAuth 2.0 for user-facing app flows
- **Telehealth Relevance:** Useful as a reference for AI-native pre-visit triage API design. HealthTap's Doctor A.I. is trained on 104,000 physician-contributed clinical responses — their symptom checker and urgency routing API represents the current state of the art in consumer AI triage. The developer platform allows embedding triage, consultation, and prescription services as microservices within a broader telehealth platform.

---

### Mend

- **Description:** Enterprise patient engagement and telehealth platform with AI-powered no-show prediction (up to 99% accuracy per vendor claims). Integrates with 100+ EHR and PMS systems via SMART FHIR, HL7, ADT, SFTP, and REST APIs.
- **EHR Integration Documentation:** https://mend.com/features/seamless-ehr-pms-integrations/
- **SDKs/Libraries:** No public SDK; integration via HL7 v2.x, FHIR R4, ADT, and SFTP data exchange with EHR/PMS systems
- **Standards:** HL7 FHIR R4, HL7 v2.x ADT, SMART on FHIR, SFTP; HIPAA BAA provided; SOC 2 certified
- **Authentication:** SSO via health system identity provider; API Key for data integrations
- **Telehealth Relevance:** Mend's no-show prediction algorithm (PredictiveIQ) and proactive waitlist backfill automation are the most developed implementations of AI-driven attendance management in telehealth. Their EHR write-back capability (intake forms and session notes directly into the EHR) is a useful integration pattern to replicate.

---

## Notes

**Emerging and Evolving Areas:**

1. **DEA Controlled Substance Prescribing via Telehealth (2026 and beyond):** The regulatory framework for Schedule II substance prescribing via telehealth (without prior in-person visit) remains unsettled as of May 2026. The DEA's extended COVID-era flexibilities expire December 31, 2025; the final special registration rules will govern 2026 practice. Any telehealth platform supporting psychiatric or pain management specialties must monitor DEA rulemaking closely.

2. **HIPAA Security Rule Final Rule (Expected May 2026):** The proposed NPRM (January 2025) will become a final rule likely in May 2026, eliminating the "addressable" vs. "required" distinction and mandating multi-factor authentication, encryption at rest, and vulnerability scanning as explicit requirements rather than risk-assessed options. Design to the proposed standards now.

3. **HL7 FHIR R5 and R6:** FHIR R5 (v5.0.0) is published and FHIR R6 ballot is underway (build.fhir.org). New builds should target R4 for maximum EHR compatibility in 2026, but architects should be aware of R5/R6 directions for future-proofing. Oracle Health deprecated DSTU 2 in December 2025; Epic remains R4-primary.

4. **AI Transcription and Clinical Note APIs (Emerging Standards Gap):** There is currently no standardised API or data model for AI-generated clinical notes from telehealth video sessions. Daily.co's Clinical Notes API, Nuance DAX (Microsoft), and Suki are each proprietary. The output format of AI-generated SOAP notes for EHR write-back is typically a FHIR `DocumentReference` resource — but the AI processing pipeline itself is unstandarised. Watch for HL7 working groups addressing AI-generated clinical documentation provenance.

5. **IHE Virtual Consult Profile:** The IHE Patient Care Coordination domain maintains integration profiles for virtual consultations. Check https://profiles.ihe.net/ for the current Virtual Consult Profile specification, which defines standardised workflow for telehealth consultations integrated with EHR scheduling and referral systems.
