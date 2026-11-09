# SeniorsInProcess-Prothia-Report

## Overview

This repository is the documentation hub for **SeniorsInProcess**, a student project developing **Prothia**, a proposed digital platform for supporting prosthetic rehabilitation and monitoring. The report documents the project from initial research and requirements discovery through UX/UI and software design, implementation evidence, and recommendations.

The project’s primary objective is to improve continuity of care for people with limb loss by helping patients, rehabilitation professionals, and orthopedic centers share information about rehabilitation progress and prosthesis use. This repository contains the team’s research, analyses, report chapters, diagrams, and supporting evidence. It does not contain application source code.

## Target Segment / Context

Despite the team name **SeniorsInProcess**, the project’s documented target segment is **people with limb loss who are adapting to and rehabilitating with a prosthesis**—not older adults as a demographic. The work focuses on the information and follow-up gaps between in-person clinical appointments: patients may have limited feedback while exercising at home, clinicians may have little objective visibility into daily progress, and orthopedic technicians may lack timely information about prosthesis use and maintenance needs.

Prothia is designed around three primary user groups:

- **Patients** undergoing prosthetic adaptation and rehabilitation.
- **Rehabilitation professionals** who prescribe and monitor treatment.
- **Orthopedic/prosthetic technicians and centers** that manage prostheses and maintenance.

## Documentation Structure

The report is maintained as Markdown source files in `front-matter/`, with referenced visual materials in `assets/`.

```text
SeniorsInProcess-Prothia-Report/
├── README.md
├── assets/                                # Images, diagrams, mockups, and project evidence
└── front-matter/                          # Report source and supporting documentation
    ├── 001-cover.md                       # Course, project, and contributor information
    ├── 002-version_control.md              # Report version history
    ├── 003-project_report_collaboration.md  # Team collaboration record
    ├── 004-index.md                        # Report table of contents
    ├── 005-student-outcome.md              # Teamwork and student outcome evidence
    ├── 010-chapter-01.md                   # Introduction, startup, solution, and target segments
    ├── 020-chapter-02.md                   # Competitive analysis, interviews, and needfinding
    ├── 030-chapter-03.md                   # User stories, impact mapping, and product backlog
    ├── 040-ux_ui_and_information_architecture.md # UX/UI and product design
    ├── 041-software_architecture.md        # DDD, C4 architecture, and component design
    ├── 042-technical_and_database_design.md # Object-oriented and database design
    ├── 050-chapter-05.md                   # Implementation, validation, and deployment evidence
    ├── 051-sprint.md                       # Sprint planning and development material
    ├── 097-conclusions.md                  # Project conclusions
    ├── 098-recommendations.md              # Recommendations and next steps
    ├── 099-bibliography.md                 # References
    └── 100-annexes.md                      # Supporting annexes
```

## Key Document Summaries

- [**Cover and team details**](front-matter/001-cover.md) — identifies the course, project, and contributors.
- [**Table of contents**](front-matter/004-index.md) — provides the report’s chapter outline.
- [**Introduction**](front-matter/010-chapter-01.md) — describes SeniorsInProcess, Prothia, the problem context, and intended users.
- [**Requirements elicitation and analysis**](front-matter/020-chapter-02.md) — brings together competitor research, user interviews, and needfinding artifacts such as personas and journey analysis.
- [**Requirements specification**](front-matter/030-chapter-03.md) — records user stories, acceptance criteria, impact mapping, and backlog material.
- [**UX/UI and information architecture**](front-matter/040-ux_ui_and_information_architecture.md) — documents the product experience, interface designs, and information organization.
- [**Software architecture**](front-matter/041-software_architecture.md) — describes the domain model, bounded contexts, and C4 architecture diagrams.
- [**Technical and database design**](front-matter/042-technical_and_database_design.md) — documents object-oriented and relational database designs.
- [**Implementation, validation, and deployment**](front-matter/050-chapter-05.md) and [**sprint material**](front-matter/051-sprint.md) — collect development, deployment, and iteration evidence.
- [**Conclusions**](front-matter/097-conclusions.md), [**recommendations**](front-matter/098-recommendations.md), [**bibliography**](front-matter/099-bibliography.md), and [**annexes**](front-matter/100-annexes.md) — provide the report’s findings, proposed next steps, references, and supporting materials.

## Team Members & Contributors

The contributors are listed below with their areas of contribution as documented in the report. These descriptions summarize project work and are not formal job titles.

- **Ana Camila Patricio Farias** — requirements and needfinding, backlog refinement, EventStorming, and frontend work for Communication, Locales, and Prescription.
- **Leonardo Felix Dextre Flores** — architecture and EventStorming, report design updates, and frontend work for Billing and Workshop.
- **Oscar Diego Checa Burga** — problem and introduction materials, shared frontend components, and work on Monitoring and Patients.
- **Carlos Matthew Salcedo Correa** — EventStorming collaboration and implementation/integration work for Analytics and Patient Portal.
- **Rafael Barrenechea Bustamante** — architecture and software diagrams, plus implementation work for Identity and Access Management and Option.

For detailed student profiles, see [Chapter I](front-matter/010-chapter-01.md). Additional collaboration and contribution evidence is available in the [student outcome section](front-matter/005-student-outcome.md).
