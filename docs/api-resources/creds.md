# Credentials API

This page explains the `creds` resource in the SmartCV service. The Credentials data lists degrees, certificates, and training items that a user can include in a CV. Each item comes from the local JSON database and returns structured fields that you can filter or combine with other SmartCV resources.

---

## Base endpoint

```
GET /creds
```

This request returns every credentials entry in the database.

You can also request a single item:

```
GET /creds/{id}
```

Replace `{id}` with any valid numeric ID.

---

## Fields in this resource

Each `creds` item has these fields:

| Field | Type | Description |
|-------|------|-------------|
| cred | string | The name of the credential, degree, or certificate. |
| location | string | The institution or place where the user earned the credential. |
| id | number | The unique identifier for this item. |

These fields match the values in api/db-cv.json.

---

## Example response

### GET `/creds`

```
[
  {
    "cred": "API Documentation",
    "location": "University of Washington",
    "id": 1
  },
  {
    "cred": "Society for Technical Communication (STC)",
    "location": "Washington, DC chapter",
    "id": 2
  },
  {
    "cred": "B. Sc., Computer Information Systems",
    "location": "East Texas Baptist University",
    "id": 3
  }
]
```

---

## Try it with curl

Run this command after you start the JSON server:

```
curl http://localhost:3000/creds
```

If the server runs correctly, the response matches the example JSON in the example response section.

---

## Search by credential name

Use the `_like` filter to search by part of a credential title:

```
curl "http://localhost:3000/creds?cred_like=API"
```

---

## Related topics

- [Prerequisites](../getting-started/prerequisites.html)
- [API References](../index.html#api-references)
- [Tutorials](../tutorials/index.html)

---

[← Back to home](../index.html)
