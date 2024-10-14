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

- `src/`
  - `backend/`: Contains the Flask backend code
    - `app/`: Core application code
    - `tests/`: Backend test files
    - `run.py`: Entry point for running the backend
  - `frontend/`: Contains the Next.js frontend code
    - `src/`: Frontend source code
    - `public/`: Static files
- `README.md`: Project documentation
- `pyproject.toml`: Python project configuration and dependencies
- `.gitignore`: Specifies files to be ignored by Git
- `.pre-commit-config.yaml`: Configuration for pre-commit hooks
- `LICENSE`: MIT License for the project

### Development Tools

1. **Black**: We use Black for Python code formatting. It's configured in the `pyproject.toml` file.

2. **Pre-commit**: We use pre-commit hooks to ensure code quality. The configuration is in `.pre-commit-config.yaml`.

3. **pytest**: For Python testing, we use pytest. The configuration is in `tests/pytest.ini`.

## Development

### Setting up the Backend

1. Install dependencies:
   ```
   poetry install
   ```

2. Set up environment variables:
   Create a `.env` file in the `src/backend` directory with the following content:
   ```
   SECRET_KEY=your-secret-key
   DATABASE_URL=postgresql://username:password@localhost/dbname
   ```
   Replace `your-secret-key`, `username`, `password`, and `dbname` with your actual values.

3. Initialize the database:
   ```
   cd src/backend
   poetry run flask db init
   poetry run flask db migrate -m "Initial migration"
   poetry run flask db upgrade
   ```

### Running the Backend

To run the Flask development server for the backend:

1. Navigate to the backend directory:
   ```
   cd src/backend
   ```

2. Start the Flask development server:
   ```
   poetry run python run.py
   ```

This will start your Flask application, typically accessible at `http://localhost:5000`.

### Project Structure

The backend follows this structure:

```
src/backend/
├── app/
│   ├── __init__.py
│   ├── main.py
│   └── config.py
├── tests/
├── run.py
└── .env
```

- `app/`: Contains the core application code
- `tests/`: Contains test files
- `run.py`: Entry point for running the application
- `.env`: Contains environment variables (not tracked in git)

### API Endpoints

- `GET /`: Returns a welcome message

## Frontend Development

The frontend of this project uses Next.js with TypeScript and Tailwind CSS.

### Setting up the Frontend

1. Navigate to the frontend directory:
   ```
   cd src/frontend
   ```

2. Install dependencies:
   ```
   npm install
   ```

3. Set up environment variables:
   Create a `.env.local` file in the `src/frontend` directory with any necessary environment variables.

### Running the Frontend

To start the Next.js development server:

1. Navigate to the frontend directory:
   ```
   cd src/frontend
   ```

2. Start the development server:
   ```
   npm run dev
   ```

This will start your Next.js application, typically accessible at `http://localhost:3000`.

### Frontend Structure

The frontend follows the standard Next.js structure:

- `src/app/`: Contains the application routes and components
- `src/components/`: Reusable React components
- `public/`: Static assets
- `tailwind.config.ts`: Tailwind CSS configuration
- `next.config.mjs`: Next.js configuration

## Getting Started

1. Clone the repository:
   ```
   git clone https://github.com/your-username/your-repo-name.git
   cd your-repo-name
   ```

2. Set up the backend:
   a. Navigate to the backend directory:
      ```
      cd src/backend
      ```
   b. Install Python dependencies:
      ```
      poetry install
      ```
   c. Set up environment variables:
      Create a `.env` file in the `src/backend` directory with the necessary environment variables.
   d. Initialize the database:
      ```
      poetry run flask db init
      poetry run flask db migrate -m "Initial migration"
      poetry run flask db upgrade
      ```

3. Set up the frontend:
   a. Navigate to the frontend directory:
      ```
      cd src/frontend
      ```
   b. Install Node.js dependencies:
      ```
      npm install
      ```
   c. Set up environment variables:
      Create a `.env.local` file in the `src/frontend` directory with any necessary environment variables.

4. Start the backend server:
   ```
   cd src/backend
   poetry run python run.py
   ```

5. In a new terminal, start the frontend development server:
   ```
   cd src/frontend
   npm run dev
   ```

6. Open your browser and visit `http://localhost:3000` to see the application running.

For more detailed instructions on setting up and running each part of the application, refer to the Backend Development and Frontend Development sections of this README.

## License

This project is open-source and available under the MIT License. See the `LICENSE` file for more details.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.
