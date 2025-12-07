Create a new workflow in n8n ( Form -> Sheets -> Gmail).

1.Add On form submission trigger and connect to your form provider (Google Forms / Typeform / custom webhook).

2.Configure the trigger to capture submission fields (e.g., name, email, message, timestamp).

3.Add Append row in sheet (Google Sheets) node and connect the trigger output to it.

4.Configure Google Sheets node: authenticate with Google, choose Spreadsheet and Sheet name.

5.Map form fields to sheet columns (e.g., Name → {{$json["name"]}}, Email → {{$json["email"]}}, Message → {{$json["message"]}}, SubmittedAt → {{$json["timestamp"]}}).

6.Set append mode (append as new row) and test the node by submitting a sample form — confirm a new row appears.

7.Add a Google Sheets Trigger node (event: rowAdded) and point it to the same spreadsheet and sheet.

8.Configure the Sheets Trigger to fire when a new row is added (use the same sheet and correct range if needed).

9.Add Send a message (Gmail) node and connect the Sheets Trigger output to it.

10.Configure Gmail node: authenticate, set To = {{$json["Email"]}} (or a fixed admin email), Subject = Thanks for your submission, Body = use mapped values like Hi {{$json["Name"]}}, thanks for submitting: {{$json["Message"]}}.

11.Add error handling: a Catch node to log failures or notify admin if either the Sheets append or Gmail send fails.

12.Test end-to-end: submit form → verify row appended → confirm trigger fires → confirm Gmail sent.


<img width="360" height="226" alt="n8n4" src="https://github.com/user-attachments/assets/381a1854-cabc-435d-88fb-0f144fddc6c6" />











Save workflow and export JSON for GitHub; keep API credentials in n8n Credentials (do not put keys in exported JSON).
