# RapidAPI v2 Endpoint Setup Guide

## Step 1: Update Gateway Base URL

1. Go to **Gateway** tab
2. Set **Base URL** to:
   ```
   https://trustlayer-control-plane-v2.nimblyjson-api.workers.dev
   ```
3. Click **Save**

---

## Step 2: Update Existing Endpoints

Click **Edit** on each endpoint and update:

### Prompt Injection Scan
- **Path:** `/v2/scan`
- **Method:** POST
- **Body (example):**
```json
{
  "prompt": "string (required)",
  "providers": ["heuristic", "openai_moderation"],
  "mode": "worst_case"
}
```

### Contract Test
- **Path:** `/v2/contracts`
- **Method:** POST
- **Body:**
```json
{
  "text": "string (required)"
}
```

### Health Check
- **Path:** `/health`
- **Method:** GET

### Incident Status
- **Path:** `/v2/incident/status`
- **Method:** GET

### Incident Lockdown (Kill Switch)
- **Path:** `/v2/incident/lockdown`
- **Method:** POST ⚠️ (change from GET!)
- **Body:**
```json
{
  "scope": "tenant"
}
```

### Drift Baseline
- **Path:** `/v2/drift/baseline`
- **Method:** POST
- **Body:**
```json
{
  "suite_id": "string (required)",
  "baseline_output": "string (required)",
  "baseline_tool_calls": []
}
```

### Drift Check
- **Path:** `/v2/drift/check`
- **Method:** POST
- **Body:**
```json
{
  "suite_id": "string (required)",
  "current_output": "string (required)",
  "tool_calls": [],
  "threshold": 0.35
}
```

### Drift Events
- **Path:** `/v2/drift/events`
- **Method:** GET
- **Query params:** `suite_id` (required), `limit` (optional)

### Audit Trace Events
- **Path:** `/v2/audit/export.csv`
- **Method:** GET

---

## Step 3: Add NEW Endpoints

Click **Create Endpoint** for each:

### Incident Unlock (NEW)
- **Name:** Incident Unlock
- **Path:** `/v2/incident/unlock`
- **Method:** POST
- **Body:**
```json
{
  "scope": "tenant"
}
```

### Policy Upload (NEW)
- **Name:** Policy Upload
- **Path:** `/v2/policy/upload`
- **Method:** POST
- **Body:**
```json
{
  "policy": "JSON string of policy pack"
}
```

### Policy Get (NEW)
- **Name:** Get Policy
- **Path:** `/v2/policy`
- **Method:** GET

---

## Step 4: Test Each Endpoint

After saving, use RapidAPI's built-in test feature to verify each endpoint works.

---

## Tier Access Reference

| Endpoint | Minimum Tier |
|----------|--------------|
| /health | Public |
| /v2/scan | Developer |
| /v2/contracts | Developer |
| /v2/incident/status | Startup |
| /v2/drift/* | Startup |
| /v2/policy (GET) | Startup |
| /v2/incident/lockdown | Business |
| /v2/incident/unlock | Business |
| /v2/policy/upload | Business |
| /v2/audit/export.csv | Business |
