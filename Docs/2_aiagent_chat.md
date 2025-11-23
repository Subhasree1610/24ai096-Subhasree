Create a new workflow in n8n and name it[CHAT ->GEMINI AI AGENT]

Add When chat message received (Webhook or platform-specific) as the trigger.

Configure trigger: set endpoint/path, method (POST) or platform event, and map userId, text, channelId.

Add an AI Agent node and connect the trigger output to it.

Set the AI Agent Chat Model to Google Gemini Chat (provider ID used by your n8n).

Map the user message into the Agent input: {{$json["text"]}}.

Configure model params: temperature, max tokens, stop sequences (e.g., temperature 0.2, max tokens 800).

Add an output node to send the AI reply back to chat (map reply: {{$node["AI Agent"].json["reply"]}}).

Add error handling: a Catch node to log errors and notify admin or retry.

Save and export: save workflow in n8n, export JSON to your GitHub repo, and store API keys as n8n Credentials (do NOT hardcode keys).

<img width="408" height="216" alt="n8n2" src="https://github.com/user-attachments/assets/c290c924-1ce9-4381-b3b2-53ebf8d43bee" />












