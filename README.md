# SmartCV

*Authentic CV Customization without AI.*

## Overview

**SmartCV** is a JSON-based API that builds customized CVs from structured, user-provided data — not AI-generated text.

This repository is part of the **SME/TW collaboration** for the Technical Writing Portfolio project.  

- **SME:** Eddie McHam
- **TW:** Drashti Bhatt  
- **Service:** SmartCV API  
- **Repo Purpose:** SME-managed source files for API structure and data examples.

## What SmartCV Does

- Filters a professional database (`db-cv.json`) by job description keywords to produce targeted CVs.
- Delivers authentic, keyword-rich CVs aligned with real job descriptions for stronger ATS results.
- **Audiences:** Job seekers, career platforms, and résumé builders focused on credibility.

## What SmartCV Does Not Do

- **Use AI to write or fabricate CV content.** All data comes from verified user input.

## API Resources

### `/bkgds`

| Field | Type | Description |
|:-|:-|:-|
| `bkgd` | String | Career background category |
| `id` | Integer | A unique ID number |

### `/tools`

| Field | Type | Description |
|:-|:-|:-|
| `tool` | String | Skill or tool name |
| `type` | String | Skill or tool category |
| `id` | Integer | A unique ID number |

### `/creds`

| Field | Type | Description |
|:-|:-|:-|
| `cred` | String | Degree, class, or certificate name |
| `location` | String | Where cred was earned |
| `id` | Integer | A unique ID number |

### `/jobs`

| Field | Type | Description |
|:-|:-|:-|
| `title` | String | Job or project title |
| `type` | String | Job category |
| `startMonth` | Integer | Month job started |
| `startYear` | Integer | Year job started |
| `endMonth` | Integer | Month job ended. If `null`, this is the current job. |
| `endYear` | Integer | Year job ended. If `null`, this is the current job. |
| `id` | Integer | A unique ID number |

### `/portfolio`

| Field | Type | Description |
|:-|:-|:-|
| `name` | String | Sample name |
| `url` | String | Link to sample page |
| `jobId` | Integer | The ID number of the `jobs` item from which this sample was taken |
| `id` | Integer | A unique ID number |

### `/achievements`

| Field | Type | Description |
|:-|:-|:-|
| `achievement` | String | Brief description of the achievement |
| `jobId` | Integer | The ID number of the `jobs` item from which this sample was taken |
| `id` | Integer | A unique ID number |

## Example Database File

The main database file for this service is `api/db-cv.json`, which models how data would be stored and fetched by a backend service.

## Example Query

### Request

```bash
GET /recipes?ingredients=spinach,cheese
```

### Response

```json
[
  {
    "id": 1,
    "title": "Spinach Cheese Omelet",
    "ingredients": ["Eggs", "Spinach", "Cheese", "Salt", "Pepper"],
    "cookingTime": 10,
    "difficulty": "Easy",
    "authorId": 1
  }
]
```

## Quick Start (Example Integration)

### Using cURL

```bash
curl https://example.com/api/recipes?ingredients=tomato,cheese
```

### Using JavaScript (fetch)

```javascript
fetch('/api/recipes?ingredients=tomato,cheese')
  .then(response => response.json())
  .then(data => console.log(data));
```

These calls return a filtered list of recipes that match the provided ingredients.

## Project Structure

```text
RecipeBuddy-API/
├── README.md
└── api/
    └── recipe-buddy-db-source.json
```

## Use Case Example

A user named **Drashti** opens Recipe Buddy, enters “potatoes, spinach, and cheese” as available ingredients. The API instantly returns dishes like *Spinach Cheese Omelet* or *Aloo Palak*, which can be made immediately without extra shopping. This reduces food waste and simplifies decision-making in the kitchen.

## Collaboration Notes

This repository is maintained by **Drashti Bhatt (SME)** and shared with **Eddie McHam (TW)**. It provides base data and specifications to support API documentation in the **SmartCV** repo.

Future collaboration will include:  

- Adding OpenAPI/Swagger specifications  
- Writing reference documentation and tutorials  
- Integrating visuals and code samples into Eddie’s SmartCV project

## License

This project is part of an academic documentation portfolio and may be used for educational purposes only.  

© 2025 Drashti Bhatt. All rights reserved.
