# Cloud Architect Lab CLI (cal)

The Cloud Architect Lab CLI (`cal`) is a command-line tool that standardizes the creation, documentation, and publication of Cloud Architect Lab case studies.

Rather than recreating project structures and documentation by hand, `cal` automates repetitive tasks so development effort can remain focused on architecture, implementation, and learning.

---

## Vision

Cloud Architect Lab is built on the philosophy of **Architecture as Code**.

Infrastructure, diagrams, documentation, architecture decisions, and project artifacts should all be version-controlled and treated as first-class engineering assets.

The `cal` CLI exists to automate that workflow.

---

## Current Features

### `cal new`

Creates a new Cloud Architect Lab project with the standard repository structure.

```bash
cal new my-project
```

Generates:

```text
my-project/
├── terraform/
├── diagrams/
│   ├── source/
│   └── exported/
├── docs/
│   ├── notes/
│   ├── adr/
│   ├── architecture.md
│   ├── decisions.md
│   ├── deployment.md
│   ├── lessons-learned.md
│   └── validation.md
├── screenshots/
├── LICENSE
├── README.md
└── .gitignore
```

The command also:

- Initializes a Git repository
- Sets the default branch to `main`
- Creates an initial commit
- Generates a project README, MIT license, and starter documentation
- Adds minimal YAML metadata to generated Markdown documents

### Document metadata

Generated Markdown documents begin with YAML front matter:

```yaml
---
document_type: architecture
authority_class: descriptive
status: draft
---
```

The fields provide lightweight, human-readable classification:

- `document_type` identifies the document's role in a CAL case study.
- `authority_class` identifies how the document should be interpreted, such as descriptive, decisional, or evidentiary.
- `status` records its lifecycle state; generated documents begin as `draft`.

Keep the metadata at the top of each generated document and update `status` as the document evolves. The convention is intentionally minimal: it makes scaffolded artifacts self-describing and provides a future hook for richer metadata automation without making that automation part of the current CLI.

---

## Planned Features

- Interactive project creation
- Architecture Decision Record generation
- Mermaid diagram templates
- Terraform project scaffolding
- Environment validation (`cal doctor`)
- Case study website scaffolding
- Publishing workflow automation

---

## Roadmap
---

CAL CLI is intended to become the standard project generator and automation tool for Cloud Architect Lab.

## Phase 1 – Foundation ✅

- Create standard Cloud Architect Lab repository structure
- Generate documentation folders
- Generate diagrams folders
- Generate Terraform folders

---

## Phase 2 – Project Templates ✅

Generate documentation from reusable templates.

Implemented:

- Populate README.md from a standard template
- Generate architecture.md
- Generate deployment.md
- Generate decisions.md
- Generate validation.md
- Generate lessons-learned.md
- Add minimal YAML metadata to generated Markdown documents

---

## Phase 3 – Terraform Scaffolding

Generate reusable Terraform starter files.

Planned files:

- versions.tf
- providers.tf
- variables.tf
- main.tf
- outputs.tf
- terraform.tfvars.example

Starter files will eventually include:

- Terraform version constraints
- AWS provider configuration
- Standard variables
- Standard tagging strategy
- Placeholder outputs

---

## Phase 4 – Project Types

Support specialized project generators.

Examples:

```bash
cal new networking
cal new vpc-peering
cal new ecs
cal new serverless
cal new snowflake
cal new multi-cloud
```

Each generator will create a tailored project structure, Terraform scaffolding, documentation templates, and architecture assets.

---

## Phase 5 – Automation

Future automation ideas include:

- Validate Terraform
- Render Mermaid diagrams
- Export SVG architecture diagrams
- Generate documentation indexes
- Initialize Git repositories
- Create GitHub repositories
- Push initial commits
- Run Terraform plan
- Run Terraform apply (optional)

The long-term vision is for CAL CLI to become the opinionated project generator that standardizes Infrastructure as Code, Architecture as Code, documentation, and publishing across every Cloud Architect Lab project.
---

## Philosophy

Standardize the process so creativity is spent on architecture—not setup.
