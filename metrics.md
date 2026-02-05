# Metrics Catalog

| Metric ID | Title | Associated Tests |
|----------|------|----------------|
| data.reused.co.1 | maDMP declares reused datasets | [View](tests.md#test-check-for-reused-dataset-declaration) |
| data.reused.co.2 | Reused Data PID | [View](tests.md#test-check-for-reused-dataset-pid) |
| data.reused.co.3 | Reused Data License | [View](tests.md#test-license-for-reused-datasets) |
| data.reused.co.4 | Reused Data Source | [View](tests.md#test-distribution-present) |
| data.reused.co.5 | Reused Data Access | [View](tests.md#test-access-rights-for-reused-datasets) |
| data.reused.co.6 | Reused Data Personal | [View](tests.md#test-personal-data-for-reused-datasets) |
| data.reused.co.7 | Reused Data Sensitive | [View](tests.md#test-sensitive-data-for-reused-datasets) |
| data.reused.co.8 | Reused Data URL | [View](tests.md#test-access-url) |
| data.reused.feas.1 | Repository Reused Data PID | [View](tests.md#test-pid-matches-destination-repository-record) |
| data.reused.feas.2 | Repository Reused Data Access | [View](tests.md#test-reused-data-access-matches-destination) |
| data.reused.feas.3 | Repository Reused Data License | [View](tests.md#test-reused-data-license-matches-destination) |

---

## Metric: maDMP declares reused datasets

**Metric ID:** data.reused.co.1  
**Persistent URI:** https://example.org/metric/madmp-reused-datasets-declared  

### Narrative  
The machine-actionable Data Management Plan (maDMP) declares whether any dataset described in the plan is reused.

### Intended Outcome  
Determine whether reuse of datasets is explicitly declared in the maDMP.

### Applies To  
Machine-actionable Data Management Plan (maDMP) in JSON format.

### Success Criterion  
At least one dataset entry in the maDMP contains a boolean field indicating reuse.

### Failure Criterion  
No dataset entry contains reuse information.

### Expected Result Type  
Boolean (pass/fail)

### Associated Test  
- [Check for reused dataset declaration](tests.md#test-check-for-reused-dataset-declaration)

---

## Metric: Reused Data PID

**Metric ID:** data.reused.co.2  

### Narrative  
Verifies that reused datasets come with PIDs.

### Intended Outcome  
Determine whether reused datasets include persistent identifiers.

### Applies To  
maDMP JSON

### Success Criterion  
For each reused dataset (`is_reused=true`), an identifier is present and, where applicable, a type is provided.

### Failure Criterion  
At least one reused dataset lacks identifier metadata.

### Expected Result Type  
Boolean (pass/fail)

### Associated Test  
- [Check for reused dataset PID](tests.md#test-check-for-reused-dataset-pid)

---

## Metric: Reused Data License

**Metric ID:** data.reused.co.3  

### Narrative  
Verifies that reused datasets come with license.

### Intended Outcome  
Determine whether reused datasets include license metadata.

### Success Criterion  
For each reused dataset, license information is present.

### Failure Criterion  
At least one reused dataset lacks license information.

### Expected Result Type  
Boolean (pass/fail)

### Associated Test  
- [License for reused datasets](tests.md#test-license-for-reused-datasets)

---

## Metric: Reused Data Source

**Metric ID:** data.reused.co.4  

### Narrative  
Verifies that reused datasets are shared.

### Intended Outcome  
Determine whether reused datasets include distribution/source metadata.

### Success Criterion  
Distribution metadata exists and includes identifying information.

### Failure Criterion  
Missing distribution metadata.

### Expected Result Type  
Boolean (pass/fail)

### Associated Tests  
- [Distribution present](tests.md#test-distribution-present)  
- [Distribution access information](tests.md#test-distribution-access-information)  
- [Distribution title](tests.md#test-distribution-title)

---

## Metric: Reused Data Access

**Metric ID:** data.reused.co.5  

### Narrative  
Verifies the access rights of the reused datasets.

### Success Criterion  
`data_access` exists and equals open/shared/closed.

### Failure Criterion  
Missing or invalid `data_access`.

### Expected Result Type  
Boolean

### Associated Test  
- [Access rights for reused datasets](tests.md#test-access-rights-for-reused-datasets)

---

## Metric: Reused Data Personal

**Metric ID:** data.reused.co.6  

### Narrative  
Verifies the existence of personal data.

### Success Criterion  
`personal_data` exists and is explicit.

### Failure Criterion  
Missing or undefined `personal_data`.

### Expected Result Type  
Boolean

### Associated Test  
- [Personal data for reused datasets](tests.md#test-personal-data-for-reused-datasets)

---

## Metric: Reused Data Sensitive

**Metric ID:** data.reused.co.7  

### Narrative  
Verifies the existence of sensitive data.

### Success Criterion  
`sensitive_data` exists and is explicit.

### Failure Criterion  
Missing or undefined `sensitive_data`.

### Expected Result Type  
Boolean

### Associated Test  
- [Sensitive data for reused datasets](tests.md#test-sensitive-data-for-reused-datasets)

---

## Metric: Reused Data URL

**Metric ID:** data.reused.co.8  

### Narrative  
Verifies that the reused data have URL.

### Success Criterion  
At least one distribution contains `access_url`.

### Failure Criterion  
No distribution URL.

### Expected Result Type  
Boolean

### Associated Tests  
- [Distribution present (URL)](tests.md#test-distribution-present-url)  
- [Access URL](tests.md#test-access-url)

---

## Metric: Repository Reused Data PID

**Metric ID:** data.reused.feas.1  

### Narrative  
Validates that the reused dataset exists in the repository.

### Success Criterion  
Identifier matches repository record AND PID resolves.

### Failure Criterion  
Mismatch or non-resolving PID.

### Expected Result Type  
Boolean

### Associated Tests  
- [PID matches destination repository record](tests.md#test-pid-matches-destination-repository-record)  
- [PID resolves](tests.md#test-pid-resolves)

---

## Metric: Repository Reused Data Access

**Metric ID:** data.reused.feas.2  

### Narrative  
Validates that access rights match destination.

### Associated Test  
- [Reused data access matches destination](tests.md#test-reused-data-access-matches-destination)

---

## Metric: Repository Reused Data License

**Metric ID:** data.reused.feas.3  

### Narrative  
Validates that license matches destination.

### Associated Test  
- [Reused data license matches destination](tests.md#test-reused-data-license-matches-destination)
