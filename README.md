
🔍 Project Title: Automated Multi-Agent PR Reviewer with n8n & LLMs
📚 Overview:
This project implements a fully automated pull request review system using n8n, connected to multiple LLM agents from different models (including Google Gemini and others). The workflow is triggered automatically by a GitHub event (pull_request) on the repository n8nCodeReviewer.

The system performs an AI-powered multi-perspective code review and posts the feedback directly to the pull request on GitHub.

⚙️ Architecture & Workflow:
GitHub Trigger
The workflow is triggered by any new or updated pull request on a specific branch (e.g., main) in the configured repository.

Get Pull Request Information
Metadata and the diff of the pull request are fetched using GitHub’s API.

Multiple LLM Agents Review the Code:

Code Quality Agent (Gemini Model):
Checks for code readability, maintainability, naming conventions, and adherence to clean code principles.

Logic Bug Finder Agent (Gemini Model):
Detects potential logical errors, risky code patterns, and common programming mistakes.

Code Security Agent (Gemini Model):
Identifies security vulnerabilities, unsafe code usage, and possible exploits (like input validation or secret handling flaws).

Aggregator Agent
Gathers all insights from the above LLMs, merges their feedback into a coherent, structured format.

Custom Code Node
Transforms the aggregated feedback into a GitHub-compatible format (dictating file paths, line numbers, and specific comments).

Post Review Comments to GitHub PR
The system automatically posts the review comments back to the original PR on GitHub using the GitHub API.

🤖 Types of AI Agents Used:
Agent Role	Purpose	Model Example
Code Quality	Clean code practices, naming, structure	Gemini 1.5 Flash
Logic Bug Finder	Detecting logical errors, potential bugs	Gemini 1.5 Flash
Security Reviewer	Security vulnerabilities, unsafe patterns	Gemini 1.5 Flash
Aggregator	Merge and format all agents’ outputs	Custom Agent + Python Code

🛠️ Tech Stack:
n8n.io: Workflow Automation Engine

GitHub API: Pull Request Metadata & Commenting

Google Gemini LLM: AI Code Review Agents

Python (inside n8n Code node): JSON processing and formatting

OAuth2 & GitHub PAT: Authentication for GitHub API

🎯 Key Features:
✔️ Automated multi-angle PR review (quality, logic, security)
✔️ LLM-generated actionable comments per file & line
✔️ GitHub PR integration — feedback posted directly to the PR
✔️ Modular & extendable — additional agents or checks can be added easily
✔️ Branch-specific trigger (e.g., main branch only)

