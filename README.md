<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>GitHub README Generator</title>
  <style>
    body {
      font-family: 'Segoe UI', sans-serif;
      margin: 20px;
      background-color: #f9f9f9;
    }
    label, input, textarea, select {
      display: block;
      width: 100%;
      margin-bottom: 15px;
    }
    textarea {
      height: 100px;
    }
    button {
      padding: 10px 20px;
      background-color: #007acc;
      color: white;
      border: none;
      cursor: pointer;
    }
    pre {
      background: #eee;
      padding: 10px;
      white-space: pre-wrap;
    }
  </style>
</head>
<body>
  <h1>README.md Generator</h1>
  <form id="readmeForm">
    <label>Project Title</label>
    <input type="text" id="title" required />

    <label>Description</label>
    <textarea id="description" required></textarea>

    <label>Installation</label>
    <textarea id="installation"></textarea>

    <label>Usage</label>
    <textarea id="usage"></textarea>

    <label>License</label>
    <select id="license">
      <option value="MIT">MIT</option>
      <option value="GPL-3.0">GPL 3.0</option>
      <option value="Apache-2.0">Apache 2.0</option>
      <option value="None">None</option>
    </select>

    <label>GitHub Username</label>
    <input type="text" id="github" required />

    <label>Email</label>
    <input type="email" id="email" />

    <button type="button" onclick="generateReadme()">Generate</button>
  </form>

  <h2>Generated README.md</h2>
  <pre id="output"></pre>

  <script>
    function generateReadme() {
      const title = document.getElementById("title").value;
      const description = document.getElementById("description").value;
      const installation = document.getElementById("installation").value;
      const usage = document.getElementById("usage").value;
      const license = document.getElementById("license").value;
      const github = document.getElementById("github").value;
      const email = document.getElementById("email").value;

      const licenseBadge = license !== "None" ? `![License](https://img.shields.io/badge/License-${license}-blue.svg)` : '';

      const readmeContent = `# ${title}

${licenseBadge}

## Description
${description}

## Installation
${installation || 'No installation steps provided.'}

## Usage
${usage || 'No usage instructions provided.'}

## License
This project is licensed under the ${license} license.

## Contact
GitHub: [${github}](https://github.com/${github})  
${email ? `Email: ${email}` : ''}`

      document.getElementById("output").textContent = readmeContent;
    }
  </script>
</body>
</html>
