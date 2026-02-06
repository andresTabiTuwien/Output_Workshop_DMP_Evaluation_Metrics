# Tests Catalog

| Test Name | Link |
|----------|------|
| Check for reused dataset declaration | [Go](#test-check-for-reused-dataset-declaration) |
| License for reused datasets | [Go](#test-license-for-reused-datasets) |
| Check for reused dataset PID | [Go](#test-check-for-reused-dataset-pid) |
| Distribution Present | [Go](#test-distribution-present) |
| Distribution Access Information | [Go](#test-distribution-access-information) |
| Distribution Title | [Go](#test-distribution-title) |
| Access rights for reused datasets | [Go](#test-access-rights-for-reused-datasets) |
| Personal data for reused datasets | [Go](#test-personal-data-for-reused-datasets) |
| Sensitive data for reused datasets | [Go](#test-sensitive-data-for-reused-datasets) |
| Distribution present | [Go](#test-distribution-present) |
| Access URL | [Go](#test-access-url) |
| PID matches destination repository record | [Go](#test-pid-matches-destination-repository-record) |
| PID resolves | [Go](#test-pid-resolves) |
| Reused data access matches destination | [Go](#test-reused-data-access-matches-destination) |
| Reused data license matches destination | [Go](#test-reused-data-license-matches-destination) |

---

## Test: Check for reused dataset declaration

**Test ID:** madmp-reused-datasets-declared-json  
**Persistent URI:** https://example.org/test/madmp-reused-datasets-declared-json  

**Implements:** [data.reused.co.1](metrics.md#metric-madmp-declares-reused-datasets)  

### Description
Given a maDMP JSON document, inspect dataset objects and verify the presence of a field indicating whether the dataset is reused.

### Input
maDMP JSON

### Output
pass/fail

### Procedure
1. Parse the maDMP JSON document.  
2. Locate dataset entries.  
3. Check whether at least one dataset contains `is_reused`.  
4. If present, return pass; otherwise return fail.

### JSON-LD (Test)
```json
{
  "@context": {
    "dcterms": "http://purl.org/dc/terms/",
    "ftr": "https://w3id.org/ftr#",
    "sio": "http://semanticscience.org/resource/"
  },
  "@id": "https://example.org/test/madmp-reused-datasets-declared-json",
  "@type": "ftr:Test",
  "dcterms:identifier": "madmp-reused-datasets-declared-json",
  "dcterms:title": "Check for reused dataset declaration",
  "dcterms:description": "Given a maDMP JSON document, inspect dataset objects and verify the presence of a field indicating whether the dataset is reused.",
  "ftr:input": "maDMP JSON",
  "ftr:output": "pass/fail",
  "sio:is-implementation-of": {
    "@id": "https://example.org/metric/madmp-reused-datasets-declared"
  }
}
```

---

## Test: License for reused datasets

**Test ID:** T-DCSC  
**Persistent URI:** https://example.org/test/T-DCSC-license  

**Implements:** [data.reused.co.3](metrics.md#metric-reused-data-license)  

### Description
Check if `is_reused` includes license (ref and start_date).

### Input
maDMP JSON

### Output
pass/fail

### Procedure
1. Parse the maDMP JSON document.  
2. Locate all dataset entries.  
3. Select datasets where `is_reused = true`.  
4. Verify that a `license` object exists.  
5. Verify that `license.ref` exists and is non-empty.  
6. Optionally verify that `license.start_date` exists.  
7. If all reused datasets comply, return pass; otherwise return fail.

### JSON-LD (Test)
```json
{
  "@context": {
    "dcterms": "http://purl.org/dc/terms/",
    "ftr": "https://w3id.org/ftr#",
    "sio": "http://semanticscience.org/resource/"
  },
  "@id": "https://example.org/test/T-DCSC-license",
  "@type": "ftr:Test",
  "dcterms:identifier": "T-DCSC",
  "dcterms:title": "License for reused datasets",
  "dcterms:description": "Check if `is_reused` includes license (ref and start_date).",
  "ftr:input": "maDMP JSON",
  "ftr:output": "pass/fail",
  "sio:is-implementation-of": {
    "@id": "https://example.org/metric/data.reused.co.3"
  }
}
```

---

## Test: Check for reused dataset PID

**Test ID:** T-DCSC  
**Persistent URI:** https://example.org/test/T-DCSC  

**Implements:** [data.reused.co.2](metrics.md#metric-reused-data-pid)  

### Description
Check if `is_reused` includes `dataset_id` (identifier, type).

### Input
maDMP JSON

### Output
pass/fail

### Procedure
1. Parse the maDMP JSON document.  
2. Locate all dataset entries.  
3. Select datasets where `is_reused = true`.  
4. Verify that `dataset_id.identifier` exists and is non-empty.  
5. Optionally verify that `dataset_id.type` exists.  
6. If all reused datasets comply, return pass; otherwise return fail.  
7. If no reused datasets exist, return not applicable (optional policy).

### JSON-LD (Test)
```json
{
  "@context": {
    "dcterms": "http://purl.org/dc/terms/",
    "ftr": "https://w3id.org/ftr#",
    "sio": "http://semanticscience.org/resource/"
  },
  "@id": "https://example.org/test/T-DCSC",
  "@type": "ftr:Test",
  "dcterms:identifier": "T-DCSC",
  "dcterms:title": "Check for reused dataset PID",
  "dcterms:description": "Check if `is_reused` includes `dataset_id` (identifier, type).",
  "ftr:input": "maDMP JSON",
  "ftr:output": "pass/fail",
  "sio:is-implementation-of": {
    "@id": "https://example.org/metric/data.reused.co.2"
  }
}
```

---

## Test: Distribution Present

**Test ID:** T-DCSC  
**Persistent URI:** https://example.org/test/T-DCSC-distribution-present  

**Implements:** [data.reused.co.4](metrics.md#metric-reused-data-source)  

### Description
Checks the distribution.

### Input
maDMP JSON

### Output
pass/fail

### Procedure
1. Parse the maDMP JSON document.  
2. Locate all dataset entries.  
3. Select datasets where `is_reused = true`.  
4. Verify that a `distribution` (or equivalent) object or array exists.  
5. If all reused datasets contain distribution metadata, return pass; otherwise return fail.

### JSON-LD (Test)
```json
{
  "@context": {
    "dcterms": "http://purl.org/dc/terms/",
    "ftr": "https://w3id.org/ftr#",
    "sio": "http://semanticscience.org/resource/"
  },
  "@id": "https://example.org/test/T-DCSC-distribution-present",
  "@type": "ftr:Test",
  "dcterms:identifier": "T-DCSC",
  "dcterms:title": "Distribution Present",
  "dcterms:description": "Checks the distribution.",
  "ftr:input": "maDMP JSON",
  "ftr:output": "pass/fail",
  "sio:is-implementation-of": {
    "@id": "https://example.org/metric/data.reused.co.4"
  }
}
```

---

## Test: Distribution Access Information

**Test ID:** T-DCSC  
**Persistent URI:** https://example.org/test/T-DCSC-distribution-access  

**Implements:** [data.reused.co.4](metrics.md#metric-reused-data-source)  

### Description
Checks whether distribution includes access information (e.g., access URL or download URL).

### Input
maDMP JSON

### Output
pass/fail

### Procedure
1. Parse the maDMP JSON document.  
2. Locate reused datasets (`is_reused = true`).  
3. For each distribution, verify that at least one access field exists (e.g., `access_url`, `download_url`, or equivalent).  
4. If all reused datasets contain access information, return pass; otherwise return fail.

### JSON-LD (Test)
```json
{
  "@context": {
    "dcterms": "http://purl.org/dc/terms/",
    "ftr": "https://w3id.org/ftr#",
    "sio": "http://semanticscience.org/resource/"
  },
  "@id": "https://example.org/test/T-DCSC-distribution-access",
  "@type": "ftr:Test",
  "dcterms:identifier": "T-DCSC",
  "dcterms:title": "Distribution Access Information",
  "dcterms:description": "Checks whether distribution includes access information (e.g., access URL or download URL).",
  "ftr:input": "maDMP JSON",
  "ftr:output": "pass/fail",
  "sio:is-implementation-of": {
    "@id": "https://example.org/metric/data.reused.co.4"
  }
}
```

---

## Test: Distribution Title

**Test ID:** T-DCSC  
**Persistent URI:** https://example.org/test/T-DCSC-distribution-title  

**Implements:** [data.reused.co.4](metrics.md#metric-reused-data-source)  

### Description
Checks if there is title of distribution.

### Input
maDMP JSON

### Output
pass/fail

### Procedure
1. Parse the maDMP JSON document.  
2. Locate reused datasets (`is_reused = true`).  
3. For each distribution, verify that a non-empty `title` field exists.  
4. If all reused datasets contain a title, return pass; otherwise return fail.

### JSON-LD (Test)
```json
{
  "@context": {
    "dcterms": "http://purl.org/dc/terms/",
    "ftr": "https://w3id.org/ftr#",
    "sio": "http://semanticscience.org/resource/"
  },
  "@id": "https://example.org/test/T-DCSC-distribution-title",
  "@type": "ftr:Test",
  "dcterms:identifier": "T-DCSC",
  "dcterms:title": "Distribution Title",
  "dcterms:description": "Checks if there is title of distribution.",
  "ftr:input": "maDMP JSON",
  "ftr:output": "pass/fail",
  "sio:is-implementation-of": {
    "@id": "https://example.org/metric/data.reused.co.4"
  }
}
```

---

## Test: Access rights for reused datasets

**Test ID:** T-DCSC  
**Persistent URI:** https://example.org/test/T-DCSC-access  

**Implements:** [data.reused.co.5](metrics.md#metric-reused-data-access)  

### Description
Checks the data_access (open, shared, closed).

### Input
maDMP JSON

### Output
pass/fail

### Procedure
1. Parse the maDMP JSON document.  
2. Locate all dataset entries.  
3. Select datasets where `is_reused = true`.  
4. Verify that `data_access` exists.  
5. Verify that its value is one of: `open`, `shared`, `closed`.  
6. If all reused datasets comply, return pass; otherwise return fail.

### JSON-LD (Test)
```json
{
  "@context": {
    "dcterms": "http://purl.org/dc/terms/",
    "ftr": "https://w3id.org/ftr#",
    "sio": "http://semanticscience.org/resource/"
  },
  "@id": "https://example.org/test/T-DCSC-access",
  "@type": "ftr:Test",
  "dcterms:identifier": "T-DCSC",
  "dcterms:title": "Access rights for reused datasets",
  "dcterms:description": "Checks the data_access (open, shared, closed).",
  "ftr:input": "maDMP JSON",
  "ftr:output": "pass/fail",
  "sio:is-implementation-of": {
    "@id": "https://example.org/metric/data.reused.co.5"
  }
}
```

---

## Test: Personal data for reused datasets

**Test ID:** T-DCSC  
**Persistent URI:** https://example.org/test/T-DCSC-personal-data  

**Implements:** [data.reused.co.6](metrics.md#metric-reused-data-personal)  

### Description
Checks the personal_data.

### Input
maDMP JSON

### Output
pass/fail

### Procedure
1. Parse the maDMP JSON document.  
2. Locate all dataset entries.  
3. Select datasets where `is_reused = true`.  
4. Verify that `personal_data` exists.  
5. Verify that its value is explicit and valid (e.g., `true/false`, or a controlled term your schema allows).  
6. If all reused datasets comply, return pass; otherwise return fail.

### JSON-LD (Test)
```json
{
  "@context": {
    "dcterms": "http://purl.org/dc/terms/",
    "ftr": "https://w3id.org/ftr#",
    "sio": "http://semanticscience.org/resource/"
  },
  "@id": "https://example.org/test/T-DCSC-personal-data",
  "@type": "ftr:Test",
  "dcterms:identifier": "T-DCSC",
  "dcterms:title": "Personal data for reused datasets",
  "dcterms:description": "Checks the personal_data.",
  "ftr:input": "maDMP JSON",
  "ftr:output": "pass/fail",
  "sio:is-implementation-of": {
    "@id": "https://example.org/metric/data.reused.co.6"
  }
}
```

---

## Test: Sensitive data for reused datasets

**Test ID:** T-DCSC  
**Persistent URI:** https://example.org/test/T-DCSC-sensitive-data  

**Implements:** [data.reused.co.7](metrics.md#metric-reused-data-sensitive)  

### Description
Checks the sensitive_data.

### Input
maDMP JSON

### Output
pass/fail

### Procedure
1. Parse the maDMP JSON document.  
2. Locate all dataset entries.  
3. Select datasets where `is_reused = true`.  
4. Verify that `sensitive_data` exists.  
5. Verify that its value is explicit and valid.  
6. If all reused datasets comply, return pass; otherwise return fail.

### JSON-LD (Test)
```json
{
  "@context": {
    "dcterms": "http://purl.org/dc/terms/",
    "ftr": "https://w3id.org/ftr#",
    "sio": "http://semanticscience.org/resource/"
  },
  "@id": "https://example.org/test/T-DCSC-sensitive-data",
  "@type": "ftr:Test",
  "dcterms:identifier": "T-DCSC",
  "dcterms:title": "Sensitive data for reused datasets",
  "dcterms:description": "Checks the sensitive_data.",
  "ftr:input": "maDMP JSON",
  "ftr:output": "pass/fail",
  "sio:is-implementation-of": {
    "@id": "https://example.org/metric/data.reused.co.7"
  }
}
```

---

## Test: Distribution present

**Test ID:** T-DCSC  
**Persistent URI:** https://example.org/test/T-DCSC-distribution-url-present  

**Implements:** [data.reused.co.8](metrics.md#metric-reused-data-url)  

### Description
Checks the distribution.

### Input
maDMP JSON

### Output
pass/fail

### Procedure
1. Parse the maDMP JSON document.  
2. Locate reused datasets (`is_reused = true`).  
3. Verify that at least one distribution object exists.  
4. If yes, return pass; otherwise return fail.

### JSON-LD (Test)
```json
{
  "@context": {
    "dcterms": "http://purl.org/dc/terms/",
    "ftr": "https://w3id.org/ftr#",
    "sio": "http://semanticscience.org/resource/"
  },
  "@id": "https://example.org/test/T-DCSC-distribution-url-present",
  "@type": "ftr:Test",
  "dcterms:identifier": "T-DCSC",
  "dcterms:title": "Distribution present",
  "dcterms:description": "Checks the distribution.",
  "ftr:input": "maDMP JSON",
  "ftr:output": "pass/fail",
  "sio:is-implementation-of": {
    "@id": "https://example.org/metric/data.reused.co.8"
  }
}
```

---

## Test: Access URL

**Test ID:** T-DCSC  
**Persistent URI:** https://example.org/test/T-DCSC-access-url  

**Implements:** [data.reused.co.8](metrics.md#metric-reused-data-url)  

### Description
Checks the access_url.

### Input
maDMP JSON

### Output
pass/fail

### Procedure
1. Parse the maDMP JSON document.  
2. Locate reused datasets (`is_reused = true`).  
3. Verify that at least one distribution contains `access_url`.  
4. If yes, return pass; otherwise return fail.

### JSON-LD (Test)
```json
{
  "@context": {
    "dcterms": "http://purl.org/dc/terms/",
    "ftr": "https://w3id.org/ftr#",
    "sio": "http://semanticscience.org/resource/"
  },
  "@id": "https://example.org/test/T-DCSC-access-url",
  "@type": "ftr:Test",
  "dcterms:identifier": "T-DCSC",
  "dcterms:title": "Access URL",
  "dcterms:description": "Checks the access_url.",
  "ftr:input": "maDMP JSON",
  "ftr:output": "pass/fail",
  "sio:is-implementation-of": {
    "@id": "https://example.org/metric/data.reused.co.8"
  }
}
```

---

## Test: PID matches destination repository record

**Test ID:** T-DCSC  
**Persistent URI:** https://example.org/test/T-DCSC-repo-match  

**Implements:** [data.reused.feas.1](metrics.md#metric-repository-reused-data-pid)  

### Description
Checks if reused dataset id in DMP matches the destination.

### Input
- dataset_id in maDMP  
- repository identifier field(s) (e.g., DOI URL)

### Output
pass/fail

### Procedure
1. Extract reused dataset identifiers from maDMP (`is_reused = true`).  
2. Query the target repository using the identifier.  
3. Retrieve the repository’s canonical identifier for the record.  
4. Compare with the maDMP dataset identifier.  
5. Pass if all identifiers match a repository record; otherwise fail.

### JSON-LD (Test)
```json
{
  "@context": {
    "dcterms": "http://purl.org/dc/terms/",
    "ftr": "https://w3id.org/ftr#",
    "sio": "http://semanticscience.org/resource/"
  },
  "@id": "https://example.org/test/T-DCSC-repo-match",
  "@type": "ftr:Test",
  "dcterms:identifier": "T-DCSC",
  "dcterms:title": "PID matches destination repository record",
  "dcterms:description": "Checks if reused dataset id in DMP matches the destination.",
  "ftr:input": "- dataset_id in maDMP   - repository identifier field(s) (e.g., DOI URL)",
  "ftr:output": "pass/fail",
  "sio:is-implementation-of": {
    "@id": "https://example.org/metric/data.reused.feas.1"
  }
}
```

---

## Test: PID resolves

**Test ID:** T-DCSC  
**Persistent URI:** https://example.org/test/T-DCSC-pid-resolves  

**Implements:** [data.reused.feas.1](metrics.md#metric-repository-reused-data-pid)  

### Description
Checks if the PID resolves.

### Input
- dataset_id from maDMP  
- PID resolver

### Output
pass/fail

### Procedure
1. Extract reused dataset identifiers from maDMP (`is_reused = true`).  
2. Attempt resolution via the resolver (HTTP request).  
3. Treat successful HTTP responses (2xx/3xx) as resolvable.  
4. Pass if all PIDs resolve; otherwise fail.

### JSON-LD (Test)
```json
{
  "@context": {
    "dcterms": "http://purl.org/dc/terms/",
    "ftr": "https://w3id.org/ftr#",
    "sio": "http://semanticscience.org/resource/"
  },
  "@id": "https://example.org/test/T-DCSC-pid-resolves",
  "@type": "ftr:Test",
  "dcterms:identifier": "T-DCSC",
  "dcterms:title": "PID resolves",
  "dcterms:description": "Checks if the PID resolves.",
  "ftr:input": "- dataset_id from maDMP   - PID resolver",
  "ftr:output": "pass/fail",
  "sio:is-implementation-of": {
    "@id": "https://example.org/metric/data.reused.feas.1"
  }
}
```

---

## Test: Reused data access matches destination

**Test ID:** T-DCSC  
**Persistent URI:** https://example.org/test/T-DCSC-access-match  

**Implements:** [data.reused.feas.2](metrics.md#metric-repository-reused-data-access)  

### Description
Check if reused data access in DMP matches the destination.

### Input
- `data_access` in maDMP  
- `access_right` in destination repository (e.g., Zenodo)

### Output
pass/fail

### Procedure
1. Extract reused datasets from maDMP (`is_reused = true`).  
2. For each reused dataset, retrieve its record from the destination repository.  
3. Extract the repository access rights value.  
4. Compare maDMP `data_access` with repository `access_right`.  
5. Pass if all values match; otherwise fail.

### JSON-LD (Test)
```json
{
  "@context": {
    "dcterms": "http://purl.org/dc/terms/",
    "ftr": "https://w3id.org/ftr#",
    "sio": "http://semanticscience.org/resource/"
  },
  "@id": "https://example.org/test/T-DCSC-access-match",
  "@type": "ftr:Test",
  "dcterms:identifier": "T-DCSC",
  "dcterms:title": "Reused data access matches destination",
  "dcterms:description": "Check if reused data access in DMP matches the destination.",
  "ftr:input": "- `data_access` in maDMP   - `access_right` in destination repository (e.g., Zenodo)",
  "ftr:output": "pass/fail",
  "sio:is-implementation-of": {
    "@id": "https://example.org/metric/data.reused.feas.2"
  }
}
```

---

## Test: Reused data license matches destination

**Test ID:** T-DCSC  
**Persistent URI:** https://example.org/test/T-DCSC-license-match  

**Implements:** [data.reused.feas.3](metrics.md#metric-repository-reused-data-license)  

### Description
Checks if the license of the repository is the one mentioned in the DMP.

### Input
- license in maDMP JSON  
- license in destination repository (e.g., Zenodo)

### Output
pass/fail

### Procedure


### JSON-LD (Test)
```json
{
  "@context": {
    "dcterms": "http://purl.org/dc/terms/",
    "ftr": "https://w3id.org/ftr#",
    "sio": "http://semanticscience.org/resource/"
  },
  "@id": "https://example.org/test/T-DCSC-license-match",
  "@type": "ftr:Test",
  "dcterms:identifier": "T-DCSC",
  "dcterms:title": "Reused data license matches destination",
  "dcterms:description": "Checks if the license of the repository is the one mentioned in the DMP.",
  "ftr:input": "- license in maDMP JSON   - license in destination repository (e.g., Zenodo)",
  "ftr:output": "pass/fail",
  "sio:is-implementation-of": {
    "@id": "https://example.org/metric/data.reused.feas.3"
  }
}
```

