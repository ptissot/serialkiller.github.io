# serialkiller.github.io
<!DOCTYPE html>
<html>
<head>
  <title>Just a Quick Check</title>
  <style>
    body {
      font-family: sans-serif;
      text-align: center;
      padding-top: 100px;
    }
    button {
      margin: 10px;
      padding: 10px 20px;
      font-size: 16px;
    }
    #response {
      margin-top: 30px;
      font-size: 20px;
      color: darkred;
    }
  </style>
</head>
<body>
  <h1>Please confirm you're not a serial killer</h1>
  <button onclick="respond('not')">I'm not 🙄</button>
  <button onclick="respond('sorry')">Sorry 🤷🏻‍♀️</button>
  <div id="response"></div>

  <script>
    function respond(answer) {
      const res = document.getElementById('response');
      if (answer === 'not') {
        res.textContent = "Great! I'll send my address soon.";
      } else {
        res.textContent = "I'll probably send it anyway tbf.";
      }

      // 🔔 Webhook tracking — replace URL with your own
      fetch('https://webhook.site/da886ec0-c661-4b85-9d72-33f174a0b9d9', {
        method: 'POST',
        body: JSON.stringify({ clicked: answer, timestamp: new Date().toISOString() }),
        headers: { 'Content-Type': 'application/json' }
      });
    }
  </script>
</body>
</html>
