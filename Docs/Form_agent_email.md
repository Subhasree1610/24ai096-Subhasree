Form → AI Agent → Email Workflow

Start with a Google Form – Create a form that collects user details (name, email, message, etc.).

Add “On Form Submission” Trigger – In n8n, connect your Google Form using the Form Submission trigger so the workflow starts automatically when a user submits.

Test the Trigger Output – Submit a sample form response and check the fields coming into n8n (like name, email, message).

Add the AI Agent Node – Drag in the AI Agent node and connect it to the trigger.

Select Google Gemini Chat Model – Under the AI Agent node, choose the Google Gemini Chat Model as the chat model.

Write the Prompt – Use form data inside the prompt (example: “User message: {{$json[‘message’]}}”) to generate an AI reply.

Configure Optional Tools/Memory – If needed, enable memory or tools for better responses (optional).

Connect AI Output to Gmail Node – Add a Send a Message (Gmail) node and map the AI output text into the email body.

Set Email Fields – Set “To” using the user’s form email, add subject, and paste the AI reply as the message.

Test & Activate Workflow – Run a full test (form → AI → email) and then activate the workflow for live use.










