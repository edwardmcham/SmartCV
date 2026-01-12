# SmartCV API (Sample Documentation Project)

SmartCV is a sample API documentation project that demonstrates how to document
a resume analysis and scoring service using modern docs-as-code practices.

This repository focuses on:
- API overview and usage documentation
- Endpoint descriptions and request/response examples
- OpenAPI-based reference material
- Developer-focused explanations and workflows

> Note: SmartCV is a documentation-focused sample project. This repository prioritizes documentation structure and developer usability over production readiness.

## What This Project Demonstrates

- API documentation structure for a REST-style service
- Markdown-based docs-as-code workflow
- OpenAPI usage for API reference
- Clear developer onboarding and examples

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

## Examples

### Postman Request

This call returns a single job where the employer name contains `NRSI`.

```bash
GET {base_url}/jobs?employer_like=NRSI
```

### Postman Response

```json
[
    {
        "title": "Web Developer",
        "type": "wd",
        "employer": "Non-Roman Script Initiative (NRSI)",
        "startMonth": 6,
        "startYear": 2015,
        "endMonth": 10,
        "endYear": 2017,
        "id": 4
    }
]
```

### cURL Request

This call returns a list of portfolio samples that were created for the employer `NRSI`.

The DB tables are joined by setting `jobId` in the **portfolio** resource to the `id` grabbed from the **jobs** resource by the [Postman request](#postman-request).

```bash
curl http://localhost:3000/portfolio?jobId=4
```

### cURL Response

```json
[
    {
        "name": "SIL PRODUCT WEBSITES",
        "url": "https://emcham.io/product-sites/",
        "jobId": 4,
        "id": 4
    },
    {
        "name": "WORDPRESS SHORT CODE TO GENERATE CSS FOR ARABIC CALLIGRAPHY",
        "url": "https://emcham.io/wp-css-arabic/",
        "jobId": 4,
        "id": 5
    }
]
```

## Project Structure

```text
SmartCV/
├── README.md
└── api/
    └── db-cv.json
```

## Use Case Example

1. The user grabs keywords from a job description.
2. The user filters items from the **tools**, **jobs**, and **portfolio** resources to generate a CV tailored to the job description.

## Collaboration Notes

This repository is maintained by **Eddie McHam (SME)** and shared with **Drashti Bhatt (TW)**. It provides base data and specifications to support API documentation in the **SmartCV** repo.

Future collaboration will include:  

- Adding OpenAPI/Swagger specifications  
- Writing reference documentation and tutorials  
- Integrating visuals and code samples into Eddie’s SmartCV project

## License

This project is part of an academic documentation portfolio and may be used for educational purposes only.  

© 2025 Eddie McHam. All rights reserved.
