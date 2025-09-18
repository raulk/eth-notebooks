# Ethereum Analysis Notebooks

A collection of Jupyter notebooks for analyzing Ethereum-related topics.

## Setup

### Prerequisites

- Python 3.13 or higher
- [uv](https://docs.astral.sh/uv/) package manager

### Install uv

```bash
# On macOS/Linux
curl -LsSf https://astral.sh/uv/install.sh | sh

# On Windows
powershell -c "irm https://astral.sh/uv/install.ps1 | iex"

# Alternative: using pip
pip install uv
```

### Project setup
```bash
# Clone and navigate to the project
cd eth-notebooks

# Install dependencies
uv sync

# Activate the virtual environment
source .venv/bin/activate  # On macOS/Linux
# or
.venv\Scripts\activate     # On Windows
```

## Running notebooks with Jupyter Lab

```bash
# With uv
uv run jupyter lab

# Or activate environment first
source .venv/bin/activate
jupyter lab
```

## Running notebooks with VS Code

Simply open the directory in Visual Studio Code with the relevant Python extensions.

### Available notebooks

- **[peerdas-bw-estimation.ipynb](peerdas-bw-estimation.ipynb)** - Bandwidth estimation analysis for PeerDAS and blob parameter optimization in the context of EIP-7892.

## Development

### Adding new dependencies

```bash
# Add a new package
uv add package-name

# Add development dependencies
uv add --group dev package-name
```
