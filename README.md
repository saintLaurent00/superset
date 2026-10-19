<!--
Licensed to the Apache Software Foundation (ASF) under one
or more contributor license agreements. See the NOTICE file
distributed with this work for additional information
regarding copyright ownership. The ASF licenses this file
to you under the Apache License, Version 2.0 (the
"License"); you may not use this file except in compliance
with the License. You may obtain a copy of the License at

  http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing,
software distributed under the License is distributed on an
"AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
KIND, either express or implied. See the License for the
specific language governing permissions and limitations
under the License.
-->

# BI-Plateforme — Superset Experience

**A focused design and user-experience initiative by Laurent Ouattara, built on Apache Superset.**

[![Based on Apache Superset](https://img.shields.io/badge/based%20on-Apache%20Superset-1f2937?logo=apache)](https://github.com/apache/superset)
[![License: Apache 2.0](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](LICENSE.txt)
[![Preview workflow](https://github.com/saintLaurent00/superset/actions/workflows/deploy-pages-preview.yml/badge.svg)](https://github.com/saintLaurent00/superset/actions/workflows/deploy-pages-preview.yml)
[![GitHub branch](https://img.shields.io/badge/work-in%20progress-8b5cf6)](https://github.com/saintLaurent00/superset/tree/bi-plateforme/page-by-page-theme)

> **Project status: active work in progress.** This repository is a personal development fork of Apache Superset. The current focus is a careful, page-by-page refinement of its interface for the BI-Plateforme design direction. It is not an official Apache project or a standalone BI product.

---

## Overview

BI-Plateforme is my effort to make business-intelligence workflows feel clearer, more coherent, and easier to navigate without sacrificing the analytical capabilities that make Apache Superset valuable.

Rather than building a parallel application or replacing Superset's foundations, this work starts with the existing product and improves its experience incrementally: information hierarchy, spacing, visual consistency, readability, interaction feedback, and responsive behaviour.

The long-term direction is a professional, data-first interface that helps people move naturally from data sources and datasets to charts, queries, and dashboards.

### Preview

**[Open the BI-Plateforme interface preview](https://saintlaurent00.github.io/superset/)**

The preview is a static visual prototype served through GitHub Pages when deployment is available. It is intended for reviewing interface direction and navigation—not for connecting databases or running real SQL queries. Its sample metrics and chart content are illustrative.

### What is being refined

- **Dashboards** — a cleaner way to find, organize, and manage dashboards.
- **Charts** — a consistent visual language for exploring and presenting data.
- **Datasets** — clearer entry points for working with analytical datasets.
- **Data sources** — a more understandable presentation of connection-related workflows.
- **SQL Lab** — a preview of the query-workspace experience.

These areas are being approached progressively. A screen appearing in the static preview does not mean its production counterpart has already been redesigned or that its backend behaviour has changed.

---

## Design principles

The interface direction is deliberately restrained. The aim is to make analytical content—not decorative UI—the centre of attention.

| Principle | Direction |
| --- | --- |
| **Data first** | Give charts, tables, metrics, and decisions visual priority. |
| **Minimal and professional** | Reduce unnecessary decoration and visual noise. |
| **Consistent** | Reuse predictable spacing, controls, borders, and interaction patterns. |
| **Readable** | Establish clear hierarchy, accessible contrast, and comfortable line lengths. |
| **Responsive** | Keep core workflows usable across desktop and smaller screens. |
| **Accessible** | Provide visible focus states and respect reduced-motion preferences. |
| **Incremental** | Improve existing Superset pages without needlessly replacing their logic. |

### Visual language

- **Base palette:** white, near-black, and neutral greys.
- **Accent:** violet `#8b5cf6`, used selectively for emphasis and focus.
- **Surfaces:** subtle borders, restrained shadows, and rounded cards.
- **Typography:** Inter for interface text, with Cormorant Garamond and JetBrains Mono used where appropriate to the broader BI-Plateforme identity.
- **Motion:** purposeful transitions that respect `prefers-reduced-motion`.

The existing Superset theme system and component conventions remain important. Styling should be scoped where possible and should not break existing workflows.

---

## Current implementation

The current working branch is:

```text
bi-plateforme/page-by-page-theme
```

The initial implementation includes:

- a static interface prototype in `docs/index.html`;
- a GitHub Actions workflow at `.github/workflows/deploy-pages-preview.yml`;
- a first, scoped visual refinement of the Superset dashboard-list page;
- page-specific CSS in `superset-frontend/src/pages/DashboardList/biPlatformDashboardList.css`.

### Key files

| Path | Purpose |
| --- | --- |
| `docs/index.html` | Static BI-Plateforme visual preview. |
| `.github/workflows/deploy-pages-preview.yml` | Publishes the static preview to GitHub Pages. |
| `superset-frontend/src/pages/DashboardList/index.tsx` | Existing dashboard-list page with initial UX refinements. |
| `superset-frontend/src/pages/DashboardList/biPlatformDashboardList.css` | Scoped styles for the dashboard-list page. |

**Validation status:** this work is ongoing. Do not assume that the full frontend build, automated tests, accessibility audit, or production deployment has passed unless a corresponding successful workflow or test result is available.

---

## Architecture and scope

This repository remains based on **Apache Superset**. The intention is to preserve its existing application architecture and extend the experience in place.

- **Frontend:** the existing Superset React and TypeScript application.
- **Backend:** the existing Superset Python application and its services.
- **Data access:** the connectors, SQLAlchemy integrations, metadata, and query workflows provided by Superset.
- **Interface work:** incremental updates to existing pages and components, with scoped styling where appropriate.
- **Preview:** static HTML and CSS/JavaScript served independently from the live application.

The GitHub Pages prototype has **no connected Superset backend**. Its search, navigation, sample metrics, and actions are demonstrations. It does not authenticate users, connect to a database, execute SQL, or persist dashboard changes.

This distinction is intentional: the static preview helps validate visual direction before those refinements are reviewed and integrated into the real application.

---

## Development approach

The work follows a page-by-page cycle:

1. **Inspect** the existing page, components, routes, and interactions.
2. **Define** the visual and usability changes against the BI-Plateforme direction.
3. **Implement** the smallest maintainable change in the correct feature location.
4. **Preserve** existing Superset behaviour and established component patterns.
5. **Validate** the relevant build, tests, and user flows.
6. **Review** the result before moving to the next page.

The guiding rule is simple: improve the interface without introducing regressions or creating a disconnected second application.

### Working branch and pull request

- **Working branch:** [`bi-plateforme/page-by-page-theme`](https://github.com/saintLaurent00/superset/tree/bi-plateforme/page-by-page-theme)
- **Current draft pull request:** [PR #1 — Apply BI-Plateforme theme to dashboard list](https://github.com/saintLaurent00/superset/pull/1)
- **Preview workflow:** [GitHub Actions](https://github.com/saintLaurent00/superset/actions/workflows/deploy-pages-preview.yml)

The pull request is a work in progress. Review its current checks and discussion before treating any change as ready to merge.

---

## Getting started

### Review the visual prototype

Open the [BI-Plateforme preview](https://saintlaurent00.github.io/superset/). If the site is unavailable, check the [GitHub Pages deployment workflow](https://github.com/saintLaurent00/superset/actions/workflows/deploy-pages-preview.yml) and the repository's [Pages settings](https://github.com/saintLaurent00/superset/settings/pages).

### Clone the repository

```bash
git clone https://github.com/saintLaurent00/superset.git
cd superset
git fetch origin
git switch bi-plateforme/page-by-page-theme
```

### Run the full Superset application

Apache Superset has a Python backend and a JavaScript/TypeScript frontend, along with specific development dependencies and setup requirements. Follow the official instructions rather than relying on the static preview:

- [Apache Superset documentation](https://superset.apache.org/)
- [Installation guide](https://superset.apache.org/docs/installation/installing-superset-from-scratch/)
- [Developer documentation](https://superset.apache.org/developer-docs/)
- [Contributing guide](https://github.com/apache/superset/blob/master/CONTRIBUTING.md)

Before submitting changes, run the relevant checks described by the upstream contributor documentation and any checks required by the pull request.

---

## Roadmap

The roadmap is intentionally iterative and may change as each screen is reviewed.

- [x] Establish a dedicated working branch for BI-Plateforme interface work.
- [x] Create an initial static preview for core BI navigation areas.
- [x] Add an automated GitHub Pages deployment workflow.
- [x] Apply the first scoped visual refinements to the dashboard list.
- [ ] Confirm and stabilize the GitHub Pages deployment.
- [ ] Validate the dashboard-list changes against the actual Superset frontend.
- [ ] Review responsive behaviour, keyboard navigation, focus visibility, and reduced motion.
- [ ] Refine the next page only after the current page is reviewed.
- [ ] Expand automated checks and document verified outcomes.

A checked item records implementation work, not necessarily a successful production release. Deployment and validation are tracked separately.

---

## About the maintainer

**Laurent Ouattara** — Software Engineer & Builder

I work across software engineering, data systems, AI, and security. I am interested in building useful, scalable technology and in making complex systems easier for people to understand and use.

BI-Plateforme is part of that direction: combining strong engineering foundations with a thoughtful, accessible interface for data exploration and decision-making, with a long-term interest in solutions that can create meaningful value in African contexts.

- **GitHub:** [@saintLaurent00](https://github.com/saintLaurent00)
- **BI-Plateforme project:** [github.com/saintLaurent00/BI-Plateforme](https://github.com/saintLaurent00/BI-Plateforme)
- **Upstream project:** [Apache Superset](https://github.com/apache/superset)

---

## Upstream project and acknowledgements

This work builds on [Apache Superset](https://github.com/apache/superset), an open-source business-intelligence platform maintained by its community and contributors.

Superset's original code, trademarks, documentation, and licensing notices remain subject to their respective terms. This personal fork is **not affiliated with, endorsed by, or an official distribution of the Apache Software Foundation**.

For the canonical product documentation, supported database details, release notes, and full upstream capabilities, consult the [official Apache Superset project](https://github.com/apache/superset).

## License

Apache Superset is distributed under the [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0). See the repository's license and notice files for the applicable terms and attributions.
