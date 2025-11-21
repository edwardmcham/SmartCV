# Tools API

This page explains the `tools` resource in the SmartCV service. The Tools data lists skills and tools that a user can include in a CV. Each item comes from the local JSON database and returns structured fields that you can search, filter, or reuse in SmartCV tasks.

---

## Base endpoint

```
GET /tools
```

This request returns every tools entry in the database.

You can also request a single item:

```
GET /tools/{id}
```

Replace `{id}` with any valid numeric ID.

---

## Fields in this resource

Each `tools` item has these fields:

| Field | Type | Description |
|-------|------|-------------|
| tool | string | The name of the tool or skill. |
| type | string | A short code that groups items by category. |
| id | number | The unique identifier for this item. |

---

## Example response

### GET `/tools`

```
[
  {
    "tool": "Adobe FrameMaker",
    "type": "tw",
    "id": 1
  },
  {
    "tool": "Confluence",
    "type": "tw",
    "id": 2
  },
  {
    "tool": "Markdown",
    "type": "tw",
    "id": 4
  },
  {
    "tool": "Adobe Creative Suite",
    "type": "wd",
    "id": 8
  }
]
```

---

## Try it with curl

Use this command after you start the JSON server:

```
curl http://localhost:3000/tools
```

---

## Filter by category

```
curl "http://localhost:3000/tools?type=tw"
```

---

## Search by tool name

```
curl "http://localhost:3000/tools?tool_like=Adobe"
```

---

## Related topics

- [Prerequisites](../getting-started/prerequisites.html)
- [API References](../index.html#api-references)
- [Tutorials](../tutorials/index.html)

---

[← Back to home](../index.html)


