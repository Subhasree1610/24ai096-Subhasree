Populating Two Sheets

1 Add the Execute Trigger
Drag the “When clicking ‘Execute workflow’” trigger node to start the workflow manually.

2 Insert Google Sheets Read Node
Add a “Get row(s) in sheet” node and connect it to the trigger.

3 Select Spreadsheet & Sheet
In the read node, choose your Google Sheet file and the sheet name you want to read from.

4 Fetch All Rows
Set the read node to Return All so it loads every row from the sheet.

5 Add an If Node
Add an If node after the read node to check a condition for each row (example: Status = “Yes”).

6 Configure the Condition
In the If node, choose the field and condition (example:
If Column A equals “Approved” → true).

7 Add Google Sheet Node for Sheet1
Connect the true output of the If node to an “Append row in sheet1” node.

8 Map Data for Sheet1
Select the target spreadsheet (Sheet1) and map the incoming fields to the columns.

9 Add Google Sheet Node for Sheet2
Connect the false output to another “Append row in sheet2” node.

10 Execute the Workflow
Click Execute Workflow and verify rows go to Sheet1 for true, and Sheet2 for false.

<img width="895" height="384" alt="Screenshot 2025-12-07 114148" src="https://github.com/user-attachments/assets/812a0994-5265-42e2-a662-9ef1b27f2675" />




