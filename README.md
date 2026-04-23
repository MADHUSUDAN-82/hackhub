# HackHub Portal

A comprehensive hackathon management dashboard with project submissions, real-time tracking, adjudication system, and an integrated AI-powered chatbot for querying project data.

---

## Features

### Dashboard
- **Hackathon Overview**: Real-time statistics including total participants, submissions, and tech stack distribution
- **Hall of Fame**: Top 3 projects ranked by adjudication scores with visual prominence
- **Tech Distribution Chart**: Horizontal bar chart showing the most used technologies across projects
- **Live Session Indicator**: Visual feedback for active hackathon sessions

### Project Submissions
- **Flexible Submission Types**: Support for both solo and team projects
- **Dynamic Team Management**: Add/remove team members during submission
- **Form Validation**: URL validation for GitHub and live demo links
- **Instant Receipt**: Visual confirmation with project hash after successful submission

### Project Hub
- **Search & Filter**: Filter projects by search term or technology stack
- **Project Cards**: Clean card layout with tech tags and participant info
- **Admin Scoring**: Protected admin mode for scoring and adjudication (requires password)
- **Winner Badges**: Visual indicators for top-performing projects

### AI Assistant (Chatbot)
- **RAG-Powered**: Queries project data using Google's Gemini AI
- **Natural Language**: Ask questions like "Find projects using React" or "Who won?"
- **Regex Fallback**: Pattern-matching responses when AI is unavailable
- **Markdown Support**: Formatted responses with tables and code blocks
- **Context Aware**: Full dataset of projects loaded into each session

---

## Tech Stack

| Category | Technology |
|----------|------------|
| Framework | React 19 |
| Language | TypeScript |
| Build Tool | Vite 6 |
| Styling | Tailwind CSS 4 |
| Animations | Motion (Framer Motion fork) |
| Charts | Recharts |
| Icons | Lucide React |
| AI Integration | Google GenAI SDK |
| Markdown | React Markdown |

---

## Prerequisites

- **Node.js** (v18 or higher recommended)
- **Gemini API Key** (for AI chatbot functionality)
- **Optional**: Admin password for scoring features

---

## Installation

1. **Clone the repository** (or navigate to project directory):
   ```bash
   cd assssssss-master
   ```

2. **Install dependencies**:
   ```bash
   npm install
   ```

3. **Configure environment variables**:
   
   Create a `.env.local` file in the root directory:
   ```env
   GEMINI_API_KEY=your_gemini_api_key_here
   VITE_ADMIN_PASSWORD=your_admin_password
   ```

---

## Running the App

### Development Mode
```bash
npm run dev
```
The app will start on `http://localhost:3000` with hot module replacement enabled.

### Production Build
```bash
npm run build
```

### Preview Production Build
```bash
npm run preview
```

### Clean Build Artifacts
```bash
npm run clean
```

### Type Checking
```bash
npm run lint
```

---

## Project Structure

```
assssssss-master/
├── src/
│   ├── App.tsx                 # Main application component
│   ├── main.tsx                # Entry point
│   ├── types.ts                # TypeScript interfaces
│   ├── components/
│   │   ├── Sidebar.tsx         # Navigation sidebar
│   │   ├── Dashboard.tsx       # Overview dashboard
│   │   ├── Submissions.tsx     # Project submission form
│   │   ├── ProjectDetails.tsx  # Project grid with filters
│   │   ├── ProjectDetailPanel.tsx  # Project detail modal
│   │   └── Chatbot.tsx         # AI chatbot interface
│   ├── data/
│   │   └── initialData.ts      # Sample project data
│   └── lib/
│       └── utils.ts            # Utility functions
├── .env.local                  # Environment variables (create this)
├── index.html                  # HTML entry point
├── package.json                # Dependencies and scripts
├── tsconfig.json               # TypeScript configuration
└── vite.config.ts              # Vite configuration
```

---

## Usage Guide

### Submitting a Project

1. Navigate to **Submissions** tab
2. Choose **Solo** or **Team** submission type
3. Fill in participant name(s)
4. Enter project title and description
5. List technologies used (comma-separated)
6. Provide GitHub repository URL (required)
7. Optionally add a live demo link
8. Click **Finalize Submission**

### Admin Mode

1. Click the **Admin Mode** toggle in the sidebar footer
2. Enter the admin password (configured in `.env.local`)
3. Press Enter or click **Unlock System**
4. Navigate to **Project Hub** to score projects

### Using the AI Assistant

The chatbot understands natural language queries:

| Query Type | Example |
|------------|---------|
| Count | "How many projects are there?" |
| Winners | "Who won the hackathon?" |
| Tech Stack | "What technologies are being used?" |
| Search | "Find projects using Python" |
| Participant | "Show me Alice's project" |

---

## Data Persistence

Project data is stored in **localStorage** under the key `hackhub_projects`. Data persists across browser sessions but is local to the current browser.

---

## API Integration

### Google Gemini AI

The chatbot uses the `@google/genai` SDK to query project data. The AI receives the full project dataset as context and responds to natural language queries.

**Fallback Mechanism**: If the Gemini API is unavailable, the chatbot falls back to regex-based pattern matching for common queries.

---

## Customization

### Adding New Tracks

Modify the `stats` array in `Dashboard.tsx` to change the "Active Tracks" count.

### Changing Winner Logic

Winners are automatically determined by sorting projects by score (descending) and taking the top 3. Modify the sorting logic in `App.tsx` line 26-32.

### Sample Data

Edit `src/data/initialData.ts` to change the default projects loaded on first run.

---

## Troubleshooting

### Chatbot Not Responding

1. Verify `GEMINI_API_KEY` is set in `.env.local`
2. Check browser console for API errors
3. Ensure the API key has not exceeded rate limits

### Admin Password Not Working

1. Verify `VITE_ADMIN_PASSWORD` is set correctly
2. Note that Vite requires a server restart after `.env` changes
3. Clear browser cache and reload

### Build Errors

```bash
# Clear node_modules and reinstall
rm -rf node_modules
npm install

# Clean build artifacts
npm run clean
```

---

## License

This project is private and proprietary.

---

## View in AI Studio

https://ai.studio/apps/f8f97683-0e25-4541-b37c-d4b412f47bff

---

<div align="center">
  <sub>Built with React, TypeScript, and Gemini AI</sub>
</div>
