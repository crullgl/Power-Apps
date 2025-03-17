# Problem Decision Tool - as seen at Micr0soft Federal BizApps Summit

As Featured at the Microsoft Federal BizApps Summit
The Problem Decision Tool streamlines how organizations classify and prioritize continuous improvement initiatives. Through a simple, guided question interface, users are directed to the most appropriate improvement pathway — whether that be a Rapid Process Improvement Workshop (RPIW), or a Lean Yellow Belt, Green Belt, or Black Belt project.

This tool, built in Power Apps, ensures that the scope and complexity of a problem are matched with the right resources and methodologies, empowering data-driven decision-making while driving efficiency and Lean process improvements across service lines.
🛠️ Problem Decision Tool – Installation Guide
As featured at the Microsoft Federal BizApps Summit

The Problem Decision Tool helps users classify and route process improvement initiatives by guiding them through a simple question-based interface. It determines whether a Rapid Process Improvement Workshop (RPIW), Yellow Belt, Green Belt, or Black Belt project is most appropriate, supporting Lean methodologies and data-driven decision-making.

📁 Installation Instructions
1. Download the App Package
Click to download:
ProblemDecisionTool_20250317125920 (1).zip

Do not unzip this file — it must be imported as-is into Power Apps.

2. Access Power Apps
Go to https://make.powerapps.com
Sign in with your organizational account.
3. Import the App
In the left navigation pane, select Apps.
Click Import canvas app (top-right).
Click Upload and select the .zip file you downloaded.
Click Next and review the resources.
4. Configure Resources
Under Connections, select existing connections (e.g., SharePoint, Power BI) or create new ones if prompted.
Click Import to complete the setup.
5. Launch the App
Once imported, the app will appear under Apps.

Click Play to run the app.
Click Share to provide access to users or groups as needed.
🔗 Embedded Links & HTML Use in the App
This app uses the HTML Text control in Power Apps to dynamically render custom HTML content, including links to:

Websites (e.g., SharePoint, VA.gov)
Documents (PDFs, Word files)
Email addresses (mailto: links)
Power BI Reports
Example Link Syntax:
html
Copy
Edit
<a href="https://www.va.gov" target="_blank">Visit VA Website</a>
Example Power Fx for Dynamic Links:
powerapps
Copy
Edit
Set(varHTML, "<a href='https://www.va.gov' target='_blank'>Visit VA</a>")
The app intelligently changes guidance and embedded links based on user selections, improving user experience and engagement with resources.

🛡️ Notes & Best Practices
Ensure users have access to linked SharePoint resources and Power BI reports.
The HTML Text control is secure (no script execution) — but always use trusted URLs.
For performance, store complex HTML content in variables rather than inline in controls.

🧩 Custom HTML in Power Apps — Linking to Resources
The tool leverages the HTML Text control to dynamically present custom guidance and clickable links to:

🔗 Websites (e.g., yoursite.org, SharePoint)
📄 Documents (e.g., templates or resource folders)
👨‍💼 Email contacts (mailto: links)
📊 Power BI Reports
🔗 Basic HTML Link Syntax

<a href="URL_HERE" target="_blank">Link Text Here</a>
href: Destination (URL, document, email)
target="_blank": Opens in a new tab/window
Link Text Here: Clickable link label
💻 Examples of Links Used in the Tool:
1️⃣ Link to a Website:

<a href="https://www.va.gov" target="_blank">Visit VA Website</a>
2️⃣ Link to a SharePoint Document:

<a href="https://yourorg.sharepoint.com/sites/Docs/Shared%20Documents/Example.pdf" target="_blank">View PDF Document</a>
3️⃣ Email a Person:

<a href="mailto:john.doe@va.gov">Email John Doe</a>
🧠 Power Fx – Dynamic HTML with Variables
Power Fx allows dynamic link generation by concatenating values into the HTML string.

Example:
"<a href='https://yourorg.sharepoint.com/sites/Docs/" & FileName.Text & "' target='_blank'>Open Document</a>"
⚙️ Best Practices:
Use variables for large or dynamic HTML blocks:

Set(varHTML, "<a href='https://www.va.gov' target='_blank'>Visit VA</a>")
Then bind the HTML control to varHTML.

Ensure permissions for SharePoint/document links.

Trusted URLs only — HTML Text control doesn’t execute scripts (mitigates XSS risks).

🎯 The Decision Logic in Action (Power Fx Example)
Here’s how HTML links are conditionally embedded based on the project type selected in the tool:

🔍 Sample Power Fx Code:
powerapps


    If(
    varGreenbeltselected = true,
    "This problem requires a Lean A3 Deep Dive. A Green Belt project impacts 2-4 service lines. Completion can award Lean Green Belt certification if facilitated by a trained individual.<br><br>" &
    "Recruit support here: <a href='https://app.powerbigov.us/Redirect?...' target='_blank'>Power BI (powerbigov.us)</a><br><br>" &

    "Start with A3 templates: <a href='https://environment.sharepoint.com/sites/location/Shared%20Documents/...'
    target='_blank'>CNVAMC Systems Redesign - A-3 Documents</a><br><br>" &

    "Contact your Systems Redesign Coordinators for assistance.")
🎨 Optional Styling for Links:

<a href="https://va.gov" style="color:blue; font-weight:bold;" target="_blank">Bold Blue Link</a>
🏁 Summary:
The Problem Decision Tool doesn't just guide users — it empowers action by embedding direct access to relevant tools, contacts, and resources in real-time, all using HTML Text controls in Power Apps and smart Power Fx logic.

