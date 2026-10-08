---
name: set-up-support-agent
description: Guide the user through creating, testing and publishing an AI Smarty AI agent for their website, one confirmed step at a time. Use when the user wants to set up an AI agent or customer support agent.
---

# Set up an AI agent

Work through these steps in order. Use the AI Smarty tools only. Never ask for or pass passwords, tokens, API keys or card details.

## Confirm before every change

Before calling any tool that changes something (`create_agent_from_website`, `add_knowledge`, `update_instructions`, `save_form`, `save_booking_setup`, `update_appearance`, `set_avatar`, `publish_agent`), show the user exactly what will change and wait for a clear yes. For `update_instructions`, show the current text and the new text side by side, before and after. If the user says no or changes their mind, stop and adjust.

## Steps

1. Call `get_account_status`. Check that the email is verified and billing is set up. If not, tell the user what is missing and that it is done in the AI Smarty dashboard, then wait.
2. Ask for the website address. Confirm it, then call `create_agent_from_website`. It starts reading the public pages of that site.
3. Call `get_agent` for the setup checklist and the next step. Repeat it after each later step and tell the user what is done and what is left.
4. Offer `add_knowledge` for anything the website does not cover: one web page, pasted text, or an attached document. If an attached file cannot be passed, the tool returns the dashboard page for uploading it.
5. Offer `update_instructions` if the user wants to change how the AI agent behaves. Show before and after first.
6. Call `test_agent` with up to three realistic questions and show the answers. If an answer is wrong, add knowledge or adjust instructions, then test again.
7. Offer a lead form: call `draft_form` with one sentence from the user, show the draft, and call `save_form` only after a yes.
8. Optional, only if the user wants appointments: call `draft_booking_setup`, show the draft, then `save_booking_setup` after a yes. If no calendar is connected, call `get_calendar_connect_link` and ask the user to open the link in their browser and connect it there. Without a connected calendar, booking is saved as off.
9. Optional: `update_appearance` for colour, launcher text, welcome message, position and theme, and `set_avatar` for an avatar image. Show the settings first.
10. Call `publish_agent` after the user confirms they want the AI agent live. If it reports missing setup, go back to that step.
11. Install the widget: call `get_agent` for the install snippet and explain where it goes. In a code project, the install-widget skill can place it. After the site is deployed, call `check_widget_installed` with a live page address on the allowed domain and report the result.

Only describe what the tools do. Cancelling or rescheduling appointments and editing existing forms are done in the AI Smarty dashboard.
