# Workflow & Automation Prompts

These are prompts designed to run inside automated workflows (Zapier, Make, Claude API) rather than typed manually each time.

---

## 1. Email Triage & Summary (used in Gmail → Claude Zapier workflow)

**Trigger:** New email arrives in Gmail
**What this prompt does:** Classifies and summarizes it so I can decide what to do without reading it fully

```
You are my email assistant. I just received this email:

Subject: {{subject}}
From: {{sender}}
Body: {{body}}

Do the following:
1. Classify it: [Urgent action needed / Reply required / FYI only / Spam/ignore]
2. One-sentence summary of what it's about
3. If action is needed: what specifically should I do?
4. Suggested reply (2-3 sentences) if a response is needed

Be brief. I'm scanning this in 10 seconds.
```

---

## 2. Slack Message Summarizer (used in Slack → Claude Zapier workflow)

**Trigger:** New message or thread in a monitored Slack channel
**What this prompt does:** Surfaces what matters without reading every message

```
Summarize this Slack message/thread:

Channel: {{channel}}
Message: {{message_text}}

Tell me:
- What is being discussed or decided?
- Is any action required from me?
- Is there anything time-sensitive?

If it's just FYI, say so. Keep it to 2-3 lines.
```

---

## 3. Content Idea Generator (scheduled workflow — runs weekly)

**Trigger:** Scheduled (every Monday morning)
**What this prompt does:** Generates fresh content ideas based on a client's niche

```
Generate 5 content ideas for a B2B company in [CLIENT NICHE].

For each idea:
- Working title
- Target keyword or topic angle
- Why it's relevant right now (trend, question buyers are asking, etc.)
- Suggested format (blog, LinkedIn post, landing page, video script)

Focus on ideas that are specific and timely, not evergreen basics.
Current date: {{current_date}}
```

---

## 4. Lead Research Brief (triggered by new CRM entry)

**Trigger:** New lead added to HubSpot / CRM
**What this prompt does:** Auto-generates a quick company brief so you walk into every call prepared

```
A new lead just came in:

Company: {{company_name}}
Contact: {{contact_name}}, {{contact_title}}
Website: {{website}}

Give me a quick brief:
1. What does this company do and who do they sell to?
2. Estimated company size and stage
3. What marketing challenges they likely have
4. One smart question I could ask them on a discovery call

Keep it to 5 bullet points. I need this before a call.
```

---

## 5. Meeting Notes → Action Items (post-call workflow)

**Trigger:** Manual paste after a call
**What this prompt does:** Extracts clean action items from messy notes

```
Here are my raw notes from a call:

{{notes}}

Extract:
- All action items (who owns each one, deadline if mentioned)
- Any open questions that need an answer
- Key decisions that were made
- Anything I need to follow up on

Format as a clean list I can copy into Notion or send to the client.
```

---

## Notes on Building Workflows

**Tools I use:**
- **Zapier** — connecting Claude to Gmail and Slack for automated triage and summaries
- **Make** — for more complex multi-step flows with conditional logic
- **Claude API** — for custom automations where I need more control over the prompt and output

**General principle:** The prompt is the workflow. A well-designed prompt with clear output instructions means you spend less time reformatting and more time acting on the output.
