<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Samad AI Assistant</title>

  <style>
    body {
      font-family: Arial, sans-serif;
      background: linear-gradient(135deg, #0f172a, #1e293b);
      color: white;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
    }

    .box {
      width: 420px;
      background: #111827;
      padding: 25px;
      border-radius: 16px;
      box-shadow: 0 0 25px rgba(0,0,0,0.6);
    }

    h1 {
      text-align: center;
      margin-bottom: 5px;
      color: #22c55e;
    }

    p {
      text-align: center;
      font-size: 13px;
      color: #94a3b8;
      margin-bottom: 15px;
    }

    input {
      width: 100%;
      padding: 12px;
      border-radius: 10px;
      border: none;
      outline: none;
      margin-top: 10px;
      font-size: 14px;
    }

    button {
      width: 100%;
      padding: 12px;
      margin-top: 10px;
      background: #22c55e;
      border: none;
      border-radius: 10px;
      font-weight: bold;
      cursor: pointer;
      font-size: 15px;
    }

    button:hover {
      background: #16a34a;
    }

    .output {
      margin-top: 15px;
      background: #0f172a;
      padding: 12px;
      border-radius: 10px;
      min-height: 60px;
      font-size: 14px;
      color: #cbd5e1;
    }

    .tag {
      text-align: center;
      font-size: 11px;
      margin-top: 10px;
      color: #64748b;
    }
  </style>
</head>

<body>

<div class="box">
  <h1>Samad AI Assistant</h1>
  <p>Your Smart Automation Assistant</p>

  <input type="text" id="cmd" placeholder="Type command... (YouTube, Google, song search)">
  <button onclick="runCommand()">Run Command</button>

  <div class="output" id="output">
    Waiting for command...
  </div>

  <div class="tag">Made with ❤️ for Automation</div>
</div>

<script>
function runCommand() {
  let cmd = document.getElementById("cmd").value.toLowerCase();
  let output = document.getElementById("output");

  if(cmd.includes("youtube")) {
    output.innerHTML = "🎬 Opening YouTube...";
    window.open("https://www.youtube.com", "_blank");
  }

  else if(cmd.includes("google")) {
    output.innerHTML = "🌐 Opening Google...";
    window.open("https://www.google.com", "_blank");
  }

  else if(cmd.includes("song")) {
    let query = cmd.replace("song", "");
    output.innerHTML = "🎵 Searching song: " + query;
    window.open("https://www.youtube.com/results?search_query=" + query, "_blank");
  }

  else if(cmd.includes("video upload")) {
    output.innerHTML = "⚠ Video upload automation requires YouTube API integration (next level feature)";
  }

  else if(cmd.includes("seo")) {
    output.innerHTML = "⚠ SEO automation needs backend + YouTube API system";
  }

  else if(cmd.trim() === "") {
    output.innerHTML = "Please type a command first...";
  }

  else {
    output.innerHTML = "❌ Command not recognized. Try: YouTube, Google, song search";
  }
}
</script>

</body>
</html>
