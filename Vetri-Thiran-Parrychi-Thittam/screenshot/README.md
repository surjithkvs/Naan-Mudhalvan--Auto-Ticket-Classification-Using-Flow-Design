# Vetri-Thiran-Parrychi-Thittam
Auto Ticket Classification using Flow Designer
Create Update Set: Navigate to System Update Sets > Local Update Sets, click New, set the Name to Project Update Set in the Global application scope with state In progress, and save.
<img alt="1" src="https://github.com/user-attachments/assets/b83468cf-004a-446d-a27b-cb689627f90a" />

Set as Active: Click Make This My Current Set under Related Links so the system banner and top toolbar confirm it as your active context.
<img alt="2" src="https://github.com/user-attachments/assets/e7f84540-3aa6-4526-8da2-b4a178610270" />


Create Custom Table: Navigate to System Definition > Tables, click New, and set the Label to Incident Workflow (auto-generating table name u_incident_workflow) in the Global application scope.
<img alt="1" src="https://github.com/user-attachments/assets/b24a1a9b-3029-4cde-8f30-7341ce637196" />


Configure Auto-Numbering: On the Controls tab, enable Auto-number, set the Prefix to INC, Number to 1,000, and Number of digits to 5 to auto-generate ticket IDs.
<img alt="2" src="https://github.com/user-attachments/assets/744f6353-0281-4ef9-9fc0-e7cc08db7aa6" />

Navigate to Form Design: Open the form context menu (≡), select Configure, and click Form Design.
<img alt="3" src="https://github.com/user-attachments/assets/960fb31f-28d7-42e6-8289-f03f7fb3c697" />

Design Form Layout: In Form Design, structure a two-column layout containing Number, Caller, Category, Subcategory, Short Description, Description, State, Assigned Group, and Assigned to.
<img alt="4" src="https://github.com/user-attachments/assets/96075355-b062-4fd0-aa80-564b03c10f7f" />

Configure Dependent Field Logic: Open the Dictionary Entry for Subcategory, switch to the Dependent Field tab, check Use dependent field, and set Dependent on field to Category.
<img alt="5" src="https://github.com/user-attachments/assets/03901086-adeb-4165-9bf5-0b37d7d4dab0" />

Create Trigger: Configure the flow trigger to run when a Record Created action occurs on the Incident Workflow (u_incident_workflow) table with the condition where Category is empty.
<img alt="1" src="https://github.com/user-attachments/assets/d109d6a8-1a62-46df-8726-2f76617e4976" />


If (Network / Wi-Fi): Configure an If condition (SD is Wifi or Network) to check if the Short Description or Description contains "Wi-Fi" or "Network", followed by an Update Record action setting Category to Network and Subcategory to Wi-Fi.
<img alt="3" src="https://github.com/user-attachments/assets/c4f7b9c6-60a9-4c59-afb3-96881a0a0008" />
<img alt="2" src="https://github.com/user-attachments/assets/52ed8596-82b3-4514-9d91-19515924ead5" />

Else If (Hardware / Projector): Configure an Else If condition (SD is Projector or Hardware) to check if the Short Description or Description contains "Projector" or "Hardware", followed by an Update Record action setting Category to Hardware and Subcategory to Projector.
<img alt="4" src="https://github.com/user-attachments/assets/1c9cf53e-19ac-4553-98e2-f8eb4dd804e0" />
<img alt="5" src="https://github.com/user-attachments/assets/e48ba240-9ed0-475b-bdeb-f3be5f0129f2" />

Else If (Access / Password): Configure an Else If condition (SD is Forgot password or Access) to check if the Short Description or Description contains "Forgot Password" or "Access", followed by an Update Record action setting Category to Access and Subcategory to Forgot Password.
<img alt="6" src="https://github.com/user-attachments/assets/9c4541f2-4410-43c7-8493-11ae5fe05634" />
<img alt="7" src="https://github.com/user-attachments/assets/17cc6605-2866-42af-96fb-6c6393a891fa" />

Else If (Performance / Slow Computer): Configure an Else If condition (SD is Performance) to check if the Short Description or Description contains "Slow Computer" or "Performance", followed by an Update Record action setting Category to Performance and Subcategory to Slow Computer.
<img alt="8" src="https://github.com/user-attachments/assets/ca76d182-3df7-4901-aa35-30147c766bb5" />
<img alt="9" src="https://github.com/user-attachments/assets/7441994d-34d5-4063-80dc-66e2174f71b5" />

Send Email: Add a Send Email action configured to automatically deliver a submission confirmation message to the ticket requester.
<img alt="10" src="https://github.com/user-attachments/assets/91f96665-148c-4d05-93da-1cef532611a5" />

Test Case 1 (Wi-Fi Issue): Create a new incident ticket (INC01041) for caller Alfonso Griglen with the short description "Wi-Fi not working.".   Auto-Classification (Network): Verify that the flow automatically updates the record's Category to Network and Subcategory to Wi-Fi.   
<img alt="1" src="https://github.com/user-attachments/assets/448d371a-7552-4200-9113-995b5b8d0388" />
<img alt="2" src="https://github.com/user-attachments/assets/a3859942-6d8e-4b95-a1a2-85595ef4bc2a" />

Email Notification: Verify the generated send-ready email log and preview the confirmation message sent to alfonso.griglen@example.com.
<img alt="3" src="https://github.com/user-attachments/assets/e2291679-b70d-492f-a5fd-d4d706f2befb" />
<img alt="4" src="https://github.com/user-attachments/assets/06a17d84-2445-4801-9ca6-a2eeab9441b9" />

Test Case 2 (Hardware Issue): Create a second incident ticket (INC01042) for caller Sam Sorokin with the short description "Projector not working.".   Auto-Classification (Hardware): Verify that the flow automatically updates the record's Category to Hardware and Subcategory to Projector.
<img alt="5" src="https://github.com/user-attachments/assets/319e3e53-8f50-4d42-a197-96c8439f5256" />
<img alt="6" src="https://github.com/user-attachments/assets/e6e40264-0f70-4ea1-a152-99dd7cf66447" />

Mark Update Set Complete: Change the State of Project Update Set to Complete to finalize and lock the captured customizations.
<img alt="2" src="https://github.com/user-attachments/assets/b464ea5f-26b4-40c6-9052-b4c78e45233e" />

Export Update Set XML: Click Export to XML under Related Links to download the XML payload file for deployment to other ServiceNow instances.
<img alt="1" src="https://github.com/user-attachments/assets/6ce50559-f85e-4123-a422-35f5a7d56888" />


















