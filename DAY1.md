# Day 1 - Getting the Voice Agent Running

**Date:** November 22, 2025

## What I Accomplished
- ✅ Forked the ten-days-of-voice-agents-2025 repository
- ✅ Set up the development environment (Python, Node.js, pnpm, uv)
- ✅ Downloaded and ran LiveKit server locally on Windows
- ✅ Configured backend with Deepgram, Murf Falcon, and Google API keys
- ✅ Successfully ran the frontend and backend
- ✅ Connected to the voice agent and had my first conversation!

## Setup Process
- Installed dependencies for both frontend and backend
- Configured `.env.local` files with required API keys
- Downloaded required models using `uv run python src/agent.py download-files`
- Started LiveKit server, backend agent, and frontend in separate terminals

## Challenges Faced
- Initial connection errors due to missing DEEPGRAM_API_KEY
- Had to restart backend agent after browser refreshes
- Windows-specific issues with LiveKit server installation (needed to download .exe directly)

## LinkedIn Post
[Link to LinkedIn post with video demonstration]

## Tech Stack Used
- **TTS:** Murf Falcon API
- **STT:** Deepgram
- **LLM:** Google Gemini
- **Framework:** LiveKit Agents
- **Frontend:** Next.js + React
- **Backend:** Python

## Next Steps
- Continue with Day 2 challenge
- Explore customizing the agent's personality
- Learn more about LiveKit Agents framework

---
Part of the #MurfAIVoiceAgentsChallenge | #10DaysofAIVoiceAgents
