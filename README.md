# PYTHON SETUP ON MAC FOR AI PROJECTS

````
# 🛠️ Mac Python Project Environment Setup Guide

## 1. Install Xcode Command Line Tools

```bash
xcode-select --install
````

---

## 2. Install pyenv

```bash
curl https://pyenv.run | bash
```

Add the following to your `~/.bash_profile`:

```bash
export PATH="$HOME/.pyenv/bin:$PATH:/usr/local/bin"
eval "$(pyenv init --path)"
eval "$(pyenv virtualenv-init -)"
```

Reload your shell:

```bash
source ~/.bash_profile
```

---

## 3. Install Python 3.12.3

```bash
pyenv install 3.12.3
```

---

## 4. Create a Parent Project Directory

```bash
mkdir -p ~/python
cd ~/python
```

---

## 5. Set the Python Version for All Subfolders

```bash
pyenv local 3.12.3
```

---

## 6. Create Your New Project Folder

```bash
mkdir my-first-project
cd my-first-project
```

---

## 7. Install Poetry (using pip)

```bash
pip install poetry
```

---

## 8. Initialize Poetry in the Project

```bash
poetry init
```

*Follow the prompts (skip dependencies if you want a minimal config).*

---

## 9. Configure pyproject.toml

Replace the contents of your `pyproject.toml` with:

```toml
[tool.poetry]
name = "my-first-project"
version = "0.1.0"
description = "A Stark-certified Python Poetry project"
authors = ["Tony Stark"]

[tool.poetry.dependencies]
python = "3.12.3"

[tool.poetry.group.dev.dependencies]
pytest = "*"

[build-system]
requires = ["poetry-core>=1.0.0"]
build-backend = "poetry.core.masonry.api"
```

---

## 10. Install Dependencies Without Installing the Root Project

```bash
poetry install --no-root
```

---

## 11. Activate the Poetry Virtual Environment

```bash
poetry shell
```

---

## 12. Test the Setup

Create a file named `main.py` with:

```python
print("Environment setup is successful!")
```

Run the script:

```bash
python main.py
```

You should see:

```
Environment setup is successful!
```

---

**You now have a clean, repeatable, professional Python environment on Mac — Stark-certified, ready for any project.**

```

*Just remove the very first and last triple backticks after pasting into GitHub and you’re golden, Mr. Stark!*  
Let me know if you want a short FAQ or troubleshooting below this block.
```
