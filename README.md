# PatSnap Agent Skills

This repository contains PatSnap procedural knowledge skills for AI agents. The skills cover intellectual property, R&D and engineering analysis, pharmaceutical and biomedical intelligence, and materials science.

Each skill is a self-contained directory with a required `SKILL.md` file and optional bundled resources such as `references/`, `scripts/`, `assets/`, `templates/`, and `agents/`.

## Installation

Install all skills from one domain:

```bash
npx skills add patsnap/skills/tree/main/ip --all
npx skills add patsnap/skills/tree/main/engineering --all
npx skills add patsnap/skills/tree/main/life-sciences --all
npx skills add patsnap/skills/tree/main/materials --all
```

Install one skill:

```bash
npx skills add patsnap/skills/tree/main/ip/free-patent-search
```

## Structure

```text
skills/
├── engineering/          # R&D, technology analysis, innovation, industry and product workflows
├── ip/                   # Patent search, IP risk, FTO, portfolio, transfer and patent-operation workflows
├── life-sciences/        # Pharmaceutical, biomedical and patent intelligence workflows
├── materials/            # Materials science, technology scouting and alloy composition workflows
├── package.json
└── README.md
```

## Repository Snapshot

| Domain | Directory | Skill directories | Notes |
|---|---:|---:|---|
| Engineering / R&D | `engineering/` | 36 | Includes the original R&D analysis skills plus Skill Hub imports for reports, TRIZ, industry intelligence, due diligence, technical forecasting and product/market workflows. |
| IP / Patent Intelligence | `ip/` | 54 | Includes patent search, FTO support, patent quality review, patent mining, asset operation, portfolio analysis, legal-risk screening and technology-transfer workflows. |
| Life Sciences | `life-sciences/` | 16 | Includes original pharma intelligence skills plus imported generic-drug, ADC, antibody FTO and target-discovery workflows. |
| Materials | `materials/` | 10 | Includes materials explanation, technology scouting, problem solving, product translation and alloy composition search skills. |

## Skill Hub Imports

The 2026-06-30 Skill Hub batch has been normalized into the existing domain directories:

| Domain | Imported skills |
|---|---:|
| `engineering/` | 27 |
| `ip/` | 52 |
| `life-sciences/` | 4 |
| Total unique imported skill directories | 83 |

Two source records shared the same target skill directory and were intentionally collapsed by canonical skill name:

| Target skill | Source records |
|---|---|
| `engineering/tech-insight-report` | `SKILL-0009`, `SKILL-0084` |
| `ip/patent-quality-review-pro` | `SKILL-0038`, `SKILL-0082` |

The generated upload/index metadata is available locally at `outputs/skill.json` when the import-preparation outputs are present. It includes `skill_name`, `github_url`, `description`, domain, path and `SKILL.md` file location for the newly imported skills.

## Core Skills

### Engineering

General-purpose R&D analysis skills. Several core skills are available in English and Chinese (`-zhcn` suffix).

| Skill | Description |
|---|---|
| `company-tech-profile` | Single-company technology profile and R&D assessment for a defined technology topic. |
| `competitive-landscape` | Technology-sector competitive landscape analysis with player tiering and white-space identification. |
| `tech-route-comparison` | Evidence-backed comparison of technical routes, architectures or solution paths. |
| `rd-initiation-review` | R&D project initiation pre-screen and proposal audit for go/no-go decisions. |
| `triz-innovation-pro` | TRIZ innovation solution analysis with component, contact, functional and causal-chain workflows. |

### IP

Patent search and IP analysis skills powered by PatSnap data and related product workflows.

| Skill | Description |
|---|---|
| `free-patent-search` | Patent search powered by PatSnap's free MCP, covering novelty search, FTO analysis, competitive intelligence, legal-status checks and portfolio research. |

### Life Sciences

Pharmaceutical and biomedical intelligence skills. The original six skills integrate with PatSnap LifeScience MCP services and are available in English and Chinese (`-zhcn` suffix).

| Skill | Description |
|---|---|
| `biomarker-investigation` | Search academic and patent literature related to biomarkers. |
| `company-profiling` | Pharmaceutical company profiles and investment/collaboration recommendations. |
| `disease-investigation` | Disease investigation combining literature, epidemiology, clinical data and pharma intelligence. |
| `pharmaceuticals-exploration` | Drug-related Q&A covering patents, literature, clinical trials and licensing transactions. |
| `precision-oncology` | Cancer treatment reports combining literature, clinical guidance and trial data. |
| `target-intelligence` | Biomedical target analysis with biological and pharmaceutical details. |

### Materials

Materials science and engineering skills for metals, polymers, ceramics, composites and energy materials.

| Skill | Description | MCP |
|---|---|---|
| `understand-technology` | Explain materials science concepts, structure-property relationships and processing methods. | - |
| `scout-tech-landscape` | Analyze technology landscapes including value chains, key players and R&D trends. | - |
| `solve-tech-problems` | Solution-oriented analysis for materials engineering challenges. | - |
| `tech-to-product` | Translate materials technologies into real-world products and systems. | - |
| `alloy-composition-search` | Search, filter and analyze alloy compositions from structured data and patent sources. | `mace-mcp` |

## MCP Dependencies

Some skills rely on external MCP servers for retrieval. Skills without MCP dependencies can still operate from user-provided context, bundled references, public sources or model reasoning, subject to the limits described in each `SKILL.md`.

| MCP Server / Tooling | Domain | Used By | Capabilities |
|---|---|---|---|
| PatSnap LifeScience MCP | Life Sciences | Original life-sciences skills and some imported biomedical workflows | Drugs, targets, diseases, biomarkers, companies, patents, papers, clinical trials and related pharma intelligence. |
| PatSnap / Zhihuiya patent MCP | IP, Engineering, Life Sciences | Many imported patent, FTO, portfolio, transfer and competitive-intelligence skills | Patent retrieval, applicant/topic search, legal status, patent evidence collection and workflow-specific analysis. |
| `mace-mcp` | Materials | `alloy-composition-search` | Alloy composition extraction: `query_to_alloy` -> `alloy_to_substance` -> `substance_to_document` -> `document_to_alloy`. |

## Naming And Language

- Skill directory names use lowercase hyphen-case and should match the `name` field in `SKILL.md`.
- Chinese skill variants use the `-zhcn` suffix when they are a translated counterpart of an English base skill.
- Imported Skill Hub skills are mostly Chinese-first workflows and keep their canonical technical names as directory names.
- Each `SKILL.md` front matter should include only `name` and `description` unless a host-specific format explicitly requires otherwise.
