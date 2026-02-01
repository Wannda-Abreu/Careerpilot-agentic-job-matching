CareerPilot
Explainable Job Matching with Agentic AI

Built with IBM watsonx Orchestrate

Overview

CareerPilot is a demo project created for the IBM Dev Day – AI Demystified Hackathon.
It demonstrates how an agentic AI architecture, orchestrated with IBM watsonx Orchestrate, can deliver transparent, ethical, and actionable job-matching experiences.

Job seekers often receive ranked job lists without understanding why they match or how to improve. CareerPilot addresses this gap by combining explainable matching with a conservative, ethical career coaching plan.

The project intentionally focuses on agent behavior design, orchestration, and explainability, rather than UI complexity.

Problem Statement

Most job platforms rely on opaque ranking algorithms:

Candidates do not understand why they match or do not match a role

Missing skills and risks are not clearly explained

There is no concrete, ethical guidance on next steps

This results in confusion, mistrust, and low actionable value for job seekers.

Solution

CareerPilot demonstrates a multi-agent AI system where:

Each agent has a single, clearly defined responsibility

All decisions are explainable and deterministic

No agent invents, infers, or exaggerates information

The orchestrator coordinates agents without embedding business logic

The system produces a single structured JSON output suitable for direct UI rendering.

Agentic Architecture

CareerPilot is built using four specialized agents, coordinated by IBM watsonx Orchestrate.

cv_parser_agent

Responsibility:
Transforms raw resume text into a structured candidate profile.

Key constraints:

No inference or fabrication

No guessing of experience or skills

Outputs only validated, structured JSON

matcher_agent

Responsibility:
Ranks job offers against the candidate profile.

Outputs:

Top 5 job matches

Deterministic score (0–100)

Exactly three explainable reasons per match

Missing skills

Identified risks

Design principles:

Neutral scoring when job data is missing

Strict penalties for missing skills

Fully explainable scoring logic

career_coach_agent

Responsibility:
Generates a 14-day, job-specific improvement plan for the top-ranked role.

Ethical constraints:

No fabricated achievements

No performance claims

No hypothetical metrics

Only descriptive, verifiable actions

Focus areas:

CV positioning

Documentation

Preparation

Interview readiness

orchestrator_agent

Responsibility:
Coordinates the workflow using IBM watsonx Orchestrate.

What it does:

Validates inputs

Delegates tasks to specialized agents

Merges outputs into a single JSON response

What it does NOT do:

No parsing

No matching

No coaching logic

This ensures a clean, auditable agentic workflow.

End-to-End Flow

User provides resume text and job offers (plain text or JSON)

cv_parser_agent extracts a structured candidate profile

matcher_agent ranks job offers with explainable results

career_coach_agent generates an ethical 14-day plan

orchestrator_agent returns a single UI-ready JSON output

Output

The final orchestrator output includes:

Structured candidate profile

Ranked job matches with scores, reasons, missing skills, and risks

A conservative, actionable coaching plan

The UI shown in the demo renders this JSON directly, without regenerating or modifying content.

Demo Video

The demo video shows:

Agent setup in watsonx Orchestrate

End-to-end orchestration flow

Real JSON output rendered in the UI

Video URL:
https://www.canva.com/design/DAHAFg4tgSg/J8vCbcBY5PKrmmXRLH0i7A/edit

Why This Matters

CareerPilot highlights the core strengths of agentic AI:

Transparent decision-making instead of black-box models

Ethical and conservative guidance

Modular, auditable system design

Clear separation of responsibilities

The project demonstrates how IBM watsonx Orchestrate enables reliable, real-world agentic workflows beyond monolithic chatbots.

Future Extensions

Potential extensions of this architecture include:

Adding domain-specific matcher agents for different industries

Introducing a skills-gap learning recommendation agent

Supporting multi-language resume parsing

Integrating recruiter-side explainability views

Persisting agent outputs for longitudinal career tracking

These extensions can be added without modifying existing agents, reinforcing the modular design enabled by watsonx Orchestrate.

Notes

This repository focuses on architecture and agent behavior design

The UI is intentionally minimal and used only to render real orchestrator output

No production or performance claims are made
