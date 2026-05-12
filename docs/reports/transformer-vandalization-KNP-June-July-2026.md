# Transformer Vandalization

> Prepared for Kiambu National Polytechnic — June–July 2026

![Kiambu National Polytechnic - Logo Placeholder](../images/knp-logo-placeholder.png)

Report Title: Transformer Vandalization

Prepared by: Janet Njenga

Signatory Title: Student, Diploma in Electrical & Electronic Engineering

Lecturer / Recipient: Lecturer Andrew Muia

Department: Diploma in Electrical & Electronic Engineering

Series / Cover date: June–July 2026

Classification: Institutional Report — Non-Technical

---

Executive Summary

This report explains the concept of "transformer vandalization" — unauthorized modification, corruption, or manipulation of transformer-based machine learning models or their supporting systems — in clear, non-technical language suitable for institutional review. The document is intended for the Department of Diploma in Electrical & Electronic Engineering at Kiambu National Polytechnic as part of the June–July series assessment.

The report covers: an accessible introduction to transformer models and their uses; clear definitions of vandalization and associated risks; common attack methods and origins; organizational and operational impacts; practical prevention, detection, and response guidance tailored for academic and institutional environments; case studies demonstrating likely scenarios relevant to the June–July series; recommended policies and an implementation roadmap for the department.

Key recommendations include establishing governance and ownership for deployed models, implementing secure storage and access controls for model and data artifacts, regular behavioral monitoring and baseline checks, staff training, and an incident response plan adapted for the academic context.

---

Acknowledgements

This report was prepared by Janet Njenga under the supervision of Lecturer Andrew Muia for the Diploma in Electrical & Electronic Engineering program at Kiambu National Polytechnic. The author thanks instructors, peers, and library resources consulted during preparation.

---

Table of Contents

1. Introduction and Context
2. What is Transformer Vandalization?
3. Types and Examples of Vandalization
4. How Vandalization Happens
5. Impacts and Consequences
6. Prevention and Best Practices (Institutional)
7. Detection and Monitoring (Non-Technical)
8. Incident Response and Recovery
9. Case Studies and June–July Context Examples
10. Recommendations and Implementation Roadmap for the Department
11. Glossary
12. References
13. Appendices (templates and checklists)

---

Chapter 1 — Introduction and Context

1.1 Purpose of this Report

The purpose of this report is to provide Kiambu National Polytechnic with a clear, practical overview of transformer vandalization and to recommend policies and procedures suitable for an academic environment. The document is deliberately non-technical so administrators, lecturers, and students can understand risks and responsibilities without specialized machine learning knowledge.

1.2 What are Transformer Models? (Plain language)

"Transformer" refers to a family of machine learning models used widely for tasks such as language understanding, translation, summarization, and image analysis. They are powerful tools that learn patterns from data and are used in research projects, classroom exercises, and institutional services (for example, automated grading assistants or content recommendations).

1.3 Relevance to Kiambu National Polytechnic

As educational institutions adopt more digital tools, many services rely on trained models or external model-based services. Understanding how these models can be damaged, manipulated, or misused is important for protecting students, staff, and institutional data.

---

Chapter 2 — What is Transformer Vandalization?

2.1 Simple Definition

Transformer vandalization is any intentional or accidental action that changes the behavior of a transformer model or its supporting data and systems in a harmful way. This includes unauthorized edits, corrupted training data, manipulated outputs, or hidden behaviors that trigger on specific inputs.

2.2 Why it Matters

Models used in academic settings can influence grading, provide advice, or handle personal data. If vandalized, models may provide wrong advice, leak data, or behave unpredictably—causing reputational, operational, and legal problems.

---

Chapter 3 — Types and Examples of Vandalization

3.1 Weight or Parameter Corruption (Explained)

Models are built from many numeric settings learned during training. If these settings are changed or corrupted, even slightly, the model's behavior can worsen or become unpredictable.

Example: A model used to classify assignments returns inconsistent results after a corrupted file was uploaded to shared storage.

3.2 Data Poisoning (Explained)

Training data is the information used to teach models. Introducing malicious or incorrect samples into training data can make models learn wrong behaviors or trigger hidden faults.

Example: During a student group project, an unvetted dataset contains deliberately mislabeled samples causing poor performance.

3.3 Architecture Manipulation or Configuration Changes

Changing the model structure, configuration files, or training settings can degrade performance or introduce vulnerabilities.

Example: An automated script mistakenly replaces a configuration file used for evaluation, leading to incorrect outputs.

3.4 Output Manipulation and Interception

An attacker or misconfigured service intercepts or alters outputs before they reach users.

Example: A third-party grading service modifies scores in-transit to a student portal.

3.5 Supply Chain Attacks

Compromise of third-party models, libraries, or tools (for example, downloading a pre-trained model that contains hidden problems).

Example: Using an externally sourced model from an unverified source that contains a hidden backdoor.

3.6 Insider and Credential-Based Risks

Authorized users with careless or malicious behavior can change models or data.

Example: A research assistant with access to lab storage unintentionally removes important model checkpoints.

---

Chapter 4 — How Vandalization Happens (Attack Surface and Origins)

4.1 Common Origins

- Weak access controls (shared or default passwords)
- Lack of backups or version control
- Use of unverified external model and data sources
- Insufficient monitoring of model performance
- Insider mistakes or malicious actions

4.2 Typical Pathways

- Direct modification of files on shared storage
- Compromised development tools or laptop used by staff or students
- Corrupted datasets uploaded to training pipelines
- Third-party services or libraries with hidden problems

4.3 Human and Process Factors

Human errors, lack of separation of duties, and unclear responsibilities increase risk.

Example: A single staff member is responsible for both uploading training data and approving production models without peer review.

---

Chapter 5 — Impacts and Consequences

5.1 Technical Impacts

- Model performance degradation
- Unreliable or inconsistent outputs
- Increased operational burden to debug and restore

5.2 Institutional and Operational Impacts

- Disruption of teaching and assessment processes
- Loss of service availability (if models are critical to a service)
- Additional costs to retrain or replace models

5.3 Reputational and Legal Impacts

- Misinformation affecting students or partners
- Loss of trust from stakeholders
- Potential regulatory or compliance issues if personal data is exposed

5.4 Student and Academic Integrity Concerns

- Misgraded assessments
- Unfair advantages if models favor certain inputs
- Loss of confidence in automated tools used in learning

---

Chapter 6 — Prevention and Best Practices (Institutional)

6.1 Governance and Ownership

- Define clear ownership for all model artifacts (who is responsible for each model)
- Maintain a register of models used in the department (purpose, owner, data sources)
- Establish approval workflows for deploying or updating models

6.2 Access Control and Authentication

- Use strong authentication for accounts with access to models and data
- Apply least-privilege principles; grant access only as needed
- Avoid shared accounts and rotate credentials when staff change

6.3 Version Control and Backups

- Store model files and training datasets in version-controlled repositories when possible
- Keep immutable backups of important artifacts and checkpoints
- Tag classroom and research releases for traceability

6.4 Data Handling and Validation

- Validate and catalog datasets before use
- Keep original copies of source data
- Use simple checks (sample inspection, basic statistics) to detect outliers

6.5 Third-Party Model and Dependency Policy

- Only use models and libraries from trusted, documented sources
- Maintain a list of approved third-party providers
- Vet external resources and verify checksums or signatures when possible

6.6 Training and Awareness

- Train staff and students on safe handling of datasets and models
- Provide guidelines for secure development and data sharing in coursework

6.7 Physical and Infrastructure Controls

- Secure physical storage devices and lab machines
- Limit removable media use in critical environments

---

Chapter 7 — Detection and Monitoring (Non-Technical)

7.1 Behavioral Monitoring

- Establish simple baseline expectations for model outputs (for example, score ranges or commonly expected results)
- Periodically review model outputs for sudden changes or unusual patterns

7.2 Performance Checks and Logs

- Track simple performance metrics (accuracy on sample tests, error rates)
- Maintain logs for model training activities and significant changes

7.3 File Integrity and Version Comparison

- Maintain checksums or version history for model files and important configuration files
- If a model behaves unexpectedly, compare to the last known-good version

7.4 Alerts and Manual Review Triggers

- Define thresholds for manual review (for example, if grading outputs deviate by a set margin)
- Keep a simple reporting channel where staff can flag suspicious outputs or behavior

---

Chapter 8 — Incident Response and Recovery (Institutional Plan)

8.1 Preparation

- Create a lightweight incident response team (IRT) within the department
- Prepare basic contact lists and responsibilities for incidents
- Keep copies of model artifacts and documentation offline

8.2 Detection and Triage

- When unusual behavior is reported, gather evidence (logs, model files, timestamps)
- Quickly determine whether the issue is human error, misconfiguration, or possible vandalization

8.3 Containment

- Temporarily take affected models or services offline if there is clear evidence of malicious manipulation
- Prevent further use until the model has been validated

8.4 Eradication and Recovery

- Restore the last known-good version from backups
- If backups are unavailable, consider retraining using verified datasets
- Document all steps taken during recovery

8.5 Post-Incident Review

- Conduct a short lessons-learned review within the department
- Update policies, checklists, and training materials based on findings

8.6 Communication

- Prepare a clear, factual communication plan for students, staff, and affected stakeholders
- Avoid technical details in public communications; focus on actions taken and expected timelines

---

Chapter 9 — Case Studies and June–July Context Examples

9.1 Case Study A: Classroom Dataset Pollution

Scenario: During a group assignment, a student uploads an edited dataset to the shared training area. The dataset includes mislabeled samples that go unnoticed and are used in a model training run. The resulting model gives inconsistent results during grading.

Response: Instructor notices unexpected grading distribution, suspends use of the model, restores previous checkpoint, and retrains after cleansing data. New controls: instructor restricts upload permissions and requires dataset review before training.

9.2 Case Study B: Use of an Unverified Pre-trained Model

Scenario: A student downloads a pre-trained model from an online repository without verification. The model later exhibits biased outputs and unusual behavior.

Response: Department policy introduced to require documentation when external models are used. All externally acquired models must be listed in the model register and approved by the lecturer.

9.3 Case Study C: Accidental Overwrite of Model Checkpoints

Scenario: A lab machine with shared storage has a scheduled cleanup that removes older checkpoints. Mid-semester, the active checkpoint is overwritten, causing degraded performance.

Response: Recovery from backup and implementation of retention policy and protected directories for active experiments.

9.4 Relevance to June–July Series

The June–July assessment series often involves training or evaluating models. The above cases illustrate realistic risks during tight assessment periods, and highlight the need for preventive controls, clear procedures, and quick response steps appropriate for short-term teaching cycles.

---

Chapter 10 — Recommendations and Implementation Roadmap for the Department

10.1 Immediate (0–1 month)

- Create a simple model register (spreadsheet): name, owner, purpose, location, last update
- Restrict write access to shared training areas; allow uploads only after instructor approval
- Take immediate backups of any models and important datasets used for assessment
- Communicate new handling rules to students and staff

10.2 Short-term (1–3 months)

- Implement basic version control for model artifacts (e.g., use a private repository or secure folder service)
- Develop and distribute a checklist for dataset validation and model deployment for student projects
- Provide a short training session for staff and students on safe dataset and model handling

10.3 Medium-term (3–9 months)

- Adopt formal policies for third-party model usage and dependency vetting
- Establish a lightweight Incident Response Team (IRT) and run a table-top exercise relevant to assessment scenarios
- Create institutional templates for communicating incidents to students and external partners

10.4 Long-term (9–18 months)

- Integrate monitoring processes for critical models used in production or assessment
- Consider technical controls (role-based access, automated backups, and file integrity checks)
- Include model governance topics in relevant coursework to build long-term capacity

10.5 Budget and Resource Considerations

The recommended steps emphasize process and governance changes that require minimal budget, focusing on training, policy, and simple access controls. Later stages may require investment in secure storage, backup solutions, or monitoring tools.

---

Glossary (Plain Language)

- Model: A trained system that makes predictions or performs tasks using data.
- Checkpoint: A saved copy of a model at a point in time.
- Dataset: Collection of examples used to train or evaluate a model.
- Baseline: A known-good set of behavior or performance used for comparison.
- Backdoor: A hidden behavior that triggers under specific inputs.
- Vandalization: Unauthorized damaging or altering of model behavior or artifacts.

---

References and Further Reading (Selected)

- NIST AI Risk Management Framework (overview documents)
- OWASP Machine Learning Security Project (guidance for ML security)
- Academic primers on adversarial examples and data poisoning (summary-level articles)
- Institutional IT security policies and data handling best practices

---

Appendix A: Example Short Incident Response Checklist (for lecturers)

1. Stop using the model immediately if questionable outputs are observed.  
2. Record the time, the sample inputs and outputs, and the names of users affected.  
3. Notify the appointed instructor or departmental contact.  
4. Move the suspect model to a secure location and preserve logs if possible.  
5. Restore from the last known-good checkpoint while investigation proceeds.  
6. Communicate to affected students and staff with clear, non-technical language.

Appendix B: Example Model Register Template (columns to include)

- Model name  
- Owner (staff or student)  
- Purpose (e.g., assignment name)  
- Data sources  
- Location (storage path or repository)  
- Last update  
- Notes / Approval status

Appendix C: Suggested Student Instructions for Safe Model Use

- Do not download or use external models without instructor approval.  
- Keep local copies of all raw datasets and do not overwrite shared datasets.  
- Label datasets and versions clearly in group work.  
- Report any unusual model outputs to the instructor immediately.

---

Cover Page and Signature Block (to be placed at the end of the document for printing)

Prepared by: Janet Njenga  
Title: Student, Diploma in Electrical & Electronic Engineering  
Lecturer: Andrew Muia  
Department: Diploma in Electrical & Electronic Engineering  
Series: June–July 2026

Signature: _________________________    Date: __________________

---

Notes on Logo and Final Formatting

A placeholder logo is included in this document. Please replace the placeholder image with the official Kiambu National Polytechnic logo before final printing. I recommend exporting to PDF using a standard converter (GitHub's print-to-PDF, Microsoft Word export, or a PDF generator such as pandoc or LibreOffice) after replacing the logo.

Conversion instructions (suggested):

- Option 1: On GitHub, open the rendered Markdown file, choose Print from the browser menu, and select "Save as PDF". Adjust page size to A4 and enable background graphics if desired.
- Option 2: Clone the repository locally and run a conversion tool:
  - Using pandoc: `pandoc docs/reports/transformer-vandalization-KNP-June-July-2026.md -o transformer-vandalization-KNP-June-July-2026.pdf --pdf-engine=wkhtmltopdf` (or use wkhtmltopdf or wkhtmltopdf default settings)
  - Using LibreOffice: open the document and Export as PDF

---

Document version: 1.0  
Prepared: 2026-05-12  
Repository target: docs/reports/transformer-vandalization-KNP-June-July-2026.md

