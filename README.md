# Student Data Cleaning & Validation Automation

An automated data-quality workflow built with **n8n, JavaScript, and Google Drive** to clean student records, validate data, and separate valid and invalid CSV files with minimal manual intervention.

## The Problem

Organizations often receive CSV files containing missing fields, inconsistent formatting, invalid information, and duplicate records. Manually checking these records is repetitive, time-consuming, and prone to human error.

## The Solution

This workflow automates CSV cleaning and validation using predefined business rules. It standardizes records, identifies validation failures, adds error explanations, and uploads separate valid and invalid CSV files to Google Drive.

**Workflow:** Google Drive → CSV Extraction → JavaScript Cleaning & Validation → Conditional Routing → CSV Generation → Google Drive Upload

https://github.com/Surya-90/n8n-student-data-validation/blob/main/Screenshots/Screenshot%202026-10-28%20092652.png

## Key Features

- Standardizes whitespace, capitalization, and email formatting.
- Validates required fields, email syntax, phone numbers, fee status, and enrollment dates.
- Flags duplicate student IDs and repeated names.
- Adds validation status and error explanations to records.
- Generates dated CSV outputs and uploads them to Google Drive.
- Configures retries for the invalid-record upload step.

## Reusability & Business Applications

Although demonstrated with student records, this workflow follows a reusable data-processing pattern that can be adapted to other datasets by modifying the input fields, validation rules, and output configuration.

Potential applications include:
- **HR:** Employee records and onboarding data.
- **Sales & CRM:** Customer data and duplicate identification.
- **Finance:** Invoice and payment data checks.
- **Operations:** Inventory, supplier, and routine data imports.

Each use case requires appropriate configuration, business rules, and testing.

## Engineering Decision: Why Not AI?

The current requirements involve clearly defined validation rules. JavaScript provides predictable results, easier debugging, and avoids unnecessary AI costs and latency for checks that do not require a language model.

**Good engineering means choosing the right technology for the problem—not adding AI simply because it is available.**

Future enhancements could include AI-assisted correction suggestions, anomaly detection, and natural-language rule assistance where contextual reasoning adds value. These capabilities are not implemented in the current version.

## Technology Stack

n8n, JavaScript, Google Drive, CSV

## Setup

1. Import the exported workflow JSON into n8n.
2. Configure your own Google Drive OAuth2 credentials.
3. Set the input CSV file and output folder.
4. Test with sample data and inspect both output files.

## Scope

Email validation checks syntax, not mailbox existence. Phone validation checks digit count, not whether a number is active. Repeated names may belong to different people. Production deployments may require additional monitoring, access controls, testing, and error handling.

## Contact

Interested in data automation, workflow improvement, or adapting this solution to your business? Feel free to connect.

- **LinkedIn:** https://www.linkedin.com/in/surya2605/
- **GitHub:** https://github.com/Surya-90
- **Email:** Suryaofficial2605@gmail.com

