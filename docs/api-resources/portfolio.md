# Portfolio API

This page explains the `portfolio` resource in the SmartCV service. The Portfolio data lists sample work items that a user can include in a CV. Each entry links to a job through a job ID, so you can connect each sample to the role that created it..

---

## Base endpoint

```
GET /portfolio
```

This request returns every portfolio entry in the database.

You can also request a single item:

```
GET /portfolio/{id}
```

Replace `{id}` with any valid numeric ID.

---

## Fields in this resource

Each `portfolio` item has these fields:

| Field | Type | Description |
|-------|--------|-------------|
| name | string | The title of the work sample. |
| URL | string | A link to the sample. |
| jobId | number | The ID of the related job. |
| id | number | The unique identifier for this item. |

These fields match the values in api/db-cv.json.

---

## Example response

### GET `/portfolio`

```
[
  {
    "name": "INSTRUCTIONS FOR USE, Welch Allyn FlexiPort Disposable Blood Pressure Cuff",
    "url": "https://bit.ly/46vnUdU",
    "jobId": 2,
    "id": 1
  },
  {
    "name": "WILDFIRE 5 ADMIN THEME",
    "url": "https://emcham.io/wildfire-5-admin-theme",
    "jobId": 3,
    "id": 2
  },
  {
    "name": "SIL PRODUCT WEBSITES",
    "url": "https://emcham.io/product-sites/",
    "jobId": 4,
    "id": 4
  }
]
```

---

## Try it with curl

Run this command after you start the JSON server:

```
curl http://localhost:3000/portfolio
```

A successful response matches the example JSON in the example response.

---

## Filter samples by job ID

Every portfolio entry links to the job where the user created the sample.  
Use the `jobId` field to filter the list:

```
curl "http://localhost:3000/portfolio?jobId=4"
```

This returns samples that belong to job ID 4.  
You can replace `4` with any other ID in the Jobs resource.

---

## Combine portfolio with job details

You can fetch a job first, note its ID, and then use that ID to get related samples.

Example:

1. Get the job:
```
curl "http://localhost:3000/jobs?employer_like=Non-Roman Script Initiative"
```

2. Use the returned ID to find samples:
```
curl "http://localhost:3000/portfolio?jobId=4"
```

This pattern helps you build a CV section that links work samples to each role.

---

## Related topics

- [Prerequisites](../getting-started/prerequisites.html)
- [API References](../index.html#api-references)
- [Tutorials](../tutorials/index.html)

---

[← Back to home](../index.html)
