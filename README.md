# PYTHON SETUP ON MAC FOR AI PROJECTS

# 1. Check/Install Xcode Command Line Tools (skip if already installed)
xcode-select --install

# 2. Install pyenv (if not already installed)
curl https://pyenv.run | bash

# 3. Add pyenv to PATH and initialize (add to ~/.bash_profile)
echo 'export PATH="$HOME/.pyenv/bin:$PATH:/usr/local/bin"' >> ~/.bash_profile
echo 'eval "$(pyenv init --path)"' >> ~/.bash_profile
echo 'eval "$(pyenv virtualenv-init -)"' >> ~/.bash_profile

# 4. Reload your bash profile
source ~/.bash_profile

# 5. Install Python 3.12.3
pyenv install 3.12.3

# 6. Create a parent folder for all your Python projects (if it doesn't exist)
mkdir -p ~/python
cd ~/python

# 7. Set Python version locally for all subfolders
pyenv local 3.12.3

# 8. Create your project directory and enter it
mkdir my-first-project
cd my-first-project

# 9. Install Poetry using pip from your current Python
pip install poetry

# 10. Initialize Poetry (skip dependency prompts for a minimal setup)
poetry init

# 11. Edit pyproject.toml (open and replace the contents as shown below)
cat > pyproject.toml <<EOF
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

# 12. Install dependencies (no-root, just to get started)
poetry install --no-root

# 13. Activate Poetry shell
poetry shell

# 14. Test: Create a main.py file and run it
echo 'print("Environment setup is successful!")' > main.py
python main.py

# ====
# Your Mac is now ready for any Python+Poetry project.
# To add dependencies, just use: poetry add package-name
# ====

