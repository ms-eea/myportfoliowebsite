# Enterprise Product Leadership & AI Strategy Portfolio

Welcome to the technical portfolio repository for **Elizabeth Enyart-Allen**, an Executive Product Leader and AI Strategist based in Saint Paul, Minnesota. 

This repository hosts the source code, Jupyter notebooks, n8n automation workflows, and architectural governance specifications showcased on my personal portfolio website.

---

## 📋 Table of Contents
1. [Enterprise AI Sycophancy & Guardrails Audit Harness](#1-enterprise-ai-sycophancy--guardrails-audit-harness)
2. [Dynamic Enterprise Product Evaluation Harness](#2-dynamic-enterprise-product-evaluation-harness)
3. [AI Patient Agent Chat](#3-ai-patient-agent-chat)
4. [Daily Weather AI Automation Engine](#4-daily-weather-ai-automation-engine)
5. [Cloud Telemetry & FinOps Observability Engine](#5-cloud-telemetry--finops-observability-engine)
6. [Credentials & Leadership](#credentials--leadership)
7. [Repository Structure & Local Setup](#repository-structure--local-setup)

---

## 1. Enterprise AI Sycophancy & Guardrails Audit Harness

### Overview & Objective
An automated Python testing framework designed to evaluate LLM behavior under adversarial conditions—quantifying model drift, sycophancy (agreeing with flawed or unsafe user premises), and safety policy survival rates before production deployment.

### Audit Test Suite & Adversarial Methodologies
The audit harness subjects target LLM endpoints to three primary adversarial test modes across legal, health, safety, and financial domains:
* **Adversarial Pushback & Evasion:** Simulates persistent user pushback, rule evasion, and symptom/risk downplaying to test model firmness.
* **Sycophancy Triggers:** Prompts models with intentionally incorrect or biased user premises to test whether the LLM validates misinformation.
* **Guardrail Benchmarking:** Comparative analysis evaluating raw model outputs against system-prompted, bounded safety guardrails.

### Key Evaluation Metrics
* **Referral Survival Rate (%):** Percentage of high-risk queries where the model correctly maintains a required referral or escalation recommendation despite user pushback.
* **Policy Adherence Rate (%):** Quantitative measure of system responses adhering strictly to organizational safety and regulatory rules.
* **Sycophancy Drift Rate (%):** Percentage of test runs where the model improperly yielded to user pressure or validated flawed premises.
* **Model Drift vs Baseline (%):** Relative performance degradation or gain across model versions and prompt updates.

### Artifacts & Code
* **Jupyter Notebook:** [`Enterprise_AI_Sycophancy_&_Guardrails_Audit_Harness.ipynb`](./Enterprise_AI_Sycophancy_%26_Guardrails_Audit_Harness.ipynb)
* **Architecture Infographic:** [`Enterprise AI LLM Goverance.png`](./Enterprise%20AI%20LLM%20Goverance.png)

---

## 2. Dynamic Enterprise Product Evaluation Harness

### Overview & Objective
A standardized evaluation framework and Python engine designed to score AI initiatives across four enterprise dimensions: financial ROI, execution latency, safety compliance, and task completion velocity.

### Core Architecture & Evaluation Pillars
1. **Financial ROI & Unit Economics ($):** Tracks cost-per-execution, token consumption efficiency, and infrastructure spend against user volume trends.
2. **Execution Latency (p95 / p99):** Monitors operational throughput, API call round-trips, and time-to-first-token (TTFT) against SLA targets.
3. **Safety Compliance (%):** Measures policy adherence, content safety classification, risk flag frequency, and regulatory guardrail survival rates.
4. **Task Completion Velocity (%):** Evaluates autonomous task completion, multi-step execution accuracy, and fallback/escalation frequencies.

### Automated Threshold Monitoring & Gating
* **Prompt Drift Alert (>15% variance):** Algorithmic detection of model response divergence from established baseline benchmarks.
* **Cost Spike Anomaly (> threshold limit):** Triggered when unit token execution costs exceed targeted budget parameters.
* **Safety Degradation Gate (Score < 80/100):** Halts automated deployment pipelines if policy adherence drops below safety compliance baselines.

### Artifacts & Code
* **Jupyter Notebook:** [`Dynamic_Enterprise_Product_Evaluation_Harness.ipynb`](./Dynamic_Enterprise_Product_Evaluation_Harness.ipynb)
* **Architecture Infographic:** [`Dynamic Enterprise Product Evaluation Harness.png`](./Dynamic%20Enterprise%20Product%20Evaluation%20Harness.png)

---

## 3. AI Patient Agent Chat

### Overview & Objective
An agentic conversational workflow built in n8n leveraging Google Gemini to automate patient appointment rescheduling and enforce clinical triage escalation for medication refills.

### Workflow Architecture & Technical Features
* **Clinical Guardrail Enforcement:** Custom JavaScript tools enforce deterministic routing for restricted medications (e.g., Adderall) to human triage.
* **Dynamic Slot Selection:** Tool-assisted state management handling multi-turn appointment rescheduling (Location & Timeframe selection).
* **LLM Tool-Calling Architecture:** Gemini Chat Model dynamically invoking custom JavaScript execution tools based on utterance intent.
* **State Management:** Maintains conversation context across multi-turn exchanges for seamless rescheduling and triage routing.

### Artifacts & Code
* **n8n Workflow JSON:** [`AI Patient Agent Chat.json`](./AI%20Patient%20Agent%20Chat.json)
* **Architecture Infographic:** [`AI Patient Agent Chat.png`](./AI%20Patient%20Agent%20Chat.png)

---

## 4. Daily Weather AI Automation Engine

### Overview & Objective
An automated morning briefing pipeline fetching real-time weather telemetry via Tomorrow.io REST API and leveraging Google Gemini to deliver concise, formatted forecasts with custom daily outfit tips directly to Telegram.

### Automation Pipeline
1. **Schedule Trigger:** Scheduled n8n cron execution fetching minutely and daily forecast timelines.
2. **Telemetry Transformation:** Formats and maps raw weather code IDs, temperature ranges, and precipitation probabilities.
3. **LLM Context Synthesis:** Direct prompt engineering converts parsed telemetry into natural language morning briefings with outfit suggestions.
4. **Multi-Channel Delivery:** Webhook integration routing generated summaries straight to dedicated Telegram chat channels.

### Artifacts & Code
* **n8n Workflow JSON:** [`Daily Weather.json`](./Daily%20Weather.json)
* **Interactive Canvas HTML:** [`Daily Weather n8n workflow.html`](./Daily%20Weather%20n8n%20workflow.html)
* **Architecture Infographic:** [`Daily Weather AI Automation Engine.png`](./Daily%20Weather%20AI%20Automation%20Engine.png)

---

## 5. Cloud Telemetry & FinOps Observability Engine

### Overview & Objective
An enterprise cloud governance strategy and telemetry framework designed to track multi-cloud dependency flows (AWS, Azure, GCP), detect idle resource anomalies, and enforce automated lifecycle rules—delivering over $2M in structural cloud cost optimizations.

### Core Capabilities
* **Unit Economic Telemetry:** Correlates real-time infrastructure spend directly against active platform user volume to quantify cost-per-transaction.
* **Automated Anomaly & Drift Detection:** Algorithmic monitoring flagging unattached storage volumes, idle compute instances, and over-provisioned clusters.
* **Decision-Rights Governance:** Established cross-functional cloud tagging standards and lifecycle policies across multi-tenant SaaS environments.

### Artifacts & Code
* **Jupyter Notebook:** [`Cloud_Observability_FinOps_Pipeline.ipynb`](./Cloud_Observability_FinOps_Pipeline.ipynb)
* **Architecture Infographic:** [`Cloud Telemetry & FinOps Observability Engine.png`](./Cloud%20Telemetry%20%26%20FinOps%20Observability%20Engine.png)

---

## Credentials & Leadership

* **Executive MBA (EMBA):** Carlson School of Management, University of Minnesota
* **Certified AI Transformation Leader™ (CAITL™):** USAII® / Bravura (Credential ID: `8718400406`)
* **Generative AI Leader:** Google Cloud (2026–2029)
* **Azure Fundamentals Certified:** Microsoft
* **Certified Agile Coach (CAC):** Chicago State University
* **B.S. in Medical Technology:** University of Minnesota
* **MN Women in AI:** Founding Member & North Star Member

---

## Repository Structure & Local Setup
