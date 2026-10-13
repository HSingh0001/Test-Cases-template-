All .txt files are TAB-separated.
To use: open the file, Ctrl+A, Ctrl+C, then click cell A1 in a blank Excel sheet and Ctrl+V - it splits into columns.
00_Test_Cases_ADO.txt: paste into Excel, then Save As CSV to import into Azure DevOps Test Plans.

Form Field Validation – Parameter Library

What this is
Ready-made parameter rows for each field type, to paste into an Azure DevOps test case's Parameter values grid (or a Shared Parameter set).

Test case steps to use with these parameters
Step 1:  Open the form and go to <Page>   →   Page loads
Step 2:  @Action @Value in the @Field field and press Tab   →   @Message
Step 3:  Click Next   →   @NextResult

How to use
1. Pick the tabs that match the field types on your page.
2. Replace placeholders in <angle brackets> with your field names and options, and adjust example rules (max 50, 10 digits, 10 MB…) to your requirements.
3. Delete rows that don't apply (e.g. keep Mandatory OR Optional, not both).
4. Combine the rows for all fields on one page into one list.
5. Copy ONLY the blue columns (Field, Action, Value, Message, NextResult) and paste into Azure DevOps. Grey columns are for your reference – pasting them would create extra parameters.
6. Keep the 'Valid' row last, so the final iteration proves the page accepts good data.

Column guide
Field – field label as shown on screen
Action – Enter / Select / Tick / Untick / Leave empty / Leave default / Upload / Paste
Value – test data. Blank = leave empty. '–' = no value needed
Message – expected error or behaviour. Replace example wording with your form's actual messages
NextResult – what happens on Next.  '–' = no need to click Next for this row
Check type / Priority / Notes – reference only. With limited time, run P1 rows first

Security rows
Script/SQL/formula injection rows check the form treats input as plain text. Expected: value is rejected or shown as text everywhere (page, Review page, back-end, emails, exports) and nothing executes. Only run these in a test environment you are authorised to test.

Also check once per page (not parameterised)
• Leave everything empty → Next → all required errors show together + error summary at top
• Values kept after Back then Next, and shown correctly on the Review page