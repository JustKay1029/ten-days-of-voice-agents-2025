# Day 3 – Health & Wellness Voice Companion

**Date:** November 24, 2025  
**Challenge:** Murf AI Voice Agents Challenge - #10DaysofAIVoiceAgents

---

## 🎯 Project Overview

Built a voice-driven wellness companion that conducts daily check-ins about mood, energy, and goals. The agent persists all data to JSON for continuity across sessions and references previous check-ins to create a personal accountability buddy experience.

---

## ✨ Features Implemented

### Primary Features (Required)
✅ **Voice-based daily check-ins** via LiveKit  
✅ **JSON persistence** – all sessions saved to `wellness_log.json`  
✅ **Historical context** – agent references previous check-ins  
✅ **Grounded system prompt** – supportive but realistic, non-diagnostic  
✅ **Conversational workflow:**
   1. Greets user and loads previous sessions
   2. Asks: "How are you feeling today?"
   3. Asks: "What's your energy level (1-10)?"
   4. Asks: "What are 1-3 things you'd like to accomplish today?"
   5. Records the check-in with timestamp
   6. Summarizes and confirms with user

---

## 🛠️ Tech Stack

| Component | Technology |
|-----------|------------|
| **STT (Speech-to-Text)** | Deepgram Nova-3 |
| **TTS (Text-to-Speech)** | Murf Falcon |
| **LLM** | Google Gemini Pro |
| **Framework** | LiveKit Agents SDK |
| **Persistence** | JSON file storage |

---

## 💾 Data Structure

### Example `wellness_log.json`

```json
{
  "sessions": [
    {
      "date": "2025-11-24T19:30:00+05:30",
      "mood": "energized and focused",
      "energy_level": 8,
      "goals": [
        "Finish DSA assignment",
        "Go for a 30-minute walk",
        "Read one chapter of my book"
      ]
    }
  ]
}
```

---

## 🔧 Implementation Details

### Function Tools Created:

1. **`record_daily_checkin(mood, energy_level, goals)`**
   - Saves check-in data to JSON file
   - Stores timestamp, mood, energy (1-10), and goals
   - Returns confirmation message

2. **`get_previous_checkins(limit=3)`**
   - Retrieves past N check-ins from JSON
   - Returns formatted summary for agent context
   - Enables continuity in conversations

3. **`summarize_checkin()`**
   - Provides recap of current session
   - Confirms data was recorded
   - Asks user for verification

### System Prompt Strategy:

- Strict workflow enforcement with numbered steps
- Mandatory function tool calls at specific points
- Non-medical, supportive language
- Grounded advice (actionable, realistic)
- Temperature set to 0.3 for better instruction following

---

## 📚 What I Learned

### Technical Skills:
- Implementing function tools with LiveKit Agents SDK
- Managing stateful conversations with JSON persistence
- Designing conversation flows that feel natural yet structured
- Working with `@function_tool` decorator and `RunContext`
- Debugging LLM behavior with temperature adjustments

### Design Insights:
- Importance of explicit system instructions for function calling
- Balancing conversational flow with data collection needs
- Creating non-judgmental, supportive AI personas
- Ensuring data persistence across sessions for continuity

---

## 🚧 Challenges Faced

1. **Function tools not being called:** Initially, the LLM wasn't using the function tools. Solved by:
   - Making system instructions extremely explicit
   - Lowering temperature from 0.7 to 0.3
   - Adding mandatory workflow steps

2. **Environment configuration:** Had to adjust LLM provider from OpenAI to Gemini based on available API keys

3. **File structure confusion:** Learned the difference between running agents as separate files vs. consolidated code

---

## 🎥 Demo

[Link to demo video will be added]

**Demo shows:**
- Agent greeting and checking previous sessions
- Voice-based mood/energy/goals collection
- JSON file being updated in real-time
- Second conversation referencing first check-in

---

## 📝 Day 3 Requirements Checklist

✅ Uses a clear, grounded system prompt (non-medical, supportive)  
✅ Conducts short daily check-ins via voice  
✅ Persists key data to JSON file (`wellness_log.json`)  
✅ Uses past data to inform new conversations  
✅ Asks about mood, energy, and daily goals  
✅ Offers simple, realistic advice (non-diagnostic)  
✅ Provides a brief recap at the end of each check-in  
✅ References previous check-ins when starting new sessions

---

## 🔗 Resources Used

- [LiveKit Agents - Function Tools](https://docs.livekit.io/agents/build/tools/)
- [LiveKit Agents - Passing State](https://docs.livekit.io/agents/build/agents-handoffs/#passing-state)
- [Drive-Thru Example](https://github.com/livekit/agents/blob/main/examples/drive-thru/agent.py)
- Official Day 3 Task: [GitHub Repo](https://github.com/murf-ai/ten-days-of-voice-agents-2025/blob/main/challenges/Day%203%20Task.md)

---

## 🚀 Next Steps

### Potential Advanced Goals (Optional):
- **MCP Integration:** Connect to Notion/Todoist to turn goals into actual tasks
- **Weekly Reflection:** Aggregate JSON data for mood trends and goal completion rates
- **Follow-up Reminders:** Use MCP tools to create calendar events for self-care activities

---

## 🏆 Challenge Info

**Challenge:** Murf AI Voice Agents Challenge  
**Day:** 3 of 10  
**Focus:** Health & Wellness Voice Companion with JSON Persistence  
**Hashtags:** #MurfAIVoiceAgentsChallenge #10DaysofAIVoiceAgents

---

## 📄 Repository Structure

```
ten-days-of-voice-agents-2025/
│
├── backend/
│   ├── src/
│   │   ├── agent.py              # Main wellness agent code
│   │   └── wellness_log.json     # Auto-generated session data
│   └── .env                      # API keys
│
├── DAY1.md                       # Day 1 documentation
├── DAY2.md                       # Day 2 documentation
├── DAY3.md                       # This file
└── README.md                     # Project overview
```

---

**Built with ❤️ as part of the 10 Days of AI Voice Agents Challenge**  
**Powered by Murf Falcon - The Fastest TTS API**
