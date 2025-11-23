Manual click → send Gmail (n8n)

Create a new workflow — Click + New, name it Click → Gmail.

Add Manual Trigger — Add the Manual Trigger node (this lets you run the workflow by clicking Execute Workflow).

Add Gmail node — Add the Gmail (or Google Gmail) node to the canvas.

Connect nodes — Drag a connection from Manual Trigger → Gmail.

Create Gmail credentials — In the Gmail node click Credentials → New, choose Gmail OAuth2 / Google Gmail, follow the OAuth flow and save the credential.

Configure Gmail node — Set Resource = Message, Operation = Send, fill To (e.g., your-email@gmail.com), Subject (Test from n8n), and Text (This email was sent by executing the workflow in n8n.).

Save the workflow — Click Save.

Run it — Click Execute Workflow; the Manual Trigger runs and the Gmail node sends the email. Check the recipient inbox.

<img width="557" height="200" alt="n8n1" src="https://github.com/user-attachments/assets/47d17d40-9436-43e6-8fc6-0a6c0e4dfc9f" />
