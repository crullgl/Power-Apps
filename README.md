<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  
</head>
<body>

<h1>🜭 Problem Decision Tool</h1>

<p><strong>As featured at the Microsoft Federal BizApps Summit</strong></p>

<p>
  The Problem Decision Tool streamlines how organizations classify and prioritize continuous improvement initiatives. Through a guided question interface, users are directed to the most appropriate improvement path — such as a Rapid Process Improvement Workshop (RPIW), or a Lean Yellow Belt, Green Belt, or Black Belt project.
</p>

<p>
  Built using Power Apps, the tool ensures the scope and complexity of a problem are matched with the right resources and methodologies. It supports data-informed decision-making and drives efficiency across service lines.
</p>

<h2>🛠️ Installation Guide</h2>

<ol>
  <li><strong>Download the App Package:</strong><br>
    <code>ProblemDecisionTool_20250317125920.zip</code> (Do not unzip)
  </li>
  <li><strong>Access Power Apps:</strong><br>
    <a href="https://make.powerapps.com" target="_blank">make.powerapps.com</a>
  </li>
  <li><strong>Import the App:</strong>
    <ul>
      <li>Go to Apps → Import canvas app</li>
      <li>Upload the ZIP file</li>
      <li>Select or create SharePoint/Power BI connections</li>
      <li>Click Import</li>
    </ul>
  </li>
  <li><strong>Launch and Share:</strong><br>
    Click <em>Play</em> to run the app, and <em>Share</em> to assign access.
  </li>
</ol>

<h2>🔗 Embedded Links & HTML Usage</h2>
<p>This app uses Power Apps' HTML Text control to render:</p>
<ul>
  <li>Links to websites and dashboards</li>
  <li>PDFs and Word docs</li>
  <li>Email contacts with <code>mailto:</code></li>
  <li>Embedded Power BI links</li>
</ul>

<h3>🔹 HTML Link Syntax:</h3>
<pre><code>&lt;a href="https://yourorg.com" target="_blank"&gt;Visit Site&lt;/a&gt;</code></pre>

<h3>🔹 Power Fx Example:</h3>
<pre><code>Set(varHTML, "&lt;a href='https://yourorg.com/resource' target='_blank'&gt;Open Document&lt;/a&gt;")</code></pre>

<h2>🧠 Conditional Power Fx Example</h2>
<pre><code>
Set(varReset,true); // Reset all but start
Set(varconsultinnovationspecialist,false); // Solution consult innovation specialist
Set(varNo1,true); // Is there a known standard that should be followed
Set(varNo2,false);
Set(varYes1,false);
Set(varIsthisproblemprocessrelated,false);
Set(varYesObviousSolution,false);
Set(varYes2JUDI,false);
Set(varIsthereasuspectedimprovement,false);
Set(varNo3,false);
Set(varWhatisthescope,false);
Set(varYellowbelt,false);
Set(varGreenbelt,false);
Set(varBlackbelt,false);
Set(varYellowbeltselected,false);
Set(varGreenbeltselected,false);
Set(varBlackbeltselected,false);
Set(vardoestheknownstandardneedtobeenhanced,false);
Set(varYes3Presenttheproblem,true);
Set(varYes4IsprocessRelated,false);
Set(varYes4Processrelated,false);
Set(varProcessrelatedandEnhanced,false);
Set(varYesStep1,true);
Set(varYesStepStep2,false);
</code></pre>

<h2>📈 ROI Breakdown</h2>
<ul>
  <li>5 unnecessary RPIWs avoided/year</li>
  <li>2,000 labor hours saved = $480,000/year</li>
  <li>App cost: $2,040 in manpower time and collaboration with a colleague</li>
  <li><strong>ROI: 23,429%</strong></li>
  <li>Potential enterprise-wide impact: $22M+</li>
</ul>
<img src="images/ROI-Screenshot.png" alt="ROI Summary">
<img src="images/Tool-Screenshot.png" alt="Decision Tool Screenshot">

<h2>🧰 Best Practices</h2>
<ul>
  <li>Store large HTML blocks in variables</li>
  <li>Always use trusted URLs</li>
  <li>Ensure users have access to resources</li>
</ul>

</body>
</html>
