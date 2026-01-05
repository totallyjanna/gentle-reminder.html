<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Daily Pause</title>

  <style>
    body {
      margin: 0;
      height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;

      background: #f6f7f5;
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
      color: #333;
    }

    .container {
      width: 90%;
      max-width: 480px;
      padding: 32px;
    }

    .prompt {
      font-size: 1.2rem;
      line-height: 1.6;
      margin-bottom: 24px;
    }

    textarea {
      width: 100%;
      min-height: 160px;
      border: none;
      resize: none;
      padding: 16px;
      font-size: 1rem;
      line-height: 1.5;

      background: #ffffff;
      border-radius: 12px;
      box-shadow: 0 4px 12px rgba(0,0,0,0.04);
      outline: none;
    }

    textarea::placeholder {
      color: #aaa;
    }

    button {
      margin-top: 24px;
      background: none;
      border: none;
      font-size: 0.95rem;
      color: #777;
      cursor: pointer;
    }

    button:hover {
      color: #444;
    }
  </style>
</head>

<body>
  <div class="container">
    <div class="prompt" id="prompt"></div>

    <textarea
      placeholder="Write anything. Or nothing."
    ></textarea>

    <button onclick="closeDay()">Close the day</button>
  </div>

  <script>
    const prompts = [
      "What stayed with you today?",
      "What felt heavy? What felt light?",
      "What do you want to let go of?",
      "What deserves a little gratitude?",
      "What do you need tomorrow?",
      "What mattered today, even briefly?"
    ];

    const promptEl = document.getElementById("prompt");

    // pick one prompt per load
    const todayPrompt =
      prompts[Math.floor(Math.random() * prompts.length)];

    promptEl.textContent = todayPrompt;

    function closeDay() {
      document.querySelector("textarea").value = "";
      alert("That’s enough for today.");
    }
  </script>
</body>
</html>
