# Jobs API

This page explains the `jobs` resource in the SmartCV service. The Jobs data lists past and current roles that a user can include in a CV. Each item comes from the local JSON database and returns structured fields that you can filter or combine with other SmartCV resources.

---

## Base endpoint

```
GET /jobs
```

This request returns every jobs entry in the database.

You can also request a single item:

```
GET /jobs/{id}
```

Replace `{id}` with any valid numeric ID.

---

## Fields in this resource

Each `jobs` item has these fields:

| Field      | Type   | Description |
|-----------|--------|-------------|
| title     | string | The job title, such as Technical Writer or Web Developer. |
| type      | string | A short code that groups jobs by category. |
| employer  | string | The company or organization name. |
| startMonth | number | The month when the job began. |
| startYear  | number | The year when the job began. |
| endMonth   | number or null | The month when the job ended. Use null for a current job. |
| endYear    | number or null | The year when the job ended. Use null for a current job. |
| id        | number | The unique identifier for this item. |

These fields match the values in api/db-cv.json.

---

## Example response

### GET `/jobs`

```
[
  {
    "title": "Technical Writer",
    "type": "wd",
    "employer": "SteelCloud LLC",
    "startMonth": 2,
    "startYear": 2023,
    "endMonth": null,
    "endYear": null,
    "id": 1
  },
  {
    "title": "Technical Writer",
    "type": "wd",
    "employer": "Baxter International",
    "startMonth": 6,
    "startYear": 2022,
    "endMonth": 2,
    "endYear": 2023,
    "id": 2
  },
  {
    "title": "Web Developer",
    "type": "wd",
    "employer": "Internet Publishing Service (IPS)",
    "startMonth": 1,
    "startYear": 2018,
    "endMonth": 2,
    "endYear": 2022,
    "id": 3
  }
]
```

---

## Try it with curl

Run this command after you start the JSON server:

```
curl http://localhost:3000/jobs
```

If the server runs correctly, the response matches the example JSON in the example response section.

---

## Filter jobs by employer

Use the `employer` field to find jobs for a specific organization.  
This example looks for jobs that match the organization name Non-Roman Script Initiative (NRSI) in the employer field:

```
curl "http://localhost:3000/jobs?employer_like=NRSI"
```

You can change the value of `employer_like` to match the company name that you need.

---

## Filter jobs by type

Use the `type` field to group jobs by category. The demo database uses simple codes such as \`wd\`:

```
curl "http://localhost:3000/jobs?type=wd"
```

Use this pattern when you want to build a CV that focuses on one work domain.

---

## Related topics

- [Prerequisites](../getting-started/prerequisites.html)
- [API References](../index.html#api-references)
- [Tutorials](../tutorials/index.html)

---

[← Back to home](../index.html)
