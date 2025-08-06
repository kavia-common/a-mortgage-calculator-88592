# A Mortgage Calculator

A simple, user-friendly mortgage calculator application built in Java. Supports both a desktop GUI and a command-line interface (CLI) for calculating monthly payments, total payments, and generating a yearly amortization schedule.

## Table of Contents

- [Project Overview](#project-overview)
- [Features](#features)
- [Requirements](#requirements)
- [Setup & Installation](#setup--installation)
- [Building the Application](#building-the-application)
- [Usage](#usage)
  - [GUI Version](#gui-version)
  - [Command-line Version](#command-line-version)
  - [Sample Usage Walkthroughs](#sample-usage-walkthroughs)
- [Development](#development)
- [Continuous Integration](#continuous-integration)
- [Contribution Guidelines](#contribution-guidelines)
- [License](#license)
- [Acknowledgements](#acknowledgements)

---

## Project Overview

This application helps users calculate mortgage payments and review amortization schedules. It is implemented in Java, features a rich desktop graphical interface (using Swing), and an alternative CLI. Designed with modularity and clean code in mind, it makes use of Java 8 features and follows best practices for open-source collaboration.

## Features

- Calculate monthly mortgage payments given amount, rate, and term
- View aggregate total payment, total interest, and a breakdown schedule
- Yearly amortization schedule shown in both CLI and GUI
- Input validation with clear error handling
- Clean and intuitive desktop GUI
- CLI for fast terminal-based calculation
- Modular source code for easy further development

## Requirements

- Java 8 or higher
- Maven 3.6 or higher

## Setup & Installation

1. **Clone this repository**:
    ```sh
    git clone <your_repo_url>
    cd a-mortgage-calculator-88592
    ```

2. **Ensure you have Java 8+ and Maven installed**:
    - Check Java: `java -version`
    - Check Maven: `mvn -version`

## Building the Application

Compile and package the application using Maven:

```sh
mvn clean package
```

This creates JAR files in the `target` directory:
- `a-mortgage-calculator-1.0-SNAPSHOT.jar` — main JAR
- `a-mortgage-calculator-1.0-SNAPSHOT-jar-with-dependencies.jar` — standalone executable JAR

## Usage

### GUI Version

To launch the desktop application:

```sh
java -jar target/a-mortgage-calculator-1.0-SNAPSHOT-jar-with-dependencies.jar
```

### Command-line Version

To run the CLI version:

```sh
java -cp target/a-mortgage-calculator-1.0-SNAPSHOT-jar-with-dependencies.jar com.mortgagecalculator.cli.MortgageCalculator
```

### Sample Usage Walkthroughs

#### GUI

1. Enter the **Loan Amount** (e.g., `300000`)
2. Enter the **Annual Interest Rate** (e.g., `4.5` for 4.5%)
3. Enter the **Loan Term (in years)** (e.g., `30`)
4. Click **Calculate**
5. View the resulting monthly payment, total payment, and interest.
6. See the amortization table for yearly breakdown.

#### CLI

The terminal program will prompt you for:
- Loan amount
- Interest rate
- Loan term (years)

After entry, the monthly payment, total payment, interest, and optionally, the amortization schedule are displayed. Example:

```
Enter loan amount (e.g., 250000): $300000
Enter annual interest rate (e.g., 5.5 for 5.5%): 4.5
Enter loan term in years (e.g., 30): 30

Mortgage Summary:
----------------
Loan Amount: $300,000.00
Annual Interest Rate: 4.5%
Loan Term: 30 years
Monthly Payment: $1,520.06
Total Payment: $547,220.52
Total Interest: $247,220.52

Would you like to see the amortization schedule? (y/n)
y

Amortization Schedule:
---------------------
Payment #   Payment         Principal        Interest         Remaining      
Year 1      $18,240.72      $6,634.54        $11,606.18       $293,365.46
...
```

## Development

The project structure is as follows:
- `src/main/java/com/mortgagecalculator/model/` — Core mortgage calculation logic and data structures
- `src/main/java/com/mortgagecalculator/util/` — Utility functions for parsing, formatting, computation
- `src/main/java/com/mortgagecalculator/gui/` — Swing-based desktop GUI
- `src/main/java/com/mortgagecalculator/cli/` — CLI entry point
- `src/main/resources/icons/` — Application resources (e.g., calculator icon)
- `pom.xml` — Maven build configuration

### Technologies Used

- **Java 8** features: Streams, lambdas, Optionals
- **Swing** for graphical interface
- **Maven** for dependency management/build
- **JUnit** for test support (extend with your own tests as needed)

## Continuous Integration

This project includes a `.gitlab-ci.yml` for GitLab CI/CD integration.
On every commit pushed to GitLab:
1. The project is built and tested automatically
2. Artifacts are packaged and made available

_Note: Extend `.gitlab-ci.yml` as needed for more advanced pipelines._

## Contribution Guidelines

We welcome contributions!

- Fork the repository and create your branch from `main`
- Write clear, self-contained code and follow the project structure
- Include Javadoc comments and method documentation as appropriate
- Adhere to Java and Maven best practices
- Make pull requests for merging your changes
- For feature requests, bug reports, or questions — please open an issue

**Local Development Tips:**
- Use your IDE’s build facilities or `mvn compile`/`mvn package` for fast feedback
- Add new utility or computation logic in the `util` or `model` packages
- Test both CLI and GUI interfaces for changes in loan-related computation

## License

This project is licensed under the MIT License. See the LICENSE file for details.

## Acknowledgements

- Java & Maven Documentation
- All contributors and open-source resources