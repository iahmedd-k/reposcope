# 🔭 RepoScope — Every Commit Summarized & Searchable

> Stop deciphering cryptic commit messages. Ask RepoScope instead.

RepoScope is an AI-powered GitHub commit analyzer that automatically generates plain-English summaries for every commit in a repository and lets you search through them using natural language. Paste a GitHub URL, and instantly understand what changed, when, and where — down to the exact file.

---

## ✨ Features

- 🤖 **AI Commit Summaries** — Every commit gets a formal, clear explanation powered by Groq AI (Llama 3.1). No more guessing what `fix stuff` or `misc changes` actually means.
- 🔍 **Natural Language Search** — Ask questions like *"where did I change the login page?"* or *"who fixed the payment bug last week?"* and get the exact commit, file, and a direct GitHub link.
- 🔗 **File-Level Answers** — The chatbot returns clickable links that take you straight to the exact file at the exact commit on GitHub.
- 🔒 **Private Repo Support** — Add your GitHub Personal Access Token to analyze private repositories.
- 🕓 **Recent Repos History** — Signed-in users get a sidebar showing recently analyzed repositories.
- 💳 **Usage Limits & Billing** — Free tier with 3 analyses/day. Pro and Team plans available via Stripe.

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| **Framework** | Next.js 14 (App Router) |
| **Styling** | Tailwind CSS |
| **Authentication** | Clerk (GitHub OAuth) |
| **Database** | Supabase (PostgreSQL) |
| **AI / LLM** | Groq API — Llama 3.1 |
| **Data Source** | GitHub REST API |
| **Payments** | Stripe (test mode) |
| **Deployment** | Vercel |

---

## ⚙️ How It Works

```
User pastes GitHub repo URL
        ↓
GitHub REST API → fetch all commits + file diffs
        ↓
Groq AI (Llama 3.1) → generates formal summary for each commit
        ↓
React Context (useContext) → all commits stored in memory
        ↓
User asks chatbot a question
        ↓
All commits sent as context to Groq AI
        ↓
AI returns exact commit SHA + file path + blob URL
        ↓
Clickable link to the file on GitHub ✅
```

---

## 📁 Project Structure

```
RepoScope-Every-Commit-Summarized-Searchable/
├── app/              # Next.js App Router pages & API routes
├── components/       # Reusable React UI components
├── context/          # React Context for global commit state
├── lib/              # Utility functions (GitHub API, Groq, Supabase, Stripe)
├── public/           # Static assets
├── middleware.js     # Clerk auth middleware
├── next.config.mjs
├── tailwind.config.js
└── package.json
```

---

## 🚀 Getting Started

### Prerequisites

- Node.js `v18+`
- A [Clerk](https://clerk.com) account (GitHub OAuth app)
- A [Supabase](https://supabase.com) project
- A [Groq](https://console.groq.com) API key
- A [Stripe](https://stripe.com) account (test mode)
- A GitHub Personal Access Token (for private repos / higher rate limits)

### 1. Clone the Repository

```bash
git clone https://github.com/iahmedd-k/RepoScope-Every-Commit-Summarized-Searchable.git
cd RepoScope-Every-Commit-Summarized-Searchable
```

### 2. Install Dependencies

```bash
npm install
```

### 3. Configure Environment Variables

Create a `.env.local` file in the root directory:

```env
# Clerk Auth
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key
CLERK_SECRET_KEY=your_clerk_secret_key

# Supabase
NEXT_PUBLIC_SUPABASE_URL=your_supabase_url
NEXT_PUBLIC_SUPABASE_ANON_KEY=your_supabase_anon_key
SUPABASE_SERVICE_ROLE_KEY=your_supabase_service_role_key

# Groq AI
GROQ_API_KEY=your_groq_api_key

# GitHub
GITHUB_TOKEN=your_github_personal_access_token

# Stripe
STRIPE_SECRET_KEY=your_stripe_secret_key
NEXT_PUBLIC_STRIPE_PUBLISHABLE_KEY=your_stripe_publishable_key
STRIPE_WEBHOOK_SECRET=your_stripe_webhook_secret
```

### 4. Run the Development Server

```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

---

## 💰 Pricing Tiers

| Plan | Analyses/Day | Price |
|------|-------------|-------|
| **Free** | 3 | $0 |
| **Pro** | Unlimited | Via Stripe |
| **Team** | Unlimited + Team features | Via Stripe |

---

## 🌐 Deployment

This project is built for **Vercel**. To deploy your own:

1. Fork this repository
2. Connect your fork to [Vercel](https://vercel.com)
3. Add all environment variables in the Vercel dashboard
4. Deploy!

---

## 🤝 Contributing

Contributions are welcome!

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/your-feature`
3. Commit your changes: `git commit -m "Add your feature"`
4. Push to your fork: `git push origin feature/your-feature`
5. Open a Pull Request

---
.

---

## 👤 Author

**iahmedd-k**  
GitHub: [@iahmedd-k](https://github.com/iahmedd-k)

---

> ⭐ Found it useful? Drop a star on GitHub!
