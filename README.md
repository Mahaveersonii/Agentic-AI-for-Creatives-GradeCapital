# Agentic-AI-for-Creatives-GradeCapital
Grade Capital AI Suite 🚀  An n8n automation using GPT-4o and Fal.ai to generate brand-aligned visuals. It features a "Creative Director" agent that transforms chat prompts into high-end, institutional designs using a modular "Brain &amp; Engine" workflow architecture.

## Project Overview
This project uses a "Brain and Engine" architecture to maintain brand consistency while generating complex AI imagery:

The Brain (Mahaveer 1): A LangChain-powered agent that acts as a Senior Brand Strategist. It takes user input via a Chat Trigger and expands it into a 150-word cinematic prompt, ensuring strict adherence to the Grade Capital brand DNA (Gold #FEBE2F and Black #151517 palettes).

The Engine (Grade_Capital_Engine): A worker workflow that interfaces with the Fal.ai (Flux Pro v1.1 Ultra) API. It handles the asynchronous generation process, waiting for the rendering to complete before returning a high-resolution 16:9 image URL to the user.

## Core Features
Brand DNA Enforcement: Automatically injects specific hex codes (#FDDC97, #FEBE2F, #151517), typography requirements (Poppins, Quicksand), and stylistic directives (glassmorphism, 3D glossy icons) into every request.

Dynamic Prompt Engineering: Uses GPT-4o to translate basic ideas like "make a flyer" into professional, lighting-focused, institutional-grade creative briefs.

Modular Architecture: Separates the AI logic from the API execution, allowing for easy swapping of image models (e.g., Midjourney, DALL-E) without reconfiguring the agent.

Automated Workflow Handoff: Uses n8n's toolWorkflow and Execute Workflow Trigger to pass data seamlessly between the parent and child processes.

## Tech Stack
Orchestration: n8n
LLM: OpenAI GPT-4o (via LangChain)
Image Generation: Fal.ai (Flux Pro v1.1 Ultra)
Memory: LangChain Window Buffer Memory (10-message context)

## Setup Instructions
Import Workflows: Import Mahaveer 1.json and Grade_Capital_Engine.json into your n8n instance.

Configure Credentials:
Set up OpenAI API credentials for the Chat Model.
Set up Header Auth for Fal.ai (Key: Authorization, Value: Key YOUR_API_KEY).
Link Workflows: Ensure the workflowId in the "Call Grade_Capital_Engine" node in the Mahaveer workflow matches the actual ID assigned to your Engine workflow.
