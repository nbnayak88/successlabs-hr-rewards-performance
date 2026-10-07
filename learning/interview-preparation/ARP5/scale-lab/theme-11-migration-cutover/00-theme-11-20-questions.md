# 20 Scenario-Based Interview Questions & STAR Answers

**Stream:** ARP5 — Applied SAP SuccessFactors Compensation & Variable Pay  
**Theme:** 11 — Migration & Cutover  
**Target:** 20 unique scenario-based interview questions  
**Answer method:** STAR — Situation → Task → Action → Result  
**Product posture:** HCM-first, Compensation & Variable Pay, migration-aware and architecture-led

## Purpose

This theme tests whether the candidate can move Compensation history, configuration, planning populations, and dependent data from a legacy or previous-state landscape into a controlled target state. The emphasis is on migration strategy, scope, mapping, cleansing, reconciliation, cutover sequencing, historical data, open cycles, dependencies, validation, contingency, and business continuity.

---

### HR-ARP5-B11-Q01
### Interview Question
How would you define the migration strategy for moving Compensation from a legacy platform to SAP SuccessFactors?

### STAR Answer
**Situation:** A global organization was replacing a legacy compensation planning solution with SAP SuccessFactors Compensation.  
**Task:** I needed to define what should migrate, what should be archived, and how the business would transition.  
**Action:** I classified configuration, employee eligibility data, compensation history, prior awards, planning records, audit requirements, and reference data. I defined migration waves, ownership, mapping, reconciliation, and cutover criteria.  
**Result:** The organization moved to the target solution without treating every legacy record as equally necessary.

### SAP SuccessFactors Compensation & Variable Pay Example
I would distinguish target-cycle configuration from historical compensation information and migrate only the history and reference data required for operational continuity, reporting, compliance, and employee context.

### SME Probe
How do you decide whether historical compensation data belongs in the new application or an archive?

---

### HR-ARP5-B11-Q02
### Interview Question
How would you determine the scope of Compensation data to migrate?

### STAR Answer
**Situation:** Business stakeholders requested migration of all historical compensation records.  
**Task:** I needed to establish a defensible migration scope.  
**Action:** I assessed business usage, legal and audit needs, reporting requirements, employee visibility, data quality, retention policy, and technical feasibility. I separated mandatory, valuable, and unnecessary history.  
**Result:** Migration scope was reduced without losing business-critical information.

### SAP SuccessFactors Compensation & Variable Pay Example
The scope would normally consider compensation statements, historical awards, pay changes, planning history, and information required for future eligibility or analytics, subject to the target design.

### SME Probe
What is the danger of migrating history simply because it exists?

---

### HR-ARP5-B11-Q03
### Interview Question
How would you migrate compensation configuration from a legacy design into SuccessFactors Compensation?

### STAR Answer
**Situation:** The legacy system had different concepts for eligibility, guidelines, budgets, worksheets, and approvals.  
**Task:** I needed to translate the legacy design into the target product model.  
**Action:** I created a configuration mapping between legacy concepts and SuccessFactors capabilities, identifying direct mappings, redesigns, and items that should not be reproduced.  
**Result:** The target solution reflected business intent rather than becoming a copy of legacy configuration.

### SAP SuccessFactors Compensation & Variable Pay Example
I would map eligibility rules, components, guidelines, budget structures, workflow, permissions, and planning behavior to the supported Compensation model.

### SME Probe
When should migration become transformation rather than replication?

---

### HR-ARP5-B11-Q04
### Interview Question
How would you prepare legacy compensation data for migration?

### STAR Answer
**Situation:** Legacy data contained inconsistent employee identifiers, currencies, dates, organizational structures, and compensation components.  
**Task:** I needed migration-ready data.  
**Action:** I established profiling, cleansing, standardization, duplicate detection, effective-date validation, reference-data mapping, and reconciliation rules.  
**Result:** Data quality improved before loading rather than discovering defects after cutover.

### SAP SuccessFactors Compensation & Variable Pay Example
I would reconcile employee identifiers with Employee Central, standardize compensation component semantics, validate currencies and effective dates, and establish source-to-target mappings.

### SME Probe
Which data-quality issue would cause you to stop a migration load?

---

### HR-ARP5-B11-Q05
### Interview Question
How would you create a source-to-target mapping for Compensation migration?

### STAR Answer
**Situation:** Multiple legacy fields represented similar concepts with different names and meanings.  
**Task:** I needed an unambiguous migration mapping.  
**Action:** I documented source field, business definition, target field, transformation rule, default behavior, validation rule, owner, and exception handling.  
**Result:** Functional, data, and technical teams had a shared migration contract.

### SAP SuccessFactors Compensation & Variable Pay Example
The mapping would cover employee keys, compensation components, eligibility attributes, currency, dates, organizational attributes, historical awards, and relevant planning values.

### SME Probe
Why is a field name alone insufficient for migration mapping?

---

### HR-ARP5-B11-Q06
### Interview Question
How would you migrate historical compensation data while preserving business meaning?

### STAR Answer
**Situation:** Leaders needed multi-year compensation history after the legacy platform was retired.  
**Task:** I needed to preserve analytical meaning rather than merely move values.  
**Action:** I documented the historical calculation semantics, component definitions, currencies, effective dates, organizational context, and source lineage. I retained unavailable legacy concepts through controlled mapping or archive references.  
**Result:** Historical reporting remained interpretable after migration.

### SAP SuccessFactors Compensation & Variable Pay Example
Historical merit, bonus, incentive, and award values should retain component and effective-date meaning so future analysis is not distorted.

### SME Probe
What is more important for historical data: value preservation or semantic preservation?

---

### HR-ARP5-B11-Q07
### Interview Question
How would you handle employees who change managers or organizations during migration?

### STAR Answer
**Situation:** Employee hierarchy changed between the legacy extract and target cutover.  
**Task:** I needed to prevent incorrect Compensation ownership.  
**Action:** I established an effective-dated reconciliation between source hierarchy, Employee Central hierarchy, and cutover date. I identified transfers, promotions, inactive employees, and new managers.  
**Result:** Planning responsibility aligned with the target organizational structure.

### SAP SuccessFactors Compensation & Variable Pay Example
Manager hierarchy and employee status should be validated against the effective cutover population before Compensation worksheets are generated or released.

### SME Probe
Which effective date should govern manager ownership?

---

### HR-ARP5-B11-Q08
### Interview Question
How would you migrate compensation data when currencies differ across countries?

### STAR Answer
**Situation:** A global legacy platform stored compensation values in different currencies and formats.  
**Task:** I needed to preserve financial meaning without introducing conversion errors.  
**Action:** I documented source currency, target currency, conversion rules, effective dates, rounding, and reporting expectations. I reconciled converted totals against approved business baselines.  
**Result:** Global historical values remained auditable and comparable.

### SAP SuccessFactors Compensation & Variable Pay Example
I would validate currency configuration and explicitly define whether historical values remain in source currency or are represented in a target reporting currency.

### SME Probe
Why must currency conversion rules be treated as migration logic rather than a formatting detail?

---

### HR-ARP5-B11-Q09
### Interview Question
How would you migrate an in-flight Compensation cycle?

### STAR Answer
**Situation:** The legacy compensation cycle was already open when the implementation timeline required transition to SuccessFactors.  
**Task:** I needed to avoid losing manager decisions or creating duplicate planning work.  
**Action:** I assessed cycle stage, completed versus pending decisions, approvals, recommendations, budgets, and downstream dependencies. I chose a controlled freeze, conversion, or completion strategy based on business risk.  
**Result:** The organization avoided an uncontrolled mid-cycle switch.

### SAP SuccessFactors Compensation & Variable Pay Example
For an active cycle, I would evaluate whether to complete it in the source system, freeze and migrate approved outcomes, or transition planning under a tightly controlled cutover model.

### SME Probe
Why is an in-flight cycle fundamentally different from historical-data migration?

---

### HR-ARP5-B11-Q10
### Interview Question
How would you migrate Variable Pay history?

### STAR Answer
**Situation:** The business needed prior incentive outcomes available after moving to the new platform.  
**Task:** I needed to preserve meaningful Variable Pay history.  
**Action:** I identified plan, participant, eligibility, performance metric, calculated amount, approved award, currency, payment status, and effective period information. I reconciled totals with source reports.  
**Result:** Historical incentive outcomes remained usable for reporting and employee context.

### SAP SuccessFactors Compensation & Variable Pay Example
I would determine which Variable Pay historical attributes are required in the target platform versus enterprise reporting or archival storage.

### SME Probe
Which Variable Pay fields are essential for preserving historical meaning?

---

### HR-ARP5-B11-Q11
### Interview Question
How would you reconcile migrated Compensation data?

### STAR Answer
**Situation:** Initial migration loads produced small differences from legacy totals.  
**Task:** I needed to establish whether differences were expected transformations or defects.  
**Action:** I reconciled record counts, employee populations, component totals, currencies, effective dates, awards, exceptions, and control totals at multiple levels.  
**Result:** Genuine defects were isolated while approved transformation differences were documented.

### SAP SuccessFactors Compensation & Variable Pay Example
Reconciliation should compare source and target populations and financial measures by cycle, component, currency, organization, and other agreed control dimensions.

### SME Probe
What is the difference between validation and reconciliation?

---

### HR-ARP5-B11-Q12
### Interview Question
How would you plan mock migrations before Compensation cutover?

### STAR Answer
**Situation:** The first migration attempt exposed timing and mapping problems too late.  
**Task:** I needed repeatable migration rehearsals.  
**Action:** I scheduled mock migrations using representative data, measured extraction, transformation, load, reconciliation, defect correction, and recovery times, and captured lessons for each rehearsal.  
**Result:** The final cutover became more predictable.

### SAP SuccessFactors Compensation & Variable Pay Example
Mock migration should validate data extracts, mappings, target loads, population results, historical values, and reconciliation before production cutover.

### SME Probe
What should change between Mock 1 and the final migration rehearsal?

---

### HR-ARP5-B11-Q13
### Interview Question
How would you sequence Compensation migration dependencies?

### STAR Answer
**Situation:** Compensation depended on Employee Central, Performance & Goals, security, integrations, and payroll.  
**Task:** I needed to define the correct migration order.  
**Action:** I mapped prerequisites such as employee and organizational data, compensation components, performance inputs, configuration, security, integrations, and downstream validation. I identified hard dependencies and parallelizable activities.  
**Result:** Migration activities could proceed without creating avoidable rework.

### SAP SuccessFactors Compensation & Variable Pay Example
Employee Central foundation data must be available before dependent Compensation populations can be reliably established.

### SME Probe
Which dependency cannot safely be treated as optional?

---

### HR-ARP5-B11-Q14
### Interview Question
How would you perform the final Compensation cutover?

### STAR Answer
**Situation:** The target system had passed migration rehearsal and the organization was ready for production transition.  
**Task:** I needed to execute the final cutover with minimal business disruption.  
**Action:** I froze source changes at the agreed point, captured final extracts, executed transformations and loads, reconciled control totals, validated configuration and security, performed business smoke checks, obtained sign-off, and opened the target cycle.  
**Result:** The business transitioned through a controlled sequence with clear evidence at each gate.

### SAP SuccessFactors Compensation & Variable Pay Example
The cutover runbook would explicitly cover final population, historical/reference data, Compensation configuration, access, integrations, reconciliation, business validation, and cycle opening.

### SME Probe
What is the most important control during the cutover freeze?

---

### HR-ARP5-B11-Q15
### Interview Question
How would you manage migration exceptions?

### STAR Answer
**Situation:** A small population had missing eligibility attributes and inconsistent historical records.  
**Task:** I needed to prevent exceptions from blocking the entire migration unnecessarily.  
**Action:** I categorized exceptions by severity, defined business owners, created correction or default rules, tracked unresolved records, and established explicit acceptance criteria.  
**Result:** Critical data was protected while manageable exceptions were handled transparently.

### SAP SuccessFactors Compensation & Variable Pay Example
Exceptions affecting eligibility, awards, calculations, or financial totals would receive higher priority than cosmetic or archival issues.

### SME Probe
When should an exception block cutover?

---

### HR-ARP5-B11-Q16
### Interview Question
How would you handle a migration where source and target compensation structures are not equivalent?

### STAR Answer
**Situation:** The legacy platform supported custom compensation concepts that did not have direct equivalents in SuccessFactors.  
**Task:** I needed to preserve business intent without creating unsupported complexity.  
**Action:** I classified each concept as map, redesign, archive, or retire. I involved business owners in decisions and documented any loss of functionality or semantics.  
**Result:** The target architecture remained supportable while critical business outcomes were retained.

### SAP SuccessFactors Compensation & Variable Pay Example
I would use standard SuccessFactors Compensation capabilities where they meet the requirement and avoid recreating legacy customizations without a clear business case.

### SME Probe
What evidence justifies retaining a non-standard legacy behavior?

---

### HR-ARP5-B11-Q17
### Interview Question
How would you plan rollback during Compensation migration?

### STAR Answer
**Situation:** A production migration could potentially produce incorrect populations or historical values.  
**Task:** I needed a recovery strategy before cutover.  
**Action:** I defined source freeze rules, backup/extract retention, target recovery steps, reconciliation thresholds, decision authority, communication, and business continuity procedures.  
**Result:** The organization could return to a known operating state if migration acceptance criteria failed.

### SAP SuccessFactors Compensation & Variable Pay Example
Rollback planning should protect both source-system continuity and target-system data integrity, especially where an active Compensation cycle is involved.

### SME Probe
Why is rollback harder after business users begin making target-system decisions?

---

### HR-ARP5-B11-Q18
### Interview Question
How would you manage migration cutover across multiple countries or regions?

### STAR Answer
**Situation:** A global Compensation deployment had different local calendars, currencies, payroll schedules, and organizational structures.  
**Task:** I needed a global migration with controlled local sequencing.  
**Action:** I defined a global template, regional variations, wave criteria, local owners, time-zone sequencing, reconciliation controls, and country-specific contingency plans.  
**Result:** The migration scaled without losing local operational control.

### SAP SuccessFactors Compensation & Variable Pay Example
I would use phased waves where necessary, validating each region's population, currency, configuration, payroll dependency, and business sign-off before expansion.

### SME Probe
When is a phased migration safer than a big-bang approach?

---

### HR-ARP5-B11-Q19
### Interview Question
How would you prove that Compensation migration was successful?

### STAR Answer
**Situation:** Leadership wanted more than a completed load report before approving cutover closure.  
**Task:** I needed measurable migration acceptance criteria.  
**Action:** I established measures for record counts, population accuracy, compensation totals, historical values, eligibility, configuration integrity, integration readiness, critical exceptions, and business sign-off.  
**Result:** Migration completion became an evidence-based business decision.

### SAP SuccessFactors Compensation & Variable Pay Example
I would compare agreed source control totals and target results and obtain functional and business-owner acceptance before declaring migration complete.

### SME Probe
What is the strongest evidence that a migration preserved business meaning?

---

### HR-ARP5-B11-Q20
### Interview Question
As a Compensation architect, how would you create a reusable migration and cutover framework?

### STAR Answer
**Situation:** Each HR transformation project was reinventing migration activities and controls.  
**Task:** I needed a repeatable enterprise migration capability.  
**Action:** I standardized discovery, scope classification, profiling, mapping, cleansing, mock migrations, reconciliation, cutover, rollback, exception management, business validation, and handoff. I separated reusable controls from project-specific rules.  
**Result:** Future Compensation migrations became faster, more predictable, and auditable.

### SAP SuccessFactors Compensation & Variable Pay Example
The framework would provide reusable migration templates for employee/organization dependencies, Compensation history, Variable Pay history, configuration mapping, reconciliation, cutover, and operational handoff.

### SME Probe
Which migration artifacts should become enterprise assets rather than project documents?

---

## Theme 11 Completion Standard

- **20/20 unique scenario-based questions completed**
- **20/20 STAR answers completed**
- **20/20 SAP SuccessFactors Compensation & Variable Pay examples included**
- **20/20 SME probes included**
- Migration strategy and scope covered
- Source-to-target mapping covered
- Data cleansing and historical semantics covered
- Configuration migration covered
- In-flight cycle migration covered
- Variable Pay history covered
- Reconciliation and mock migration covered
- Dependency sequencing covered
- Production cutover covered
- Exception and rollback management covered
- Global/phased migration covered
- Migration acceptance and reusable framework covered

**Cumulative ARP5 progress: 11/22 themes = 220/440 scenarios.**
