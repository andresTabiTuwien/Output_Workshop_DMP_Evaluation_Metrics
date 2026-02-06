# Metrics Catalog

| Metric ID | Title | 
|----------|------|
| data.reused.co.1 | [maDMP declares reused datasets](#metric-madmp-declares-reused-datasets) |
| data.reused.co.2 | [Reused Data PID](#metric-reused-data-pid) |
| data.reused.co.3 | [Reused Data License](#metric-reused-data-license) |
| data.reused.co.4 | [Reused Data Source](#metric-reused-data-source) |
| data.reused.co.5 | [Reused Data Access](#metric-reused-data-access) |
| data.reused.co.6 | [Reused Data Personal](#metric-reused-data-personal) |
| data.reused.co.7 | [Reused Data Sensitive](#metric-reused-data-sensitive) |
| data.reused.co.8 | [Reused Data URL](#metric-reused-data-url) |
| data.reused.feas.1 | [Repository Reused Data PID](#metric-repository-reused-data-pid) |
| data.reused.feas.2 | [Repository Reused Data Access](#metric-repository-reused-data-access) |
| data.reused.feas.3 | [Repository Reused Data License](#metric-repository-reused-data-license) |

---

## Metric: maDMP declares reused datasets

**Metric ID:** data.reused.co.1  
**Persistent URI:** https://example.org/metric/madmp-reused-datasets-declared  

### Title
maDMP declares reused datasets

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

### Associated Test(s)
- [Check for reused dataset declaration](tests.md#test-check-for-reused-dataset-declaration)

### JSON-LD (Metric)
```json
{
  "@context": {
    "dqv": "http://www.w3.org/ns/dqv#",
    "dcterms": "http://purl.org/dc/terms/",
    "ftr": "https://w3id.org/ftr#"
  },
  "@id": "https://example.org/metric/madmp-reused-datasets-declared",
  "@type": "dqv:Metric",
  "dcterms:identifier": "data.reused.co.1",
  "dcterms:title": "maDMP declares reused datasets",
  "dcterms:description": "The machine-actionable Data Management Plan (maDMP) declares whether any dataset described in the plan is reused.",
  "ftr:intendedOutcome": "Determine whether reuse of datasets is explicitly declared in the maDMP.",
  "ftr:successCriterion": "At least one dataset entry in the maDMP contains a boolean field indicating reuse.",
  "ftr:failureCriterion": "No dataset entry contains reuse information.",
  "ftr:appliesTo": "Machine-actionable Data Management Plan (maDMP) in JSON format.",
  "ftr:expectedResultType": "boolean"
}
```

---

## Metric: Reused Data PID

**Metric ID:** data.reused.co.2  
**Persistent URI:** https://example.org/metric/data.reused.co.2  
**Dimension:** Completeness  

### Title
Reused Data PID

### Narrative
Verifies that reused datasets come with PIDs.

### Intended Outcome
Determine whether reused datasets declared in the machine-actionable Data Management Plan (maDMP) include persistent identifiers.

### Applies To
Machine-actionable Data Management Plan (maDMP) in JSON format.

### Success Criterion
For each dataset declared as reused (`is_reused = true`), an identifier is present (e.g., `dataset_id.identifier`) and, where applicable, an identifier `type` is provided.

### Failure Criterion
At least one reused dataset is missing an identifier or identifier metadata.

### Expected Result Type
Boolean (pass/fail)

### Associated Test(s)
- [Check for reused dataset PID](tests.md#test-check-for-reused-dataset-pid)

### JSON-LD (Metric)
```json
{
  "@context": {
    "dqv": "http://www.w3.org/ns/dqv#",
    "dcterms": "http://purl.org/dc/terms/",
    "ftr": "https://w3id.org/ftr#"
  },
  "@id": "https://example.org/metric/data.reused.co.2",
  "@type": "dqv:Metric",
  "dcterms:identifier": "data.reused.co.2",
  "dcterms:title": "Reused Data PID",
  "dcterms:description": "Verifies that reused datasets come with PIDs.",
  "ftr:dimension": "Completeness",
  "ftr:intendedOutcome": "Determine whether reused datasets declared in the maDMP include persistent identifiers.",
  "ftr:successCriterion": "For each dataset declared as reused (is_reused=true), an identifier is present (e.g., dataset_id.identifier) and, where applicable, an identifier type is provided.",
  "ftr:failureCriterion": "At least one reused dataset is missing an identifier or identifier metadata.",
  "ftr:appliesTo": "Machine-actionable Data Management Plan (maDMP) in JSON format.",
  "ftr:expectedResultType": "boolean"
}
```

---

## Metric: Reused Data License

**Metric ID:** data.reused.co.3  
**Persistent URI:** https://example.org/metric/data.reused.co.3  
**Dimension:** Completeness  

### Title
Reused Data License

### Narrative
Verifies that reused datasets come with license.

### Intended Outcome
Determine whether reused datasets declared in the machine-actionable Data Management Plan (maDMP) include license information.

### Applies To
Machine-actionable Data Management Plan (maDMP) in JSON format.

### Success Criterion
For each dataset declared as reused (`is_reused = true`), license metadata is present, including at least a license reference and, where applicable, a start date.

### Failure Criterion
At least one reused dataset is missing license information or required license fields.

### Expected Result Type
Boolean (pass/fail)

### Associated Test(s)
- [License for reused datasets](tests.md#test-license-for-reused-datasets)

### JSON-LD (Metric)
```json
{
  "@context": {
    "dqv": "http://www.w3.org/ns/dqv#",
    "dcterms": "http://purl.org/dc/terms/",
    "ftr": "https://w3id.org/ftr#"
  },
  "@id": "https://example.org/metric/data.reused.co.3",
  "@type": "dqv:Metric",
  "dcterms:identifier": "data.reused.co.3",
  "dcterms:title": "Reused Data License",
  "dcterms:description": "Verifies that reused datasets come with license.",
  "ftr:dimension": "Completeness",
  "ftr:intendedOutcome": "Determine whether reused datasets declared in the maDMP include license information.",
  "ftr:successCriterion": "For each reused dataset (is_reused=true), license metadata is present, including at least a license reference and, where applicable, a start date.",
  "ftr:failureCriterion": "At least one reused dataset is missing license information or required license fields.",
  "ftr:appliesTo": "Machine-actionable Data Management Plan (maDMP) in JSON format.",
  "ftr:expectedResultType": "boolean"
}
```

---

## Metric: Reused Data Source

**Metric ID:** data.reused.co.4  
**Persistent URI:** https://example.org/metric/data.reused.co.4  
**Dimension:** Completeness  

### Title
Reused Data Source

### Narrative
Verifies that reused datasets are shared.

### Intended Outcome
Determine whether reused datasets declared in the machine-actionable Data Management Plan (maDMP) include accessible source or distribution information.

### Applies To
Machine-actionable Data Management Plan (maDMP) in JSON format.

### Success Criterion
For each dataset declared as reused (`is_reused = true`), distribution or source metadata is present and contains minimally identifying information such as a title and/or an access location.

### Failure Criterion
At least one reused dataset lacks distribution or source metadata, or required minimal fields.

### Expected Result Type
Boolean (pass/fail)

### Associated Test(s)
- [Distribution present](tests.md#test-distribution-present)  
- [Distribution access information](tests.md#test-distribution-access-information)  
- [Distribution title](tests.md#test-distribution-title)

### JSON-LD (Metric)
```json
{
  "@context": {
    "dqv": "http://www.w3.org/ns/dqv#",
    "dcterms": "http://purl.org/dc/terms/",
    "ftr": "https://w3id.org/ftr#"
  },
  "@id": "https://example.org/metric/data.reused.co.4",
  "@type": "dqv:Metric",
  "dcterms:identifier": "data.reused.co.4",
  "dcterms:title": "Reused Data Source",
  "dcterms:description": "Verifies that reused datasets are shared.",
  "ftr:dimension": "Completeness",
  "ftr:intendedOutcome": "Determine whether reused datasets declared in the maDMP include accessible source or distribution information.",
  "ftr:successCriterion": "For each reused dataset (is_reused=true), distribution or source metadata is present and contains minimally identifying information such as a title and/or an access location.",
  "ftr:failureCriterion": "At least one reused dataset lacks distribution or source metadata, or required minimal fields.",
  "ftr:appliesTo": "Machine-actionable Data Management Plan (maDMP) in JSON format.",
  "ftr:expectedResultType": "boolean"
}
```

---

## Metric: Reused Data Access

**Metric ID:** data.reused.co.5  
**Persistent URI:** https://example.org/metric/data.reused.co.5  
**Dimension:** Completeness  

### Title
Reused Data Access

### Narrative
Verifies the access rights of the reused datasets.

### Intended Outcome
Determine whether reused datasets declared in the machine-actionable Data Management Plan (maDMP) include an explicit access rights statement.

### Applies To
Machine-actionable Data Management Plan (maDMP) in JSON format.

### Success Criterion
For each dataset declared as reused (`is_reused = true`), a `data_access` value is present and has an allowed value (open, shared, or closed).

### Failure Criterion
At least one reused dataset is missing a `data_access` value or contains an invalid value.

### Expected Result Type
Boolean (pass/fail)

### Associated Test(s)
- [Access rights for reused datasets](tests.md#test-access-rights-for-reused-datasets)

### JSON-LD (Metric)
```json
{
  "@context": {
    "dqv": "http://www.w3.org/ns/dqv#",
    "dcterms": "http://purl.org/dc/terms/",
    "ftr": "https://w3id.org/ftr#"
  },
  "@id": "https://example.org/metric/data.reused.co.5",
  "@type": "dqv:Metric",
  "dcterms:identifier": "data.reused.co.5",
  "dcterms:title": "Reused Data Access",
  "dcterms:description": "Verifies the access rights of the reused datasets.",
  "ftr:dimension": "Completeness",
  "ftr:intendedOutcome": "Determine whether reused datasets declared in the maDMP include an explicit access rights statement.",
  "ftr:successCriterion": "For each reused dataset (is_reused=true), a data_access value is present and has an allowed value (open, shared, or closed).",
  "ftr:failureCriterion": "At least one reused dataset is missing a data_access value or contains an invalid value.",
  "ftr:appliesTo": "Machine-actionable Data Management Plan (maDMP) in JSON format.",
  "ftr:expectedResultType": "boolean"
}
```

---

## Metric: Reused Data Personal

**Metric ID:** data.reused.co.6  
**Persistent URI:** https://example.org/metric/data.reused.co.6  
**Dimension:** Completeness  

### Title
Reused Data Personal

### Narrative
Verifies the existence of personal data.

### Intended Outcome
Determine whether reused datasets declared in the machine-actionable Data Management Plan (maDMP) include an explicit statement about the presence of personal data.

### Applies To
Machine-actionable Data Management Plan (maDMP) in JSON format.

### Success Criterion
For each dataset declared as reused (`is_reused = true`), a `personal_data` field exists and is explicitly set (e.g., boolean or controlled value).

### Failure Criterion
At least one reused dataset is missing `personal_data` information or contains an invalid or undefined value.

### Expected Result Type
Boolean (pass/fail)

### Associated Test(s)
- [Personal data for reused datasets](tests.md#test-personal-data-for-reused-datasets)

### JSON-LD (Metric)
```json
{
  "@context": {
    "dqv": "http://www.w3.org/ns/dqv#",
    "dcterms": "http://purl.org/dc/terms/",
    "ftr": "https://w3id.org/ftr#"
  },
  "@id": "https://example.org/metric/data.reused.co.6",
  "@type": "dqv:Metric",
  "dcterms:identifier": "data.reused.co.6",
  "dcterms:title": "Reused Data Personal",
  "dcterms:description": "Verifies the existence of personal data.",
  "ftr:dimension": "Completeness",
  "ftr:intendedOutcome": "Determine whether reused datasets declared in the maDMP include an explicit statement about the presence of personal data.",
  "ftr:successCriterion": "For each reused dataset (is_reused=true), a personal_data field exists and is explicitly set (e.g., boolean or controlled value).",
  "ftr:failureCriterion": "At least one reused dataset is missing personal_data information or contains an invalid or undefined value.",
  "ftr:appliesTo": "Machine-actionable Data Management Plan (maDMP) in JSON format.",
  "ftr:expectedResultType": "boolean"
}
```

---

## Metric: Reused Data Sensitive

**Metric ID:** data.reused.co.7  
**Persistent URI:** https://example.org/metric/data.reused.co.7  
**Dimension:** Completeness  

### Title
Reused Data Sensitive

### Narrative
Verifies the existence of sensitive data.

### Intended Outcome
Determine whether reused datasets declared in the machine-actionable Data Management Plan (maDMP) include an explicit statement about the presence of sensitive data.

### Applies To
Machine-actionable Data Management Plan (maDMP) in JSON format.

### Success Criterion
For each dataset declared as reused (`is_reused = true`), a `sensitive_data` field exists and is explicitly set (e.g., boolean or controlled value).

### Failure Criterion
At least one reused dataset is missing `sensitive_data` information or contains an invalid or undefined value.

### Expected Result Type
Boolean (pass/fail)

### Associated Test(s)
- [Sensitive data for reused datasets](tests.md#test-sensitive-data-for-reused-datasets)

### JSON-LD (Metric)
```json
{
  "@context": {
    "dqv": "http://www.w3.org/ns/dqv#",
    "dcterms": "http://purl.org/dc/terms/",
    "ftr": "https://w3id.org/ftr#"
  },
  "@id": "https://example.org/metric/data.reused.co.7",
  "@type": "dqv:Metric",
  "dcterms:identifier": "data.reused.co.7",
  "dcterms:title": "Reused Data Sensitive",
  "dcterms:description": "Verifies the existence of sensitive data.",
  "ftr:dimension": "Completeness",
  "ftr:intendedOutcome": "Determine whether reused datasets declared in the maDMP include an explicit statement about the presence of sensitive data.",
  "ftr:successCriterion": "For each reused dataset (is_reused=true), a sensitive_data field exists and is explicitly set (e.g., boolean or controlled value).",
  "ftr:failureCriterion": "At least one reused dataset is missing sensitive_data information or contains an invalid or undefined value.",
  "ftr:appliesTo": "Machine-actionable Data Management Plan (maDMP) in JSON format.",
  "ftr:expectedResultType": "boolean"
}
```

---

## Metric: Reused Data URL

**Metric ID:** data.reused.co.8  
**Persistent URI:** https://example.org/metric/data.reused.co.8  
**Dimension:** Completeness  

### Title
Reused Data URL

### Narrative
Verifies that the reused data have URL.

### Intended Outcome
Determine whether reused datasets declared in the machine-actionable Data Management Plan (maDMP) include a URL pointing to their distribution or access location.

### Applies To
Machine-actionable Data Management Plan (maDMP) in JSON format.

### Success Criterion
For each dataset declared as reused (`is_reused = true`), at least one distribution includes a non-empty `access_url` (or equivalent URL field).

### Failure Criterion
At least one reused dataset lacks a distribution URL.

### Expected Result Type
Boolean (pass/fail)

### Associated Test(s)
- [Distribution present (URL)](tests.md#test-distribution-present-url)  
- [Access URL](tests.md#test-access-url)

### JSON-LD (Metric)
```json
{
  "@context": {
    "dqv": "http://www.w3.org/ns/dqv#",
    "dcterms": "http://purl.org/dc/terms/",
    "ftr": "https://w3id.org/ftr#"
  },
  "@id": "https://example.org/metric/data.reused.co.8",
  "@type": "dqv:Metric",
  "dcterms:identifier": "data.reused.co.8",
  "dcterms:title": "Reused Data URL",
  "dcterms:description": "Verifies that the reused data have URL.",
  "ftr:dimension": "Completeness",
  "ftr:intendedOutcome": "Determine whether reused datasets declared in the maDMP include a URL pointing to their distribution or access location.",
  "ftr:successCriterion": "For each reused dataset (is_reused=true), at least one distribution includes a non-empty access_url (or equivalent URL field).",
  "ftr:failureCriterion": "At least one reused dataset lacks a distribution URL.",
  "ftr:appliesTo": "Machine-actionable Data Management Plan (maDMP) in JSON format.",
  "ftr:expectedResultType": "boolean"
}
```

---

## Metric: Repository Reused Data PID

**Metric ID:** data.reused.feas.1  
**Persistent URI:** https://example.org/metric/data.reused.feas.1  
**Dimension:** Feasibility  

### Title
Repository Reused Data PID

### Narrative
Validates that the reused dataset exists in the repository.

### Intended Outcome
Determine whether the PID for each reused dataset declared in the machine-actionable Data Management Plan (maDMP) corresponds to an existing record in a target repository and resolves via a PID resolver.

### Applies To
- maDMP JSON (dataset reuse declarations)  
- Target repository endpoint  
- PID resolver service  

### Success Criterion
For each dataset declared as reused (`is_reused = true`):
1. The dataset identifier in the maDMP matches an identifier discoverable in the target repository record (e.g., DOI URL), **and**  
2. The dataset PID resolves successfully.

### Failure Criterion
At least one reused dataset PID:
- cannot be matched to a target repository record, **or**  
- does not resolve via a PID resolver.

### Expected Result Type
Boolean (pass/fail)

### Associated Test(s)
- [PID matches destination repository record](tests.md#test-pid-matches-destination-repository-record)  
- [PID resolves](tests.md#test-pid-resolves)

### JSON-LD (Metric)
```json
{
  "@context": {
    "dqv": "http://www.w3.org/ns/dqv#",
    "dcterms": "http://purl.org/dc/terms/",
    "ftr": "https://w3id.org/ftr#"
  },
  "@id": "https://example.org/metric/data.reused.feas.1",
  "@type": "dqv:Metric",
  "dcterms:identifier": "data.reused.feas.1",
  "dcterms:title": "Repository Reused Data PID",
  "dcterms:description": "Validates that the reused dataset exists in the repository.",
  "ftr:dimension": "Feasibility",
  "ftr:intendedOutcome": "Determine whether the PID for each reused dataset declared in the maDMP corresponds to an existing record in a target repository and resolves via a PID resolver.",
  "ftr:successCriterion": "For each reused dataset (is_reused=true): (1) the maDMP dataset identifier matches an identifier discoverable in the target repository record, and (2) the PID resolves successfully.",
  "ftr:failureCriterion": "At least one reused dataset PID cannot be matched to a target repository record or does not resolve via a PID resolver.",
  "ftr:appliesTo": "maDMP JSON + target repository endpoint + PID resolver service",
  "ftr:expectedResultType": "boolean"
}
```

---

## Metric: Repository Reused Data Access

**Metric ID:** data.reused.feas.2  
**Persistent URI:** https://example.org/metric/data.reused.feas.2  
**Dimension:** Feasibility  

### Title
Repository Reused Data Access

### Narrative
Validates that the access rights of the reused dataset match those of the destination.

### Intended Outcome
Determine whether the access rights declared for reused datasets in the maDMP match the access rights recorded in the destination repository.

### Applies To
- maDMP JSON (dataset reuse declarations)  
- Target repository endpoint  

### Success Criterion
For each dataset declared as reused (`is_reused = true`), the `data_access` value in the maDMP matches the corresponding access rights value in the destination repository record (e.g., `access_right`).

### Failure Criterion
At least one reused dataset has a `data_access` value in the maDMP that does not match the access rights recorded in the destination repository.

### Expected Result Type
Boolean (pass/fail)

### Associated Test(s)
- [Reused data access matches destination](tests.md#test-reused-data-access-matches-destination)

### JSON-LD (Metric)
```json
{
  "@context": {
    "dqv": "http://www.w3.org/ns/dqv#",
    "dcterms": "http://purl.org/dc/terms/",
    "ftr": "https://w3id.org/ftr#"
  },
  "@id": "https://example.org/metric/data.reused.feas.2",
  "@type": "dqv:Metric",
  "dcterms:identifier": "data.reused.feas.2",
  "dcterms:title": "Repository Reused Data Access",
  "dcterms:description": "Validates that the access rights of the reused dataset match those of the destination.",
  "ftr:dimension": "Feasibility",
  "ftr:intendedOutcome": "Determine whether the access rights declared for reused datasets in the maDMP match the access rights recorded in the destination repository.",
  "ftr:successCriterion": "For each reused dataset (is_reused=true), the maDMP data_access value matches the access rights value recorded in the destination repository.",
  "ftr:failureCriterion": "At least one reused dataset has a data_access value in the maDMP that does not match the destination repository access rights.",
  "ftr:appliesTo": "maDMP JSON + target repository endpoint",
  "ftr:expectedResultType": "boolean"
}
```

---

## Metric: Repository Reused Data License

**Metric ID:** data.reused.feas.3  
**Persistent URI:** https://example.org/metric/data.reused.feas.3  
**Dimension:** Feasibility  

### Title
Repository Reused Data License

### Narrative
Validates that license of the reused dataset match those of the destination.

### Intended Outcome
Determine whether the license declared for reused datasets in the maDMP matches the license recorded in the destination repository.

### Applies To
- maDMP JSON (dataset reuse declarations)  
- Target repository endpoint  

### Success Criterion
For each dataset declared as reused (`is_reused = true`), the license value in the maDMP matches the license value in the destination repository record.

### Failure Criterion
At least one reused dataset has a license value in the maDMP that does not match the license recorded in the destination repository.

### Expected Result Type
Boolean (pass/fail)

### Associated Test(s)
- [Reused data license matches destination](tests.md#test-reused-data-license-matches-destination)

### JSON-LD (Metric)
```json
{
  "@context": {
    "dqv": "http://www.w3.org/ns/dqv#",
    "dcterms": "http://purl.org/dc/terms/",
    "ftr": "https://w3id.org/ftr#"
  },
  "@id": "https://example.org/metric/data.reused.feas.3",
  "@type": "dqv:Metric",
  "dcterms:identifier": "data.reused.feas.3",
  "dcterms:title": "Repository Reused Data License",
  "dcterms:description": "Validates that license of the reused dataset match those of the destination.",
  "ftr:dimension": "Feasibility",
  "ftr:intendedOutcome": "Determine whether the license declared for reused datasets in the maDMP matches the license recorded in the destination repository.",
  "ftr:successCriterion": "For each reused dataset (is_reused=true), the maDMP license value matches the license value in the destination repository record.",
  "ftr:failureCriterion": "At least one reused dataset has a license value in the maDMP that does not match the license recorded in the destination repository.",
  "ftr:appliesTo": "maDMP JSON + target repository endpoint",
  "ftr:expectedResultType": "boolean"
}
```
