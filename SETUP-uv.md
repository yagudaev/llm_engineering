# LLM Engineering - Setup with uv

## Quick Setup with uv (Alternative to conda)

This is a faster, lighter alternative to the conda setup described in `SETUP-mac.md`.

### Prerequisites

1. **Install uv** (if not already installed):
   ```bash
   curl -LsSf https://astral.sh/uv/install.sh | sh
   ```

2. **Install Git** (if not already installed):
   ```bash
   git --version
   ```

### Setup Steps

1. **Clone the repository:**
   ```bash
   cd ~/Documents/Projects  # or your preferred projects directory
   git clone https://github.com/ed-donner/llm_engineering.git
   cd llm_engineering
   ```

2. **Install dependencies with uv:**
   ```bash
   uv sync --no-install-project
   ```
   This creates a virtual environment in `.venv/` and installs all required dependencies.

3. **Test the setup:**
   ```bash
   uv run jupyter lab --version
   ```
   You should see the version number (e.g., `4.4.7`).

### Running Jupyter Lab

To start Jupyter Lab:
```bash
cd /path/to/llm_engineering  # navigate to project directory
uv run jupyter lab
```

This will:
- Automatically activate the virtual environment
- Start Jupyter Lab in your browser
- Make all course dependencies available

### Environment Management

- **Check installed packages:** `uv pip list`
- **Add new packages:** `uv add package-name`
- **Run any Python script:** `uv run python script.py`
- **Activate shell with env:** `uv shell` (then use `jupyter lab` directly)

### API Keys Setup

Follow the same steps as in the main setup guide for creating your `.env` file with API keys:

```bash
# In the project root directory
nano .env
```

Add your keys:
```
OPENAI_API_KEY=your_key_here
ANTHROPIC_API_KEY=your_key_here
GOOGLE_API_KEY=your_key_here
# ... other keys as needed
```

### Why uv?

- **Faster:** Much quicker installation than conda
- **Lighter:** Uses less disk space
- **Modern:** Built with Rust, follows Python packaging standards
- **Compatible:** Works with the same dependencies as the conda setup

### Troubleshooting

If you encounter issues:
1. Ensure you're in the project directory when running commands
2. Try `uv sync --refresh` to rebuild the environment
3. For package conflicts, check `pyproject.toml` and update as needed

You can still follow all the course materials exactly as described - just use `uv run` prefix for any Python commands instead of activating conda.
