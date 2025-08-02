<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Attendance Chatbot</title>
  <link rel="stylesheet" href="chatbot.css">
</head>
<body>
  <div class="chat-container">
    <div class="chat-box" id="chat-box">
      <div class="bot-msg">Hi! Im your Attendance Assistant <br>What can I do for you?</div>
    </div>
    <div class="chat-input">
      <input type="text" id="user-input" placeholder="Type your message...">
      <button onclick="sendMessage()">Send</button>
    </div>
  </div>

  <script src="chatbot.js"></script>
</body>
</html>
