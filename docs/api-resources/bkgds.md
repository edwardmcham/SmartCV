# Backgrounds API

This page explains the `bkgds` resource in the SmartCV service. The `bkgds` data lists career background categories that a user can include in a CV. Each item comes from the local JSON database and returns structured fields that you can filter or reuse in other SmartCV tasks.

---

## Base endpoint

```
GET /bkgds
```

This endpoint returns every background entry in the database.

You can also request a single item:

```
GET /bkgds/{id}
```

Replace `{id}` with any valid numeric ID.

---

## Fields in this resource

Each `bkgds` item has these fields:

| Field | Type | Description |
|-------|------|-------------|
| bkgd | string | The name of the background category. |
| id | number | The unique identifier for this item. |

These fields match the values in api/db-cv.json.

---

## Example response

### GET `/bkgds`

```
[
  {
    "bkgd": "Multilingual Content",
    "id": 1
  },
  {
    "bkgd": "Structured Authoring",
    "id": 2
  },
  {
    "bkgd": "Technical Writing",
    "id": 3
  },
  {
    "bkgd": "UI/Web Design",
    "id": 4
  }
]
```

---

## Try it with curl

Use this command in a terminal after you start your local JSON server:

```
curl http://localhost:3000/bkgds
```

If the server runs correctly, the response matches the example JSON in the example response section.

---

A successful response matches the example JSON in the example response.

---

## Related topics

- [Prerequisites](../getting-started/prerequisites.html)
- [API References](../index.html#api-references)
- [Tutorials](../tutorials/index.html)

---

[← Back to home](../index.html)


