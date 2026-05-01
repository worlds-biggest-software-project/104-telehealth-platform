# Telehealth Platform

> Candidate #104 · Researched: 2026-05-01

## Existing Products and Software Packages

| Name | Description | Model | Pricing |
|------|-------------|-------|---------|
| Teladoc Health | Largest US telehealth provider by revenue; general medicine, chronic care, mental health, and dermatology. Acquired BetterHelp and Livongo. Acquired Catapult Health (Feb 2025). | SaaS / Direct-to-consumer | Per-visit ($75–$95 PMPM); enterprise custom |
| Amwell (American Well) | Enterprise telehealth platform for health systems and payers; integrated with Cerner EHR (March 2025 partnership). | SaaS | Custom enterprise |
| Doxy.me | HIPAA-compliant browser-based video visit platform; simple, free tier available. Popular with independent providers. | SaaS | Free (basic); $35–$50/provider/month (pro) |
| MDLIVE | Telehealth platform for urgent care, behavioral health, and dermatology; owned by Evernorth (Cigna). | SaaS | Per-visit or insurance-based |
| Doctor on Demand | Virtual primary and behavioral health care platform; acquired by Grand Rounds Health, now Included Health. | SaaS | Per-visit or employer subscription |
| Zoom for Healthcare | HIPAA-compliant video conferencing with healthcare-specific BAA; integrates with EHRs via API. Not a full telehealth platform. | SaaS | ~$200/provider/month (healthcare tier) |
| HealthTap | AI-powered telehealth with triage and virtual primary care; uses AI for symptom checking before connecting to physicians. | SaaS | Subscription (~$15/month consumer) |
| Healow TeleVisit (eClinicalWorks) | Telehealth module integrated natively with eClinicalWorks EHR; virtual waiting room and e-prescribing. | SaaS | Bundled with eClinicalWorks EHR |
| Mend | Patient engagement and telehealth platform with AI-driven no-show prediction and virtual visits. | SaaS | Custom per-practice |
| HCW@Home | Open-source teleconsultation platform for healthcare workers; WebRTC-based. | Open Source | Free |
| OpenTeleHealth | Open-source telehealth framework; WebRTC video sessions, patient forms, and EHR integration connectors. | Open Source | Free |

## Relevant Industry Standards or Protocols

| Standard | Relevance |
|----------|-----------|
| WebRTC (Web Real-Time Communication) | W3C/IETF open standard for browser-based peer-to-peer audio/video; the underlying technology for most telehealth video sessions |
| NCPDP SCRIPT Standard (v2017071 and newer) | National standard for electronic prescribing (e-prescribing) transactions between prescribers and pharmacies; mandated by CMS for Medicare Part D |
| NCPDP EPCS (Electronic Prescribing for Controlled Substances) | DEA-compliant standard for transmitting controlled substance prescriptions electronically; essential for telehealth prescribing post-COVID |
| HL7 FHIR R4 | Interoperability standard for exchanging patient data between telehealth platforms and EHR systems |
| HL7 v2.x (ADT, ORM messages) | Legacy messaging for connecting telehealth platforms to hospital ADT and order management systems |
| HIPAA Security Rule (45 CFR Part 164) | Mandates encryption, access controls, and audit logging for all telehealth video and data transmissions |
| Telehealth Modernization Act (2021) / COVID-19 flexibilities | US legislative framework expanding reimbursable telehealth services; permanent extensions under ongoing legislative review |
| FCC Telehealth Broadband Programs | Federal Communications Commission programs (e.g., Connected Care Pilot) funding telehealth infrastructure in underserved areas |
| DTLS-SRTP (WebRTC encryption) | Transport Layer Security profiles used within WebRTC to encrypt media streams; relevant to HIPAA compliance architecture |
| IHE Virtual Consult Profile | IHE profile for standardized workflow for virtual consultations integrated with EHR and scheduling systems |

## Available Research Materials

| Citation | Type |
|----------|------|
| Dorsey, E.R., & Topol, E.J. (2016). State of telehealth. *New England Journal of Medicine*, 375(2), 154–161. | Peer-Reviewed Article (foundational) |
| Wosik, J., et al. (2020). Telehealth transformation: COVID-19 and the rise of virtual care. *Journal of the American Medical Informatics Association*, 27(6), 957–962. | Peer-Reviewed Article |
| Imlach, F., et al. (2020). Telehealth consultations in general practice during a pandemic lockdown: survey and interviews on patient experiences and preferences. *BMC Family Practice*, 21(1), 1–14. | Peer-Reviewed Article |
| Gajarawala, S.N., & Pelkowski, J.N. (2021). Telehealth benefits and barriers. *Journal for Nurse Practitioners*, 17(2), 218–221. | Peer-Reviewed Article |
| Calton, B., et al. (2020). Telemedicine in palliative care: a mini-review. *Telemedicine and e-Health*, 26(5), 531–539. | Peer-Reviewed Article |
| Portnoy, J., et al. (2020). Telemedicine in the era of COVID-19. *Journal of Allergy and Clinical Immunology: In Practice*, 8(5), 1489–1491. | Peer-Reviewed Article |
| Markets and Markets. (2025). *Telehealth and Telemedicine Market Report 2025–2030*. https://www.marketsandmarkets.com/Market-Reports/telehealth-market-201868927.html | Market Report |
| Grand View Research. (2024). *Telemedicine Market – Industry Analysis, Size & Forecast to 2030*. https://www.grandviewresearch.com/industry-analysis/telemedicine-industry | Market Report |
| Tuckson, R.V., et al. (2017). Telehealth. *New England Journal of Medicine*, 377(16), 1585–1592. | Peer-Reviewed Article |
| Jacobs, J.C., et al. (2023). PMC. *WebRTC: Delivering telehealth in the browser*. https://pmc.ncbi.nlm.nih.gov/articles/PMC5344122/ | Technical / Research Article |

## Market Research

**Market Size:** The global telehealth market was valued at approximately USD 146–178 billion in 2024–2025 (estimates vary by scope) and is projected to reach USD 851–858 billion by 2033–2035, at a CAGR of approximately 17–22% depending on the source. The US telemedicine market alone is projected to reach USD 160.45 billion by 2034 (Nova One Advisor). Web/cloud-based delivery accounts for ~61% of the market.

**Pricing Landscape:**

| Segment | Typical Price |
|---------|--------------|
| Direct-to-consumer per visit | $35–$95/visit |
| Employer / PMPM model | $5–$20 PMPM (per member per month) |
| Provider platform (Doxy.me, Zoom Healthcare) | $0 (free tier) – $200/provider/month |
| Enterprise health system platform (Amwell, Teladoc enterprise) | Custom; $500K–$5M+/yr |
| White-label telehealth platforms | $2,000–$20,000/month platform fee + per-visit fees |

**Key Buyer Personas:**
- Hospital and health system CMOs adopting virtual care to extend geographic reach and reduce ED load
- Employer HR and benefits directors seeking to reduce absenteeism and expand employee healthcare access
- Payer medical directors embedding telehealth into value-based care arrangements
- Mental / behavioral health practice owners needing fully remote-capable practice platforms
- Direct-to-consumer patients (especially younger demographics) seeking on-demand urgent care access

**Notable Funding / Acquisitions:**
- Teladoc Health acquired Livongo Health for USD 18.5 billion (2020) and BetterHelp (mental health) earlier. Acquired Catapult Health (February 2025) for USD 65 million.
- Amazon Clinic launched (2022) and rebranded as Amazon One Medical after acquiring One Medical for USD 3.9 billion (2023).
- Hims & Hers Health (telehealth + pharmacy) went public via SPAC at ~USD 1.6 billion (2021); reached ~USD 2.5 billion market cap by 2025.
- Doctor on Demand merged with Grand Rounds Health (2021), then rebranded as Included Health; combined valuation ~USD 2 billion.
- Amwell raised USD 742 million in IPO (September 2020) on NYSE.

## AI-Native Opportunity

- **AI-powered pre-visit triage and symptom assessment:** Before connecting to a clinician, an AI agent can conduct structured symptom gathering, assess urgency, suggest the appropriate care level (urgent care vs. primary care vs. ED), and pre-populate the clinical note — reducing appointment time and improving provider preparation.
- **Real-time clinical decision support during consultation:** AI can listen to the telehealth conversation and surface relevant clinical guidelines, drug interaction alerts, and diagnostic suggestions to the provider in real time, improving care quality without disrupting the patient encounter.
- **Automated post-visit documentation and coding:** Following a video consultation, AI can generate the clinical note, suggest billing codes, and send prescriptions — eliminating the documentation tail that drives physician burnout and extends encounter time.
- **Intelligent virtual waiting room and no-show prediction:** AI can analyze patient behavior signals (booking patterns, engagement with reminders, historical attendance) to predict no-shows and dynamically fill slots, reducing idle provider time which is a major economic problem in telehealth.
- **Asynchronous AI-mediated care pathways:** For chronic disease management and low-acuity conditions, AI can handle substantial care delivery asynchronously (reviewing submitted photos, lab results, and symptom surveys) and only escalate to synchronous video consultation when clinical complexity warrants it — dramatically reducing cost per episode of care.
