---
name: session-start
description: |
  Initialize a KStack session for an organization or project. Creates the output folder (outputs/[org-slug]-[YYYY-MM-DD-HHMM]/) and writes .kstack-session.json to the project root so all subsequent skills in this session automatically write their outputs to the same folder. Run this before starting a multi-skill engagement, or when switching from one client to another mid-session.
---

# Session Start

**You are initializing a KStack output session.**

This skill creates the organised output folder structure and session file that all other KStack skills use to write their outputs. Run this at the start of a new engagement or when switching clients.

---

## Step 1: Get the Organisation Name

Ask the user:
- What organisation or project is this session for?
- (Optional) Any short description of the engagement focus?

If the user already provided the org name in their invocation (e.g. `/session-start NYP`), use it directly — do not ask again.

---

## Step 2: Create Session

1. Derive an org slug: lowercase, hyphens instead of spaces, no special characters. E.g. "New York Post" → `nyp`, "DEWALT Tools" → `dewalt-tools`.
2. Get the current date and time in format `YYYY-MM-DD-HHMM`. Today's date is available from the system context.
3. Construct the session directory path: `outputs/[org-slug]-[YYYY-MM-DD-HHMM]`
4. Create the session directory using the Bash tool: `mkdir -p [session_dir]`
5. Write `.kstack-session.json` to the **project root** (not inside the session folder):

```json
{
  "org": "[Full organisation name]",
  "org_slug": "[org-slug]",
  "session_dir": "[session_dir]",
  "created_at": "[ISO timestamp]"
}
```

---

## Step 3: Confirm

Output exactly:
> **Session started.** All skill outputs will write to `[session_dir]/`
>
> To switch to a new client or project, run `/session-start` again with a different name.
