# SmartCV API Documentation

SmartCV provides a REST-style API for analyzing resumes and returning structured
insights such as extracted skills, experience indicators, and scoring signals.

This documentation is written for developers integrating resume analysis into
internal tools, applicant tracking systems, or screening workflows.

> SmartCV is a sample API documentation project. The API described here is
illustrative and designed to demonstrate documentation structure, clarity,
and developer-focused best practices.

---

## What the API Does

The SmartCV API accepts resume content and returns structured data that can be
used to support automated screening, ranking, or enrichment workflows.
Content is authored directly by the user, not AI-generated.

Typical use cases include:
- Parsing resumes into structured data
- Extracting skills and experience signals
- Supporting internal hiring or evaluation tools

---

## High-Level Workflow

1. Client sends resume content to the SmartCV API
2. SmartCV analyzes the content
3. API returns structured results in JSON format
4. Client uses results for downstream processing or display

---

## Audience

This documentation is intended for:
- Software engineers
- Platform and tools teams
- Technical integrators

Familiarity with REST APIs and JSON is assumed.

---

## API references

Each SmartCV resource has a dedicated page with fields, examples, and filtering options.

- [`bkgds`](api-resources/bkgds.md): career backgrounds  
- [`tools`](api-resources/tools.md): skills and tool categories  
- [`creds`](api-resources/creds.md): degrees and certificates  
- [`jobs`](api-resources/jobs.md): work experience  
- [`portfolio`](api-resources/portfolio.md): samples linked to jobs  
- [`achievements`](api-resources/achievements.md): achievements linked to jobs  

Use these links to review each resource.

---

## Getting started

Start here if you are new to SmartCV:

- [`Prerequisites`](tutorials/prerequisites.md): tools you need and how to run the service locally

This page explains how to set up the environment and access the SmartCV API.

---

## Tutorials

These guides show how to work with SmartCV data:

- [`Filter jobs by employer`](tutorials/filter-jobs-by-employer.md)  
- [`Get portfolio items for a job`](tutorials/get-portfolio-for-job.md)  
- [`Build a targeted CV`](tutorials/build-targeted-cv.md)  
- [`Combine job, portfolio, and achievement data`](tutorials/combine-job-resources.md)  
- [`Search tools and credentials by type`](tutorials/search-tools-and-creds.md)  


