Manual click → send Gmail (n8n)

1.Create a new workflow — Click + New, name it Click → Gmail.

2.Add Manual Trigger — Add the Manual Trigger node (this lets you run the workflow by clicking Execute Workflow).

3.Add Gmail node — Add the Gmail (or Google Gmail) node to the canvas.

4.Connect nodes — Drag a connection from Manual Trigger → Gmail.

5.Create Gmail credentials — In the Gmail node click Credentials → New, choose Gmail OAuth2 / Google Gmail, follow the OAuth flow and save the credential.

6.Configure Gmail node — Set Resource = Message, Operation = Send, fill To (e.g., your-email@gmail.com), Subject (Test from n8n), and Text (This email was sent by executing the workflow in n8n.).

7.Save the workflow — Click Save.

8.Run it — Click Execute Workflow; the Manual Trigger runs and the Gmail node sends the email. Check the recipient inbox.

<img width="557" height="200" alt="n8n1" src="https://github.com/user-attachments/assets/47d17d40-9436-43e6-8fc6-0a6c0e4dfc9f" />
