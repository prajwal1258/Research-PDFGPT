A specialized GPT architecture designed to transform conversational research into publication-ready PDF reports. This project bridges the gap between AI-driven knowledge synthesis and professional document formatting using OpenAI Actions and APITemplate.io.

🚀 The Problem
Standard LLM outputs are often unstructured and difficult to format for professional use. When converting chat logs to PDF, common issues include:

Orphaned Headers: Headings appearing at the bottom of a page without content.

Inconsistent Styling: Loss of hierarchical structure (H1, H2, H3).

Manual Effort: The need to copy-paste data into external editors.

🛠 The Solution
This GPT uses a logic-driven system prompt and CSS-aware HTML mapping to ensure every generated PDF follows professional layout standards.

Key Features
Contextual Synthesis: Analyzes chat history to generate relevant report content automatically.

Intelligent Layout Logic: Uses a custom keep-together wrapper system to prevent awkward page breaks.

API Orchestration: Real-time integration with APITemplate.io for instant PDF generation.

Structured Data Mapping: Converts natural language into a strictly validated JSON payload.

📂Repository Structure

research-gpt-api/
├── .github/
├── assets/                        # Portfolio visuals
│   ├── ResearchGPT_Workflow-.png  # Flow: User -> GPT -> HTML -> APITemplate -> PDF
│   ├── Sample-output.png        # Screenshot of the GPT in action
│   └── Final Output.pdf         # A high-quality export final Pdf generated 
|   └── Sample Conversation Output.png     # The APITemplate.io API definition
├── gpt-configuration/          # The "Backend" of your GPT
│   ├── instructions.md         # Your expert assistant system prompt
│   └── openapi-schema.yaml     # The APITemplate.io API definition
|   └── Conversation-starters.md     # Conversation starter statements
|   └── Gpt_actions.md          # GPT Actions summary
├── web-assets/                 # The "Frontend" logic
│   ├── base-styles.css         # The CSS that handles .keep-together and .highlight
│   └── template-structure.html # The skeleton HTML used in APITemplate.io
├── examples/                   # Demonstrating the data transformation
│   ├── raw-chat-context.png     # Example of a research conversation
│   └── api-payload-sample.json # The final JSON sent to the API
├── README.md                   # Project documentation 

⚙️ Technical Workflow
The system operates through a three-tier transformation process:

Logic Tier (GPT): The GPT acts as an expert assistant, synthesizing user queries.

Transformation Tier (HTML/JSON): The GPT maps the content into a specific JSON structure, wrapping sections in <div class="keep-together"> based on predefined heuristic rules.

Delivery Tier (API): The GPT triggers a POST request to the APITemplate.io endpoint, passing the structured HTML to a pre-configured template (ID: 0c677b235eb23128).

The "Keep-Together" Logic
To ensure professional quality, the GPT is programmed to follow specific HTML patterns:

<div class="keep-together">
    <h2>Section Title</h2>
    <ul>
        <li>Key data point 1</li>
        <li>Key data point 2</li>
    </ul>
</div>

This ensures that the header and the list are never separated by a page break.

🔗 Setup & Integration
1. GPT Instructions
Copy the content of gpt-configuration/instructions.md into the "Instructions" section of your Custom GPT.

2. API Configuration
1.Import gpt-configuration/openapi-schema.yaml into the "Actions" section.

2.Set Authentication to API Key (Header: X-API-KEY).

3.Ensure your APITemplate.io account has a template matching the provided ID.

📄 Sample Output
Raw Chat: View Sample Conversation

Generated PDF: Download Sample Report

🤝 Contributing & Portfolio Use
This repository was created to demonstrate the capability of building Production-Grade AI Tools. Feel free to explore the prompt logic to see how conditional formatting and API schemas are handled in a no-code environment.