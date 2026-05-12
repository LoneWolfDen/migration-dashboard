# Migration Assessment Dashboard

AWS Cloud Migration Assessment tool for AnyCompany — interactive dashboard with Gantt chart, NFR gates, dependency diagrams, and AI chat agent.

## Project Structure

```
sample_input/
├── pyproject.toml              # Project config, dependencies, tool settings
├── README.md
├── server.py                   # Original server (runs from root)
├── migration_dashboard/        # Main package
│   ├── __init__.py
│   ├── server.py              # Dashboard server (restructured)
│   ├── stories_data.py        # Story definitions with t-shirt sizing
│   ├── gates_data.py          # NFR gate matrix
│   ├── data/                  # CSV data files
│   │   ├── migration_epic_plan.csv
│   │   ├── migration_nfr_requirements.csv
│   │   ├── migration_operational_tracking.csv
│   │   └── migration_resource_plan.csv
│   ├── diagrams/              # draw.io diagram files
│   │   ├── migration_dependency_diagram.drawio
│   │   ├── data_flow_diagram.drawio
│   │   └── operational_dependency_diagram.drawio
│   └── agents/                # Strands AI agents
│       ├── migration_assessment_agent.py
│       ├── architecture_review_agent.py
│       └── business_case_review_agent.py
├── tests/                     # Test suite
│   ├── conftest.py            # Shared fixtures
│   ├── test_data_integrity.py # CSV data validation
│   ├── test_stories_gates.py  # Stories & gates validation
│   └── test_server.py         # Server & HTML generation tests
└── sample_data/               # Source data (input to agents)
```

## Quick Start

```bash
# Run the dashboard (from sample_input/)
python server.py
# Open http://localhost:8888

# Run tests
pytest tests/ -v

# Run from restructured package
python migration_dashboard/server.py
```

## Features

- **Gantt Chart**: Interactive, collapsible epics → roles → stories with progress tracking
- **NFR Gates**: Dependency matrix showing which NFRs block which stories
- **Dependencies**: Interactive SVG with click-to-highlight
- **Data Flow**: App-to-database relationship diagram
- **Diagram Editor**: Embedded draw.io editor for full editing
- **Chat Agent**: Amazon Nova Pro powered Q&A about the migration plan
- **Change Log**: Track scope changes with impact analysis
- **Progress Tracking**: Mark stories done, track actual vs planned hours

## Running Tests

```bash
pytest tests/ -v
pytest tests/ --cov=migration_dashboard
```
