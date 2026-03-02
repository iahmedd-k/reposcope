Features

AI Commit Summaries — Every commit gets a formal, clear explanation written by Groq AI (Llama 3). No more deciphering cryptic commit messages.
Natural Language Search — Ask questions like "where did I change the login page?" or "who fixed the payment bug last week?" and get the exact commit, file, and a direct GitHub link.
File-Level Answers — The chatbot returns clickable links that take you straight to the exact file at the exact commit on GitHub.
Private Repo Support — Add your GitHub Personal Access Token to analyze private repositories.
Recent Repos — Signed-in users get a sidebar history of recently analyzed repos.
Usage Limits + Billing — Free tier with 3 analyses/day. Pro and Team plans via Stripe.

🛠️ Tech Stack
LayerTechnologyFrameworkNext.js 14 (App Router)StylingTailwind CSSAuthenticationClerk (GitHub OAuth)DatabaseSupabase (PostgreSQL)AI / LLMGroq API — Llama 3.1Data SourceGitHub REST APIPaymentsStripe (test mode)DeploymentVercel
User pastes GitHub URL
        ↓
GitHub REST API → fetch all commits + file diffs
        ↓
Groq AI (Llama 3.1) → formal summary for each commit
        ↓
React Context (useContext) → all commits stored in memory
        ↓
User asks chatbot question
        ↓
All commits sent as context to Groq AI
        ↓
AI returns exact commit SHA + file path + blob URL
        ↓
Clickable link to file on GitHub
