# Metrics Catalog

| Metric ID | Title | Jump to Metric |
|----------|-------|---------------|
| madmp-reused-datasets-declared | maDMP declares reused datasets | [Go](#metric-madmp-declares-reused-datasets) |
| data.reused.co.2 | Reused Data PID | [Go](#metric-reused-data-pid) |
| data.reused.co.3 | Reused Data License | [Go](#metric-reused-data-license) |
| data.reused.co.4 | Reused Data Source | [Go](#metric-reused-data-source) |
| data.reused.co.5 | Reused Data Access | [Go](#metric-reused-data-access) |
| data.reused.co.6 | Reused Data Personal | [Go](#metric-reused-data-personal) |
| data.reused.co.7 | Reused Data Sensitive | [Go](#metric-reused-data-sensitive) |
| data.reused.co.8 | Reused Data URL | [Go](#metric-reused-data-url) |
| data.reused.feas.1 | Repository Reused Data PID | [Go](#metric-repository-reused-data-pid) |
| data.reused.feas.2 | Repository Reused Data Access | [Go](#metric-repository-reused-data-access) |
| data.reused.feas.2 | Repository Reused Data Access | [Go](#metric-repository-reused-data-access) |
| data.reused.feas.3 | Repository Reused Data License | [Go](#metric-repository-reused-data-license) |






# Metric: maDMP declares reused datasets

**Metric ID:** madmp-reused-datasets-declared  
**Persistent URI:** https://example.org/metric/madmp-reused-datasets-declared  

## Title
maDMP declares reused datasets

## Narrative
The machine-actionable Data Management Plan (maDMP) declares whether any dataset described in the plan is reused.

## Intended Outcome
Determine whether reuse of datasets is explicitly declared in the maDMP.

## Applies To
Machine-actionable Data Management Plan (maDMP) in JSON format.

## Success Criterion
At least one dataset entry in the maDMP contains a boolean field indicating reuse.

## Failure Criterion
No dataset entry contains reuse information.

## Expected Result Type
Boolean (pass/fail)

---

# Associated Test

## Test: Check for reused dataset declaration

**Test ID:** madmp-reused-datasets-declared-json  
**Persistent URI:** https://example.org/test/madmp-reused-datasets-declared-json  

### Description
Given a maDMP JSON document, inspect dataset objects and verify the presence of a field indicating whether the dataset is reused.

### Input
maDMP JSON

### Output
pass/fail

### Algorithm (Suggested)
1. Parse the maDMP JSON document.  
2. Locate dataset entries.  
3. Check whether at least one dataset contains `is_reused`.  
4. If present, return pass; otherwise return fail.


# Metric: Reused Data License

**Metric ID:** data.reused.co.3  
**Persistent URI:** https://example.org/metric/data.reused.co.3  
**Dimension:** Completeness  

## Title
Reused Data License

## Narrative
Verifies that reused datasets come with license.

## Intended Outcome
Determine whether reused datasets declared in the machine-actionable Data Management Plan (maDMP) include license information.

## Applies To
Machine-actionable Data Management Plan (maDMP) in JSON format.

## Success Criterion
For each dataset declared as reused (`is_reused = true`), license metadata is present, including at least a license reference and, where applicable, a start date.

## Failure Criterion
At least one reused dataset is missing license information or required license fields.

## Expected Result Type
Boolean (pass/fail)

---

# Associated Test

## Test: License for reused datasets

**Test ID:** T-DCSC  
**Persistent URI:** https://example.org/test/T-DCSC-license  

### Description
Check if `is_reused` includes license (ref and start_date).

### Input
maDMP JSON

### Output
pass/fail

### Algorithm (Suggested)
1. Parse the maDMP JSON document.  
2. Locate all dataset entries.  
3. Select datasets where `is_reused = true`.  
4. Verify that a `license` object exists.  
5. Verify that `license.ref` exists and is non-empty.  
6. Optionally verify that `license.start_date` exists.  
7. If all reused datasets comply, return pass; otherwise return fail.




# Metric: Reused Data PID

**Metric ID:** data.reused.co.2  
**Persistent URI:** https://example.org/metric/data.reused.co.2  
**Dimension:** Completeness  

## Title
Reused Data PID

## Narrative
Verifies that reused datasets come with PIDs.

## Intended Outcome
Determine whether reused datasets declared in the machine-actionable Data Management Plan (maDMP) include persistent identifiers.

## Applies To
Machine-actionable Data Management Plan (maDMP) in JSON format.

## Success Criterion
For each dataset declared as reused (`is_reused = true`), an identifier is present (e.g., `dataset_id.identifier`) and, where applicable, an identifier `type` is provided.

## Failure Criterion
At least one reused dataset is missing an identifier or identifier metadata.

## Expected Result Type
Boolean (pass/fail)

---

# Associated Test

## Test: Check for reused dataset PID

**Test ID:** T-DCSC  
**Persistent URI:** https://example.org/test/T-DCSC  

### Description
Check if `is_reused` includes `dataset_id` (identifier, type).

### Input
maDMP JSON

### Output
pass/fail

### Algorithm (Suggested)
1. Parse the maDMP JSON document.  
2. Locate all dataset entries.  
3. Select datasets where `is_reused = true`.  
4. Verify that `dataset_id.identifier` exists and is non-empty.  
5. Optionally verify that `dataset_id.type` exists.  
6. If all reused datasets comply, return pass; otherwise return fail.  
7. If no reused datasets exist, return not applicable (optional policy).



# Metric: Reused Data Source

**Metric ID:** data.reused.co.4  
**Persistent URI:** https://example.org/metric/data.reused.co.4  
**Dimension:** Completeness  

## Title
Reused Data Source

## Narrative
Verifies that reused datasets are shared.

## Intended Outcome
Determine whether reused datasets declared in the machine-actionable Data Management Plan (maDMP) include accessible source or distribution information.

## Applies To
Machine-actionable Data Management Plan (maDMP) in JSON format.

## Success Criterion
For each dataset declared as reused (`is_reused = true`), distribution or source metadata is present and contains minimally identifying information such as a title and/or an access location.

## Failure Criterion
At least one reused dataset lacks distribution or source metadata, or required minimal fields.

## Expected Result Type
Boolean (pass/fail)

---

# Associated Tests

## Test: Distribution Present

**Test ID:** T-DCSC  
**Persistent URI:** https://example.org/test/T-DCSC-distribution-present  

### Description
Checks the distribution.

### Input
maDMP JSON

### Output
pass/fail

### Algorithm (Suggested)
1. Parse the maDMP JSON document.  
2. Locate all dataset entries.  
3. Select datasets where `is_reused = true`.  
4. Verify that a `distribution` (or equivalent) object or array exists.  
5. If all reused datasets contain distribution metadata, return pass; otherwise return fail.

---

## Test: Distribution Access Information

**Test ID:** T-DCSC  
**Persistent URI:** https://example.org/test/T-DCSC-distribution-access  

### Description
Checks whether distribution includes access information (e.g., access URL or download URL).

### Input
maDMP JSON

### Output
pass/fail

### Algorithm (Suggested)
1. Parse the maDMP JSON document.  
2. Locate reused datasets (`is_reused = true`).  
3. For each distribution, verify that at least one access field exists (e.g., `access_url`, `download_url`, or equivalent).  
4. If all reused datasets contain access information, return pass; otherwise return fail.

---

## Test: Distribution Title

**Test ID:** T-DCSC  
**Persistent URI:** https://example.org/test/T-DCSC-distribution-title  

### Description
Checks if there is title of distribution.

### Input
maDMP JSON

### Output
pass/fail

### Algorithm (Suggested)
1. Parse the maDMP JSON document.  
2. Locate reused datasets (`is_reused = true`).  
3. For each distribution, verify that a non-empty `title` field exists.  
4. If all reused datasets contain a title, return pass; otherwise return fail.

# Metric: Reused Data Access

**Metric ID:** data.reused.co.5  
**Persistent URI:** https://example.org/metric/data.reused.co.5  
**Dimension:** Completeness  

## Title
Reused Data Access

## Narrative
Verifies the access rights of the reused datasets.

## Intended Outcome
Determine whether reused datasets declared in the machine-actionable Data Management Plan (maDMP) include an explicit access rights statement.

## Applies To
Machine-actionable Data Management Plan (maDMP) in JSON format.

## Success Criterion
For each dataset declared as reused (`is_reused = true`), a `data_access` value is present and has an allowed value (open, shared, or closed).

## Failure Criterion
At least one reused dataset is missing a `data_access` value or contains an invalid value.

## Expected Result Type
Boolean (pass/fail)

---

# Associated Test

## Test: Access rights for reused datasets

**Test ID:** T-DCSC  
**Persistent URI:** https://example.org/test/T-DCSC-access  

### Description
Checks the data_access (open, shared, closed).

### Input
maDMP JSON

### Output
pass/fail

### Algorithm (Suggested)
1. Parse the maDMP JSON document.  
2. Locate all dataset entries.  
3. Select datasets where `is_reused = true`.  
4. Verify that `data_access` exists.  
5. Verify that its value is one of: `open`, `shared`, `closed`.  
6. If all reused datasets comply, return pass; otherwise return fail.

# Metric: Reused Data Personal

**Metric ID:** data.reused.co.6  
**Persistent URI:** https://example.org/metric/data.reused.co.6  
**Dimension:** Completeness  

## Title
Reused Data Personal

## Narrative
Verifies the existence of personal data.

## Intended Outcome
Determine whether reused datasets declared in the machine-actionable Data Management Plan (maDMP) include an explicit statement about the presence of personal data.

## Applies To
Machine-actionable Data Management Plan (maDMP) in JSON format.

## Success Criterion
For each dataset declared as reused (`is_reused = true`), a `personal_data` field exists and is explicitly set (e.g., boolean or controlled value).

## Failure Criterion
At least one reused dataset is missing `personal_data` information or contains an invalid or undefined value.

## Expected Result Type
Boolean (pass/fail)

---

# Associated Test

## Test: Personal data for reused datasets

**Test ID:** T-DCSC  
**Persistent URI:** https://example.org/test/T-DCSC-personal-data  

### Description
Checks the personal_data.

### Input
maDMP JSON

### Output
pass/fail

### Algorithm (Suggested)
1. Parse the maDMP JSON document.  
2. Locate all dataset entries.  
3. Select datasets where `is_reused = true`.  
4. Verify that `personal_data` exists.  
5. Verify that its value is explicit and valid (e.g., `true/false`, or a controlled term your schema allows).  
6. If all reused datasets comply, return pass; otherwise return fail.

# Metric: Reused Data Sensitive

**Metric ID:** data.reused.co.7  
**Persistent URI:** https://example.org/metric/data.reused.co.7  
**Dimension:** Completeness  

## Title
Reused Data Sensitive

## Narrative
Verifies the existence of sensitive data.

## Intended Outcome
Determine whether reused datasets declared in the machine-actionable Data Management Plan (maDMP) include an explicit statement about the presence of sensitive data.

## Applies To
Machine-actionable Data Management Plan (maDMP) in JSON format.

## Success Criterion
For each dataset declared as reused (`is_reused = true`), a `sensitive_data` field exists and is explicitly set (e.g., boolean or controlled value).

## Failure Criterion
At least one reused dataset is missing `sensitive_data` information or contains an invalid or undefined value.

## Expected Result Type
Boolean (pass/fail)

---

# Associated Test

## Test: Sensitive data for reused datasets

**Test ID:** T-DCSC  
**Persistent URI:** https://example.org/test/T-DCSC-sensitive-data  

### Description
Checks the sensitive_data.

### Input
maDMP JSON

### Output
pass/fail

### Algorithm (Suggested)
1. Parse the maDMP JSON document.  
2. Locate all dataset entries.  
3. Select datasets where `is_reused = true`.  
4. Verify that `sensitive_data` exists.  
5. Verify that its value is explicit and valid.  
6. If all reused datasets comply, return pass; otherwise return fail.

# Metric: Reused Data URL

**Metric ID:** data.reused.co.8  
**Persistent URI:** https://example.org/metric/data.reused.co.8  
**Dimension:** Completeness  

## Title
Reused Data URL

## Narrative
Verifies that the reused data have URL.

## Intended Outcome
Determine whether reused datasets declared in the machine-actionable Data Management Plan (maDMP) include a URL pointing to their distribution or access location.

## Applies To
Machine-actionable Data Management Plan (maDMP) in JSON format.

## Success Criterion
For each dataset declared as reused (`is_reused = true`), at least one distribution includes a non-empty `access_url` (or equivalent URL field).

## Failure Criterion
At least one reused dataset lacks a distribution URL.

## Expected Result Type
Boolean (pass/fail)

---

# Associated Tests

## Test: Distribution present

**Test ID:** T-DCSC  
**Persistent URI:** https://example.org/test/T-DCSC-distribution-url-present  

### Description
Checks the distribution.

### Input
maDMP JSON

### Output
pass/fail

### Algorithm (Suggested)
1. Parse the maDMP JSON document.  
2. Locate reused datasets (`is_reused = true`).  
3. Verify that at least one distribution object exists.  
4. If yes, return pass; otherwise return fail.

---

## Test: Access URL

**Test ID:** T-DCSC  
**Persistent URI:** https://example.org/test/T-DCSC-access-url  

### Description
Checks the access_url.

### Input
maDMP JSON

### Output
pass/fail

### Algorithm (Suggested)
1. Parse the maDMP JSON document.  
2. Locate reused datasets (`is_reused = true`).  
3. Verify that at least one distribution contains `access_url`.  
4. If yes, return pass; otherwise return fail.

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

---

### Associated Tests

#### Test: PID matches destination repository record

**Test ID:** T-DCSC  
**Persistent URI:** https://example.org/test/T-DCSC-repo-match  

**Description**  
Checks if reused dataset id in DMP matches the destination.

**Input**  
- dataset_id in maDMP  
- repository identifier field(s) (e.g., DOI URL)

**Output**  
pass/fail

**Algorithm (Suggested)**  
1. Extract reused dataset identifiers from maDMP (`is_reused = true`).  
2. Query the target repository using the identifier.  
3. Retrieve the repository’s canonical identifier for the record.  
4. Compare with the maDMP dataset identifier.  
5. Pass if all identifiers match a repository record; otherwise fail.

---

#### Test: PID resolves

**Test ID:** T-DCSC  
**Persistent URI:** https://example.org/test/T-DCSC-pid-resolves  

**Description**  
Checks if the PID resolves.

**Input**  
- dataset_id from maDMP  
- PID resolver

**Output**  
pass/fail

**Algorithm (Suggested)**  
1. Extract reused dataset identifiers from maDMP (`is_reused = true`).  
2. Attempt resolution via the resolver (HTTP request).  
3. Treat successful HTTP responses (2xx/3xx) as resolvable.  
4. Pass if all PIDs resolve; otherwise fail.

## Metric: Repository Reused Data Access

**Metric ID:** data.reused.feas.2  
**Persistent URI:** https://example.org/metric/data.reused.feas.2  
**Dimension:** Feasibility  

### Title
Repository Reused Data Access

### Narrative
Validates that the access rights of the reused dataset match those of the destination.

### Intended Outcome
Determine whether the access rights declared for reused datasets in the machine-actionable Data Management Plan (maDMP) match the access rights recorded in the destination repository.

### Applies To
- maDMP JSON (dataset reuse declarations)  
- Target repository endpoint  

### Success Criterion
For each dataset declared as reused (`is_reused = true`), the `data_access` value in the maDMP matches the corresponding access rights value in the destination repository record (e.g., `access_right`).

### Failure Criterion
At least one reused dataset has a `data_access` value in the maDMP that does not match the access rights recorded in the destination repository.

### Expected Result Type
Boolean (pass/fail)

---

### Associated Test

#### Test: Reused data access matches destination

**Test ID:** T-DCSC  
**Persistent URI:** https://example.org/test/T-DCSC-access-match  

**Description**  
Check if reused data access in DMP matches the destination.

**Input**  
- `data_access` in maDMP  
- `access_right` in destination repository (e.g., Zenodo)

**Output**  
pass/fail

**Algorithm (Suggested)**  
1. Extract reused datasets from maDMP (`is_reused = true`).  
2. For each reused dataset, retrieve its record from the destination repository.  
3. Extract the repository access rights value.  
4. Compare maDMP `data_access` with repository `access_right`.  
5. Pass if all values match; otherwise fail.



## Metric: Repository Reused Data License

**Metric ID:** data.reused.feas.3  
**Persistent URI:** https://example.org/metric/data.reused.feas.3  
**Dimension:** Feasibility  

### Title
Repository Reused Data License

### Narrative
Validates that license of the reused dataset match those of the destination.

### Intended Outcome
Determine whether the license declared for reused datasets in the machine-actionable Data Management Plan (maDMP) matches the license recorded in the destination repository.

### Applies To
- maDMP JSON (dataset reuse declarations)  
- Target repository endpoint  

### Success Criterion
For each dataset declared as reused (`is_reused = true`), the license value in the maDMP matches the license value in the destination repository record.

### Failure Criterion
At least one reused dataset has a license value in the maDMP that does not match the license recorded in the destination repository.

### Expected Result Type
Boolean (pass/fail)

---

### Associated Test

#### Test: Reused data license matches destination

**Test ID:** T-DCSC  
**Persistent URI:** https://example.org/test/T-DCSC-license-match  

**Description**  
Checks if the license of the repository is the one mentioned in the DMP.

**Input**  
- license in maDMP JSON  
- license in destination repository (e.g., Zenodo)

**Output**  
pass/fail

**Algorithm (Suggested)**  
1. Extract reused datasets from maDMP (`is_reused = true`).  
2. For each reused dataset, retrieve its record from the destination repository.  
3. Extract license value from repository record.  
4. Compare with maDMP license value.  
5. Pass if all values match; otherwise fail.
