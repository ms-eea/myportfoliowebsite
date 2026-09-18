# myportfoliowebsite
Personal Portfolio Website
# AI Patient Access Agent (n8n Workflow)

## System Overview
This n8n workflow implements an autonomous **Patient Access AI Assistant** powered by Google Gemini and custom JavaScript tools. The system handles routine patient inquiries, including multi-turn appointment rescheduling and medication refill evaluation.

## Architecture & Tool Specifications

### 1. Agent Core (`AI Agent` + `Google Gemini Chat Model`)
* **Role:** Health Note's Patient Access AI Assistant.
* **Responsibilities:** Classify patient intent, manage multi-turn scheduling flows, and delegate safety checks to custom tools.

### 2. Clinical Guardrail Evaluator (`Rx Refill Tool`)
* **Logic:** Evaluates user utterances for restricted/controlled medications or schedule changes.
* **Safety Protocol:** Forces high-risk requests (e.g., controlled substances like Adderall) into human triage paths.

### 3. Appointment Rescheduling Engine (`Reschedule Tool`)
* **Logic:** Simulates clinic slot availability (e.g., weekend closure rules, multi-location offerings).
* **State Management:** Returns structured JSON statuses (`SELECTION_REQUIRED` vs. `CONFIRMED`) with confirmation codes.

## How to Import
1. Download `ai_patient_agent_chat.json`.
2. Open your self-hosted or cloud n8n instance.
3. Select **Workflows > Import from File** and upload the JSON.
4. Attach your **Google Gemini API** credentials to the model node.
