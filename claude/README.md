# AI Smarty for Claude

This plugin connects Claude to your AI Smarty account so you can set up and look after your website's AI agent from a conversation. It adds one server, `aismarty`, at `https://aismarty.com/api/mcp`, and three skills: set up a support agent, weekly agent report, and install the widget in your codebase.

## Install

In Claude Code:

```
/plugin marketplace add aismarty/aismarty-plugins
/plugin install aismarty@aismarty
```

The source is at https://github.com/aismarty/aismarty-plugins.

## Sign in and access

The plugin signs in to AI Smarty with OAuth. You approve it on an AI Smarty consent screen, where you choose read only access or read and change access. The assistant never asks for, and never sees, your password, tokens or card details.

## What the tools do

**Set up**
- `get_account_status` shows your email verification and billing state.
- `list_agents` and `get_agent` show your AI agents, which are live, the setup checklist and the next step.
- `create_agent_from_website` creates an AI agent from a website address and starts reading the site.
- `publish_agent` makes an AI agent live, or sets it back to draft.

**Knowledge**
- `add_knowledge` adds a web page, pasted text or an attached document. When no file can be attached, it returns the upload link instead.
- `update_instructions` changes the AI agent's instructions.

**Testing**
- `test_agent` asks the AI agent up to three test questions. Nothing is saved to conversations or leads.

**Reporting**
- `get_summary` gives counts for today or the last 7 days.
- `list_unanswered_questions` shows what the AI agent could not answer.
- `answer_unanswered_question` saves your own answer as knowledge.

**Leads**
- `list_leads` lists leads with masked contacts.
- `get_lead_contact` returns the full contact for one named lead.

**Forms**
- `draft_form` drafts a form from one sentence and saves nothing.
- `save_form` saves it.

**Booking**
- `draft_booking_setup` drafts hours and appointment kinds and saves nothing.
- `save_booking_setup` saves them.
- `get_calendar_connect_link` returns a link to connect your calendar in the browser.

**Appearance and install**
- `update_appearance` changes colours, launcher text, welcome message, position and theme.
- `set_avatar` sets the avatar from an attached image, or returns the upload link.
- `check_widget_installed` checks that the widget is on a page of your site.

## What is sent and fetched

The assistant sends the tool inputs to AI Smarty, for example a website address, pasted text or an attached file. `create_agent_from_website` and `add_knowledge` fetch pages of the website you give them. `check_widget_installed` fetches one page of your own allowed domain and returns only whether the widget is present. Text written by website visitors comes back as plain text, and contacts are masked in lists. Changes ask for your confirmation before they run.

## Licence

MIT. See the LICENSE file at the root of this repository.
