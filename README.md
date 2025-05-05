# Job Signal Analyzer

A sophisticated DevSecOps project that analyzes job postings to identify high-quality engineering opportunities based on signal detection rather than simple keyword matching.

## Project Overview

Job Signal Analyzer helps experienced engineers cut through the noise of vague job listings to find positions that truly match their skills and interests. It differentiates between roles that offer genuine design and engineering challenges versus those that primarily involve maintenance or have unclear responsibilities.

### The Problem

Senior technical professionals waste significant time filtering through job postings that are:
- Vague about actual responsibilities
- Filled with buzzwords but light on technical substance
- Disguising maintenance roles as engineering positions
- Missing concrete information about the actual work and technologies

Traditional job boards only match keywords, not the *quality* of the position or the nature of the work.

### The Solution

This project implements a sophisticated analysis system that evaluates job listings beyond simple keyword matching to identify high-quality engineering opportunities that involve actual design work and technical challenges.

## Features

- **Data Collection**: Integration with public job APIs (LinkedIn, Indeed, etc.)
- **Content Analysis**: Detection of positive and negative signals in job descriptions
- **Quality Scoring**: Multi-dimensional evaluation of job quality based on configurable heuristics
- **Result Dashboard**: Visual presentation of filtered and scored job listings
- **Trend Analysis**: Tracking of positions and market trends over time

## Architecture

![Architecture Diagram](./docs/images/architecture.png)

The system consists of:

1. **Data Collection Pipeline**: Scheduled collection from public job APIs
2. **Analysis Engine**: Rule-based and ML-powered signal detection
3. **Storage Layer**: Structured and unstructured data storage
4. **User Interface**: Streamlit-based dashboard for results exploration
5. **DevSecOps Pipeline**: Complete CI/CD integration with security controls

## DevSecOps Implementation

This project demonstrates staff-level DevSecOps practices:

### Development
- Modular Python codebase with clear separation of concerns
- Comprehensive test coverage with pytest
- Configuration management for flexible deployment

### Security
- Dependency vulnerability scanning
- Container security scanning
- Static code analysis
- Secrets management
- Least privilege IAM implementation

### Operations
- Infrastructure as Code using Terraform
- Containerized deployment with Docker
- CI/CD pipeline with GitHub Actions
- Monitoring and logging integration
- Automated backup and recovery

## Getting Started

### Prerequisites

- Python 3.9+
- AWS Account
- Docker and Docker Compose
- Terraform (optional, for IaC deployment)

### Local Development Setup

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/job-signal-analyzer.git
   cd job-signal-analyzer
   ```

2. Set up a virtual environment:
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   pip install -r requirements.txt
   pip install -r dev-requirements.txt
   ```

3. Set up pre-commit hooks:
   ```bash
   pre-commit install
   ```

4. Create a `.env` file with required configuration:
   ```
   # API Keys
   LINKEDIN_API_KEY=your_key_here
   INDEED_API_KEY=your_key_here
   
   # Database
   DB_CONNECTION_STRING=sqlite:///jobs.db
   
   # AWS (for deployment)
   AWS_REGION=us-east-1
   ```

5. Run the local development server:
   ```bash
   python -m app.main
   ```

### Docker Development

1. Build and run with Docker Compose:
   ```bash
   docker-compose up --build
   ```

2. Access the application at http://localhost:8501

## Deployment

### AWS Deployment with Terraform

1. Navigate to the terraform directory:
   ```bash
   cd terraform
   ```

2. Initialize Terraform:
   ```bash
   terraform init
   ```

3. Apply the configuration:
   ```bash
   terraform apply
   ```

### Manual Deployment

1. Build the Docker image:
   ```bash
   docker build -t job-signal-analyzer .
   ```

2. Push to your container registry:
   ```bash
   docker tag job-signal-analyzer:latest your-registry/job-signal-analyzer:latest
   docker push your-registry/job-signal-analyzer:latest
   ```

3. Deploy to your infrastructure using the provided scripts in `deploy/`

## Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/amazing-feature`
3. Commit your changes: `git commit -m 'Add amazing feature'`
4. Push to the branch: `git push origin feature/amazing-feature`
5. Open a pull request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- All the job seekers who have experienced the frustration of vague job listings
- The open-source community for the tools that make this project possible# jobfinder
