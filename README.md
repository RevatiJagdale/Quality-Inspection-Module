### Quality Inspection Module

Built on the **Frappe Framework**, this module replaces manual, paper-based systems for quality assurance with a centralized, automated workflow.
In large-scale manufacturing, maintaining a physical Production History Card leads to data silos and a lack of real-time traceability. Quality Inspection Module digitizes the entire product lifecycle—from pre-assembly and machining to final Pre-Delivery Inspection (PDI).

### Features

* **Dynamic Checklist Mapping:** Automatically assigns specific inspection formats based on product type or model.
* **Unified Digital Passport:** Consolidates document scanning, rotor balancing logs, and assembly check sheets into one record.
* **Validation Gates:** Implements "Pass/Reject" logic to prevent non-compliant products from moving to the next production stage.
* **Multimedia Integration:** Supports mandatory photo uploads and document attachments directly from the shop floor via tablet-optimized interfaces.
* **Admin-Centric Control:** Empowers internal administrators to modify, add, or delete inspection points without external developer intervention.

1. Custom Doctypes
Modified and extended standard ERPNext manufacturing and quality schemas to include:
* **Balancing Logbook:** Captures technical parameters for rotating components.
* **Assembly Check Sheet:** Multi-stage digital sign-offs for assembly line operators.
* **PDI Inspection:** Final quality gate with mandatory photo evidence and timestamping.

2. Logic & Workflows
* **Annexure Logic:** A custom engine that maps specific quality formats to distinct product categories.
* **Traceability:** Full audit trails ensuring every entry is linked to a specific Sales Order (SO) and User ID.

Usage

1.  **Configuration:** Navigate to the Quality Inspection Settings to map product types to specific inspection formats.
2.  **Execution:** Operators on the floor select the active Sales Order; the system automatically renders the correct digital checklist.
3.  **Validation:** Quality Managers review the submitted digital "Passport" before authorizing the final dispatch status.

### Installation

You can install this app using the [bench](https://github.com/frappe/bench) CLI:

```bash
cd $PATH_TO_YOUR_BENCH
bench get-app $URL_OF_THIS_REPO 
bench --site [site-name] install-app ierp_quality_module
```

### Contributing

This app uses `pre-commit` for code formatting and linting. Please [install pre-commit](https://pre-commit.com/#installation) and enable it for this repository:

```bash
cd apps/ierp_quality_module
pre-commit install
```

Pre-commit is configured to use the following tools for checking and formatting your code:

- ruff
- eslint
- prettier
- pyupgrade
### CI

This app can use GitHub Actions for CI. The following workflows are configured:

- CI: Installs this app and runs unit tests on every push to `develop` branch.
- Linters: Runs [Frappe Semgrep Rules](https://github.com/frappe/semgrep-rules) and [pip-audit](https://pypi.org/project/pip-audit/) on every pull request.


### License

mit
