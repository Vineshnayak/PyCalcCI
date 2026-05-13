# PyCalcCI

A simple calculator web application built with Python and Flask, integrated with a Jenkins CI/CD pipeline for automated testing and deployment.

## Overview

PyCalcCI is a web-based calculator that performs basic arithmetic operations (addition, subtraction, multiplication, division) through a browser interface. The project includes a full Jenkins pipeline that automates code checkout, dependency installation, testing, and application startup.

## Tech Stack

- **Backend:** Python, Flask
- **Testing:** pytest
- **CI/CD:** Jenkins (Declarative Pipeline)
- **Template Engine:** Jinja2

## Project Structure

```
PyCalcCI/
├── app.py                 # Flask application entry point
├── calculator.py          # Core arithmetic functions
├── test_calculator.py     # Unit tests for calculator module
├── Jenkinsfile            # Jenkins pipeline configuration
├── requirements.txt       # Python dependencies
├── templates/
│   └── index.html         # Web UI template
├── .gitignore
└── README.md
```

## Getting Started

### Prerequisites

- Python 3.x
- pip

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/Vineshnayak/PyCalcCI.git
   cd PyCalcCI
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Run the application:
   ```bash
   python app.py
   ```

4. Open `http://127.0.0.1:5000` in your browser.

### Running Tests

```bash
python -m pytest
```

## CI/CD Pipeline

The project includes a `Jenkinsfile` with a four-stage pipeline:

| Stage                  | Description                                  |
|------------------------|----------------------------------------------|
| Checkout Code          | Pulls the latest code from the `main` branch |
| Install Dependencies   | Installs packages from `requirements.txt`    |
| Run Tests              | Executes the pytest test suite                |
| Run Flask App          | Starts the Flask server in the background     |

### Pipeline Setup

1. Create a new Pipeline job in Jenkins.
2. Point it to this repository's `Jenkinsfile`.
3. Optionally configure a GitHub webhook for automatic builds on push.

## Calculator Module

The `calculator.py` module exposes four functions:

- `add(a, b)` — Returns the sum of two numbers.
- `subtract(a, b)` — Returns the difference.
- `multiply(a, b)` — Returns the product.
- `divide(a, b)` — Returns the quotient. Raises `ValueError` if the divisor is zero.

## License

This project is for educational and learning purposes.
