# PYTHON SETUP ON MAC FOR AI PROJECTS

# 🛠️ Mac Python Project Environment Setup Guide
# (Stark-Certified — copy everything, paste into a file, then delete these outer triple-backticks)

# 1 ▪ Install Xcode Command Line Tools
xcode-select --install

# ------------------------------------------------------------

# 2 ▪ Install pyenv
curl https://pyenv.run | bash

# ➜  Add these lines to ~/.bash_profile
export PATH="$HOME/.pyenv/bin:$PATH:/usr/local/bin"
eval "$(pyenv init --path)"
eval "$(pyenv virtualenv-init -)"

# ➜  Reload shell
source ~/.bash_profile

# ------------------------------------------------------------

# 3 ▪ Install Python 3.12.3
pyenv install 3.12.3

# ------------------------------------------------------------

# 4 ▪ Create parent projects folder and enter it
mkdir -p ~/python
cd ~/python

# ------------------------------------------------------------

# 5 ▪ Set Python 3.12.3 for ALL sub-projects
pyenv local 3.12.3

# ------------------------------------------------------------

# 6 ▪ Create a new project folder and enter it
mkdir my-first-project
cd my-first-project

# ------------------------------------------------------------

# 7 ▪ Install Poetry (using pip from Python 3.12.3)
pip install poetry

# ------------------------------------------------------------

# 8 ▪ Initialize Poetry (minimal prompts)
poetry init  --no-interaction

# ------------------------------------------------------------

# 9 ▪ Overwrite pyproject.toml with Stark template
cat > pyproject.toml <<'EOF'
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
EOF

# ------------------------------------------------------------

# 10 ▪ Install dependencies (without installing the package itself)
poetry install --no-root

# ------------------------------------------------------------

# 11 ▪ Activate the Poetry virtual environment
poetry shell

# ------------------------------------------------------------

# 12 ▪ Test the setup
echo 'print("Environment setup is successful!")' > main.py
python main.py   # ➜ should output →  Environment setup is successful!

# ------------------------------------------------------------
# 🎉  Mac environment ready — repeatable, clean, professional.  🎉
