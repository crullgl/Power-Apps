# Problem Decision Tool - as seen at Micrsoft Federal BizApps Summit

The Decision Support Tool streamlines project classification by guiding users through a simple question-based interface to determine whether their initiative requires a Rapid Process Improvement Workshop (RPIW), Yellow Belt, Green Belt, or Black Belt project. Designed to enhance efficiency and reduce ambiguity, the tool ensures that resources and methodologies are aligned with the complexity and scope of each project, supporting data-driven decision-making and continuous improvement efforts across the organization.

In Power Apps, the HTML Text control lets you display custom HTML content. You can embed hyperlinks to:

Websites (e.g., SharePoint sites)
Documents (e.g., PDFs, Word files)
Email addresses (mailto: links)
Internal Power Apps URLs (deep linking)
🔗 Basic HTML Link Syntax
html
Copy
Edit
<a href="URL_HERE" target="_blank">Link Text Here</a>
href: The destination (website, document, or email).
target="_blank": Opens link in a new tab/window.
Link Text Here: What the user sees and clicks.
💻 Example 1 – Link to a Website
html
Copy
Edit
<a href="https://www.va.gov" target="_blank">Visit VA Website</a>
📄 Example 2 – Link to a Document in SharePoint
html
Copy
Edit
<a href="https://yourorg.sharepoint.com/sites/Docs/Shared%20Documents/Example.pdf" target="_blank">
View PDF Document
</a>
⚠️ SharePoint links must be shared with proper permissions.
👨‍💼 Example 3 – Link to Email a Person
html
Copy
Edit
<a href="mailto:john.doe@va.gov">Email John Doe</a>
🧠 Dynamic Data in Links – Using Concatenation
You can use Power Fx to dynamically insert URLs or names.

Example: Link to a document with dynamic file name:

powerapps
Copy
Edit
"<a href='https://yourorg.sharepoint.com/sites/Docs/Shared%20Documents/" & FileName.Text & "' target='_blank'>Open Document</a>"
⚡ Performance Tip:
Avoid embedding large HTML strings directly in the control. Use variables or collections if the content is complex or changes frequently.

Example with a variable:

powerapps
Copy
Edit
Set(varHTML, "<a href='https://www.va.gov' target='_blank'>Visit VA</a>")
Then bind the HTML Text control to varHTML.

🔒 Security Tip:
HTML Text controls do not execute scripts, which helps prevent XSS (cross-site scripting). Still, ensure URL sources are trusted.

🔧 Advanced Styling (Optional)
Customize links with inline styles:

Here is sample HTML:
If(
    varBlackbeltselected = true,
    "Sounds like this problem is complex enough to warrant a full Lean A3 Deep Dive. A Black belt project is essentially a project that impacts more than four Service lines or is organizational in scope. It also involves a situation where root causes behind a problem are essentially unknown. A completed black belt A3 project can award a lean black belt certification if the employee who facilitates the project has been through lean black belt training and has passed the lean black belt exam.<br><br>" &
    "We’d recommend discussing this particular situation with your Systems Redesign Coordinators to understand this issue further.",
    
    If(
        varGreenbeltselected = true,
        "Sounds like this problem is complex enough to warrant a full Lean A3 Deep Dive. A Green belt project is essentially a project that impacts 2-4 Service lines and involves a situation where root causes behind a problem are essentially unknown. A completed green belt A3 project can award a lean green belt certification if the employee who facilitates the project has been through lean green belt training and has passed the lean green belt exam.<br><br>" &
        "You can view a list of all belts by Service at this link to help recruit a green belt to help with this effort: <a href='https://app.powerbigov.us/Redirect?action=OpenReport&appId=4bfd4c0d-77d6-4423-a01c-39e708431587&reportObjectId=557558cb-b8cc-4ff5-9da2-cfe5d4c0beaa&ctid=e95f1b23-abaf-45ee-821d-b7ab251ab3bf&reportPage=ReportSection&pbi_source=appShareLink&portalSessionId=eb2b6f1c-43ab-4f06-ad48-c83c230cf536'>Power BI (powerbigov.us)</a><br><br>" &
        "Link on A3 resources to get started can also be found here: <a href='https://dvagov.sharepoint.com/sites/VHAAUGSR/Shared%20Documents/Forms/AllItems.aspx?id=%2Fsites%2FVHAAUGSR%2FShared%20Documents%2FTemplates%2FA%2D3&viewid=0d14f825%2D6c62%2D4228%2D9f05%2D1e2f3e4eca45'>CNVAMC Systems Redesign - A-3 - All Documents (sharepoint.com)</a><br><br>" &
        "Additionally,  you can contact your Systems Redesign Coordinators to register your problem as a green belt project idea</a>",
        
        If(
            varYellowbeltselected = true, 
            "Sounds like this problem is complex enough to warrant a full Lean A3 Deep Dive. A yellow belt project is essentially a project that impacts a single service line and involves a situation where root causes behind a problem are essentially unknown. A completed yellow belt A3 project can award a lean yellow belt certification if the employee who facilitates the project has been through lean yellow belt training and has passed the lean yellow belt exam. Reach out to your Systems Redesign Coordinators for help for your yellow belt project",
            
            If(
                varNo2 = true && varconsultinnovationspecialist = true,
                "Sounds like your problem may need to be explored further as it isn’t process related. Please reach out to your Systems Redesign Coordinators",
                If(
                    varYes2JUDI = true,
                    "It sounds like this specific situation may be a ‘Just Do It’ improvement. Just do it’s are situations where a known solution can be implemented relatively quickly. Go ahead with your improvement idea, and Just do it!<br>
            </a>",
                     If(
                varPSDAtrue = true,
                "Sounds like a pilot test of change will be needed using a Plan-Do-Study-Act methodology. These are best for smaller projects in a work area where we have a rough idea of something that we want to try, but we’ll need to study outcomes data after implementation to see if our test of change achieved desired outcomes.<br><br>" &
                "Feel free to reach out to your Systems Redesign Coordinators for templates you can use.</a>"
                )
            )
        )
    )
))


html
Copy
Edit
<a href="https://va.gov" style="color:blue; font-weight:bold;" target="_blank">Bold Blue Link</a>
