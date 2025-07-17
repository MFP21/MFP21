<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>README Generator</title>
  <style>
    body {
      font-family: sans-serif;
      max-width: 700px;
      margin: 40px auto;
      padding: 20px;
    }
    input, textarea {
      width: 100%;
      margin: 8px 0 16px;
      padding: 8px;
      font-size: 1rem;
    }
    button {
      padding: 10px 20px;
      font-size: 1rem;
      cursor: pointer;
    }
    pre {
      background: #f4f4f4;
      padding: 15px;
      white-space: pre-wrap;
      word-break: break-word;
      margin-top: 20px;
    }
  </style>
</head>
<body>
  <h1>README.md Generator</h1>
  
  <label>📌 Project Title</label>
  <input type="text" id="title" />

  <label>📝 Description</label>
  <textarea id="description" rows="4"></textarea>

  <label>🚀 Installation Instructions</label>
  <textarea id="installation" rows="3"></textarea>

  <label>⚙️ Usage</label>
  <textarea id="usage" rows="3"></textarea>

  <label>💡 Features</label>
  <textarea id="features" rows="3"></textarea>

  <label>🧪 Tests</label>
  <textarea id="tests" rows="3"></textarea>

  <label>📩 Contact (Email or GitHub)</label>
  <input type="text" id="contact" />

  <button onclick="generateReadme()">Generate README</button>

  <h2>📄 Preview</h2>
  <pre id="output"></pre>

  <script>
    function generateReadme() {
      const title = document.getElementById("title").value;
      const description = document.getElementById("description").value;
      const installation = document.getElementById("installation").value;
      const usage = document.getElementById("usage").value;
      const features = document.getElementById("features").value;
      const tests = document.getElementById("tests").value;
      const contact = document.getElementById("contact").value;

      const readme = `
# ${title}

## 📋 Description
${description}

## 📦 Installation
\`\`\`bash
${installation}
\`\`\`

## ▶️ Usage
${usage}

## ✨ Features
${features}

## 🧪 Tests
${tests}

## 📬 Contact
${contact}
      `;

      document.getElementById("output").textContent = readme.trim();
    }
  </script>
</body>
</html>
