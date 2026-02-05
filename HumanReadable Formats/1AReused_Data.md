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
