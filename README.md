# Cross-Platform Markdown Journal Application

This open-source project aims to create a cross-platform markdown journal application. The project uses a combination of Python for the backend and TypeScript for the frontend.

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

### Poetry

We use Poetry for Python dependency management. To set up Poetry:

1. Install Poetry (if not already installed):
   ```
   curl -sSL https://install.python-poetry.org | python3 -
   ```

2. Initialize a new Poetry project:
   ```
   poetry init
   ```

3. Install project dependencies:
   ```
   poetry install
   ```

### TypeScript

The frontend of this project uses TypeScript. To set up the TypeScript environment:

1. Initialize a new Node.js project:
   ```
   npm init -y
   ```

2. Install TypeScript and other dev dependencies:
   ```
   npm install --save-dev typescript @types/node ts-node
   ```

3. Create a `tsconfig.json` file for TypeScript configuration:
   ```
   npx tsc --init
   ```

4. Update the `tsconfig.json` file with the following configuration:

   ```json
   {
     "compilerOptions": {
       "target": "es6",
       "module": "commonjs",
       "strict": true,
       "esModuleInterop": true,
       "skipLibCheck": true,
       "forceConsistentCasingInFileNames": true,
       "outDir": "./dist",
       "rootDir": "./src"
     },
     "include": ["src/**/*"],
     "exclude": ["node_modules"]
   }
   ```

### Project Structure

The project is structured as follows:

- `src/`: Contains the TypeScript source code for the frontend
- `tests/`: Contains Python test files
- `README.md`: Project documentation
- `pyproject.toml`: Python project configuration and dependencies
- `package.json`: Node.js project configuration and dependencies
- `tsconfig.json`: TypeScript configuration
- `.gitignore`: Specifies files to be ignored by Git
- `.pre-commit-config.yaml`: Configuration for pre-commit hooks
- `LICENSE`: MIT License for the project

### Development Tools

1. **Black**: We use Black for Python code formatting. It's configured in the `pyproject.toml` file.

2. **Pre-commit**: We use pre-commit hooks to ensure code quality. The configuration is in `.pre-commit-config.yaml`.

3. **pytest**: For Python testing, we use pytest. The configuration is in `tests/pytest.ini`.

## Getting Started

1. Clone the repository
2. Set up the Python environment as described above
3. Install Python dependencies: `poetry install`
4. Install Node.js dependencies: `npm install`
5. Run Python tests: `poetry run pytest`
6. Build TypeScript: `npm run build`
7. Start the development server: `npm run dev`

## License

This project is open-source and available under the MIT License. See the `LICENSE` file for more details.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.