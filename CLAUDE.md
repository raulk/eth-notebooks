# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is an Ethereum research repository focused on bandwidth analysis for PeerDAS and blob parameter optimization (EIP-7892). The project uses Jupyter notebooks for interactive data analysis and visualization.

## Development Commands

### Setup and Running
```bash
# Install dependencies
uv sync

# Run Jupyter Lab
uv run jupyter lab

# Alternative: activate venv first
source .venv/bin/activate  # Linux/macOS
jupyter lab
```

### Dependency Management
```bash
# Add new packages
uv add package-name

# Add to notebook directly (within notebook cell)
!uv add package-name
```

## Architecture and Structure

### Main Components

1. **peerdas-bw-estimation.ipynb**: Core analysis notebook containing:
   - EIP-7870 and EIP-7892 bandwidth constants
   - PeerDAS custody scenarios and calculations
   - Bandwidth requirement functions
   - Network stress testing simulations
   - Visualization generation using plotly

### Key Analysis Functions

The notebook implements several critical calculation functions:
- `calculate_bandwidth_requirements()`: Computes upload/download bandwidth for given blob parameters, supporting both full blob propagation and PeerDAS column-based distribution
- `check_node_compatibility()`: Validates if a node type can handle specific bandwidth requirements

### Important Constants

- **BYTES_PER_BLOB**: 131072 (128 KiB)
- **SECONDS_PER_SLOT**: 12
- **NUMBER_OF_COLUMNS**: 128 (PeerDAS DAS matrix)
- **GOSSIP_OVERHEAD**: 1.5 (50% overhead for gossip propagation)

### Visualization Patterns

All visualizations use plotly with dark theme (`plotly_dark`) as default. Key plot types include:
- Bandwidth requirement comparisons
- Node compatibility matrices
- Monthly data transfer estimates
- Scaling analysis charts

## Development Notes

### Python Version
This project requires Python 3.13 (specified in `.python-version`)

### Package Manager
Uses `uv` for dependency management instead of pip/conda. All dependencies are locked in `uv.lock`.

### Notebook Structure
The analysis notebook follows a structured approach:
1. Constants and configuration
2. Calculation functions
3. Scenario simulations
4. Visualization generation
5. Summary and recommendations

When modifying calculations, ensure consistency across all dependent visualizations and summary sections.