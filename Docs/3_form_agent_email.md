Create a new workflow in n8n and name it (Form -> Gemini -> Gmail).

Add On form submission trigger and connect your form provider (Typeform/Google Forms/Form webhook).

Configure trigger to receive submitted fields; note common fields: name, email, message, otherAnswers.

Add an AI Agent node and connect the trigger output to it.

In AI Agent set Chat Model to Google Gemini Chat (use the provider ID available in your n8n).

Map the form data into the agent prompt. Example prompt:
User submission from {{$json["name"]}} ({{$json["email"]}}): {{$json["message"]}} — Compose a friendly reply.

Set model params: temperature (e.g. 0.2), max tokens (e.g. 600), and any stop sequences.

(Optional) Enable Memory if you want context across submissions; use key submissions:{{$json["email"]}}.

(Optional) Attach Tools (HTTP request, DB) if the agent must look up or store data before replying.

Add Send a message (Gmail) node and connect AI Agent output to it.

Configure Gmail node: authenticate, set To = {{$json["email"]}} or map to field, Subject = e.g. Re: Your submission, Body = {{$node["AI Agent"].json["reply"]}} (or the field name your agent returns).

Add error handling (Catch node): log failures, notify admin email, or retry on transient errors.

Test: submit a sample form, inspect execution in n8n, verify the Gmail node sends the expected email.

<img width="534" height="213" alt="n8n3" src="https://github.com/user-attachments/assets/c5b724b1-dac6-4488-9918-85c2a5430af2" />












Save & export workflow JSON for GitHub; keep API keys in n8n Credentials, never in the exported file.
