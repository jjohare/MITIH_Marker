# AI-Powered Project Proposal Assessment Tool

This repository hosts an AI-powered tool designed to efficiently and accurately assess project proposals. Utilizing advanced AI models, this tool evaluates proposals against a predefined rubric, aiming to streamline the assessment process and enhance decision-making accuracy.

## Introduction

The AI-Powered Project Proposal Assessment Tool automates the evaluation of project proposals by comparing them against a detailed assessment rubric. This approach ensures a structured and objective assessment process, facilitating more informed decision-making.

## Features

- **Automated Proposal Evaluation:** Employs AI to systematically score project proposals based on an extensive assessment rubric.
- **Customizable Rubric:** Allows for the adjustment of assessment criteria to suit the specific requirements of various projects.
- **Detailed Feedback:** Provides comprehensive feedback and recommendations for each proposal, guiding proposers towards necessary improvements.
- **User-Friendly Interface:** Offers an easy-to-use interface for administrators to manage assessments and for users to submit proposals.

## Requirements

Before setting up the project, ensure you have:

- Python 3.8 or newer
- Pip package manager
- All necessary Python dependencies as listed in `requirements.txt`

## Installation

To install the project locally, follow these instructions:

1. Clone the repository:
git clone <repository-url>

css
Copy code
2. Navigate to the project directory:
cd <project-name>

markdown
Copy code
3. Install the required Python packages:
pip install -r requirements.txt

bash
Copy code

## Usage

Start the application with the following command:

streamlit run StreamLitMarkThis.py

vbnet
Copy code

Follow the prompts on the screen to upload project proposals and receive assessments.

## Configuration

Customize the assessment rubric by modifying the `assessment_rubric.json` file. For guidance on tailoring the rubric to specific assessment needs, refer to the `instructions.txt`.

## Contributing

Contributions to enhance the tool are welcome. Please adhere to the contribution guidelines if you wish to contribute.

## License

This project is under the Apache-2.0 License. See the [LICENSE](LICENSE) file for details.

```mermaid
sequenceDiagram
    actor User
    participant Streamlit as st
    participant Main
    participant ProcessFiles as Process Files
    participant Concatenate
    participant GeneratePrompt as Generate Prompt
    participant CallOpenAI as Call OpenAI API
    participant GenerateOutput as Generate Output
    participant Cleanup

    User->>st: Upload files
    st->>Main: Initiate processing
    Main->>ProcessFiles: Process each file based on type
    loop For each file
        ProcessFiles->>Concatenate: Concatenate text outputs
    end
    Concatenate->>GeneratePrompt: Generate prompt from texts
    GeneratePrompt->>CallOpenAI: Call API with prompt
    CallOpenAI->>GenerateOutput: Generate Markdown and HTML outputs
    GenerateOutput->>st: Display outputs and link to HTML
    Main->>Cleanup: Clean up directories
    Cleanup->>st: Confirm cleanup
Remember to replace <repository-url> and <project-name> with your GitHub repository's actual URL and your project's directory name, respectively.
