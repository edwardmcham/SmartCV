# Achievements API

This page explains the `achievements` resource in the SmartCV service. The `achievements` data lists accomplishments that a user can include in a CV. Each entry links to a job through a job ID, so you can connect each achievement to the role that produced it.

---

## Base endpoint

```
GET /achievements
```

This request returns every achievements entry in the database.

You can also request a single item:

```
GET /achievements/{id}
```

Replace `{id}` with any valid numeric ID.

---

## Fields in this resource

Each `achievements` item has these fields:

| Field | Type | Description |
|-------|--------|-------------|
| achievement | string | A short description of the accomplishment. |
| jobId | number | The ID of the related job. |
| id | number | The unique identifier for this item. |

These fields match the values in api/db-cv.json.

---

## Example response

### GET `/achievements`

```
[
  {
    "achievement": "Authored user guides for ConfigOS MPO, supporting RMF closed-loop STIG/CIS compliance in complex network environments.",
    "jobId": 1,
    "id": 1
  },
  {
    "achievement": "Migrated legacy PDF documentation to Markdown, reducing file size by 97% and improving accessibility.",
    "jobId": 1,
    "id": 2
  },
  {
    "achievement": "Documented UI designs using Balsamiq Wireframes and Confluence; linked documentation to Jira requirements for enhanced traceability.",
    "jobId": 1,
    "id": 3
  }
]
```

---

## Try it with curl

Run this command after you start the JSON server:

```
curl http://localhost:3000/achievements
```

A successful response matches the example JSON in the example response.

---

## Filter achievements by job ID

Use the `jobId` field to list achievements from a specific role:

```
curl "http://localhost:3000/achievements?jobId=1"
```

Change the value of `jobId` to match any job in the Jobs resource.

---

## Connect achievements to job details

You can fetch the job first and then list the achievements that match it.

Example:

1. Get the job:
```
curl "http://localhost:3000/jobs?employer_like=SteelCloud"
```

2. Use the returned ID:
```
curl "http://localhost:3000/achievements?jobId=1"
```

This pattern helps you build CV sections that group achievements by role.

---

## Related topics

- [Prerequisites](../getting-started/prerequisites.html)
- [API References](../index.html#api-references)
- [Tutorials](../tutorials/index.html)

---

[← Back to home](../index.html)
