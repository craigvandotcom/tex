# Cross-Platform Markdown Journal Application

## Development Environment Setup

### Python

This project uses Python 3.12.7. We recommend using pyenv for Python version management.

To set up Python with pyenv:

1. Install pyenv (if not already installed):
   ```
   brew install pyenv
   ```

2. Add pyenv to your shell:
   ```
   echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.zshrc
   echo 'command -v pyenv >/dev/null || export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.zshrc
   echo 'eval "$(pyenv init --path)"' >> ~/.zshrc
   echo 'eval "$(pyenv init -)"' >> ~/.zshrc
   ```

3. Restart your shell or run:
   ```
   source ~/.zshrc
   ```

4. Install Python 3.12.7:
   ```
   pyenv install 3.12.7
   ```

5. Set the local Python version for this project:
   ```
   pyenv local 3.12.7
   ```

6. Verify the installation:
   ```
   python --version
   ```

This should output: Python 3.12.7

Now you have the correct Python version set up for this project using pyenv.
