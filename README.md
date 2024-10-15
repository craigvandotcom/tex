# Cross-Platform Markdown Journal

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python Version](https://img.shields.io/badge/python-3.12.7-blue.svg)](https://www.python.org/downloads/release/python-3127/)
[![TypeScript Version](https://img.shields.io/badge/typescript-5.x-blue.svg)](https://www.typescriptlang.org/)

A cross-platform markdown journal application built with Python (Flask) backend and TypeScript (Next.js) frontend.

[Include a GIF or screenshot of your application here]

## Features

- Cross-platform support (Web, Desktop, Mobile)
- Markdown support for journal entries
- Secure user authentication
- Offline-first architecture
- Data synchronization across devices

## Technologies Used

- Backend: Python, Flask, SQLAlchemy
- Frontend: TypeScript, Next.js, Tailwind CSS
- Mobile/Desktop: Capacitor, Electron

## Installation

### Prerequisites

- Python 3.12.7
- Node.js 18+
- PostgreSQL

### Backend Setup

1. Clone the repository:
   ```
   git clone https://github.com/your-username/your-repo-name.git
   cd your-repo-name/src/backend
   ```

2. Set up a virtual environment and install dependencies:
   ```
   poetry install
   ```

3. Set up environment variables:
   Create a `.env` file in the `src/backend` directory with the following content:
   ```
   SECRET_KEY=your-secret-key
   DATABASE_URL=postgresql://username:password@localhost/dbname
   ```

4. Initialize the database:
   ```
   poetry run flask db upgrade
   ```

### Frontend Setup

1. Navigate to the frontend directory:
   ```
   cd ../frontend
   ```

2. Install dependencies:
   ```
   npm install
   ```

3. Create a `.env.local` file with necessary environment variables.

## Usage

1. Start the backend server:
   ```
   cd src/backend
   poetry run python run.py
   ```

2. In a new terminal, start the frontend development server:
   ```
   cd src/frontend
   npm run dev
   ```

3. Open your browser and visit `http://localhost:3000`.

## API Reference

[Provide a brief overview of your API endpoints or link to full documentation]

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contact

Craig van der Merwe - [@craigvandotcom](https://twitter.com/craigvandotcom)

Project Link: [https://github.com/craigvandotcom/tex](https://github.com/craigvandotcom/tex)

## Cloud Setup

This project is configured to use AWS by default, but can be adapted for other cloud providers.

### AWS Setup

1. Install the AWS CLI:
   ```
   pip install awscli
   ```

2. Configure AWS credentials:
   ```
   aws configure
   ```
   Enter your AWS Access Key ID, Secret Access Key, and preferred region when prompted.

3. Install Boto3:
   ```
   poetry add boto3
   ```

4. Update your `.env` file with AWS-specific variables:
   ```
   AWS_ACCESS_KEY_ID=your_access_key_here
   AWS_SECRET_ACCESS_KEY=your_secret_key_here
   AWS_DEFAULT_REGION=your_preferred_region
   ```

### Alternative Cloud Providers

While this project is set up for AWS, you can adapt it to use other cloud providers:

- **Google Cloud Platform (GCP)**:
  - Install the Google Cloud SDK
  - Use the `google-cloud-storage` library for Python
  - Update environment variables for GCP credentials

- **Microsoft Azure**:
  - Install the Azure CLI
  - Use the `azure-storage-blob` library for Python
  - Update environment variables for Azure credentials

- **DigitalOcean**:
  - Install the DigitalOcean CLI (doctl)
  - Use the `boto3` library with DigitalOcean Spaces (S3-compatible)
  - Update environment variables for DigitalOcean credentials

To switch providers, you'll need to modify the cloud interaction code in the backend and update the corresponding environment variables.

## Environment Variables

Create a `.env` file in the project root with the following variables:

```
# Flask
SECRET_KEY=your_secret_key_here
DATABASE_URL=postgresql://username:password@localhost/dbname

# AWS (or your chosen cloud provider)
AWS_ACCESS_KEY_ID=your_access_key_here
AWS_SECRET_ACCESS_KEY=your_secret_key_here
AWS_DEFAULT_REGION=your_preferred_region

# Electron
ELECTRON_START_URL=http://localhost:3000
```

Ensure that `.env` is listed in your `.gitignore` file to keep sensitive information out of version control.
