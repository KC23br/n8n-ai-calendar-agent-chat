# Calendar Agent (n8n Workflow)

An AI-powered appointment scheduling assistant that can check calendar availability, retrieve meetings, look up contacts, and schedule new appointments through natural conversation.

## What It Does

```
Chat message received → AI Agent processes request
                        ↓
        ┌───────────────┼───────────────┐
        ↓               ↓               ↓
   Get Contacts    Get Meetings    Create Event
   (Google Sheets) (Google Calendar) (Google Calendar)
        ↓               ↓               ↓
        └───────────────┴───────────────┘
                        ↓
              AI responds to user
```

## Features

- **Conversational Interface**: Chat-based interaction for scheduling tasks
- **Contact Lookup**: Retrieves participant email/phone from Google Sheets
- **Calendar Queries**: Lists meetings and checks availability for any date range
- **Smart Scheduling**: Creates events with attendees, avoiding double-booking
- **Context Memory**: Remembers conversation history for natural follow-ups
- **Time-Aware**: Uses current date/time for accurate scheduling decisions

## Tech Stack

| Tool | Purpose |
|------|---------|
| n8n | Workflow automation |
| Google Gemini | AI language model for conversation |
| Google Calendar | Calendar management and event creation |
| Google Sheets | Contact directory storage |

## Quick Start

1. Import `Calendar Agent.json` into n8n
2. Set up credentials (Google Gemini, Google Calendar, Google Sheets)
3. Create a Google Sheet with contacts (Name, Email, Phone columns)
4. Update the Google Sheet document ID in the "Get Contacts" node
5. Update the calendar email in Calendar nodes
6. Activate workflow and start chatting

## Credentials Required

| Credential | How to Get |
|------------|------------|
| Google Gemini API | [Google AI Studio](https://aistudio.google.com/) |
| Google Calendar OAuth2 | n8n OAuth flow |
| Google Sheets OAuth2 | n8n OAuth flow |

## Contact Sheet Setup

Create a Google Sheet with these columns:

| Name | Email | Phone |
|------|-------|-------|
| John Doe | john@example.com | +1234567890 |

## AI Agent Capabilities

The agent can handle:

- **"What meetings do I have tomorrow?"** → Lists calendar events
- **"Schedule a call with John at 3pm on Friday"** → Looks up John's email, creates event
- **"Am I free next Monday afternoon?"** → Checks calendar availability
- **"Book a meeting with the marketing team"** → Gets contacts, schedules meeting

## Guardrails

The agent is designed to:
- Only handle scheduling-related requests
- Never fabricate contact information
- Always confirm details before booking
- Respect existing calendar events (no double-booking)
- Use current date/time context for scheduling

## Customization

1. **Change Calendar**: Update the calendar email in "Get Meetings" and "Create Event" nodes
2. **Update Contacts**: Link your own Google Sheet in the "Get Contacts" node
3. **Modify System Prompt**: Adjust the AI Agent's system message for different behavior
4. **Add More Tools**: Extend with email sending, reminders, etc.

## License

MIT - Use it, modify it, share it.

## Author

**Amna Mahmood**
- [LinkedIn](https://www.linkedin.com/in/amna-mahmood-70715149/)
- [Twitter](https://x.com/AmahmoodMahmood)

---

Star this repo if you found it useful!
