(HTML)
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Attendance Chatbot</title>
   <style>
     body {
  font-family: Arial, sans-serif;
  background: #f4f7f9;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}
.chat-container {
  width: 400px;
  background: #fff;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  overflow: hidden;
}
.chat-box {
  height: 400px;
  overflow-y: auto;
  padding: 10px;
}
.chat-input {
  display: flex;
  border-top: 1px solid #ccc;
}
.chat-input input {
  flex: 1;
  padding: 10px;
  border: none;
}
.chat-input button {
  padding: 10px 20px;
  background: #4CAF50;
  color: white;
  border: none;
  cursor: pointer;
}
.user-msg, .bot-msg {
  margin: 10px 0;
  padding: 8px 12px;
  border-radius: 10px;
  max-width: 80%;
}
.user-msg {
  background: #DCF8C6;
  align-self: flex-end;
  text-align: right;
}
.bot-msg {
  background: #e2e2e2;
  align-self: flex-start;
}
</style>
  
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

  <script>
    function sendMessage() {
  const input = document.getElementById("user-input");
  const message = input.value.trim();
  if (message === "") return;

  const chatBox = document.getElementById("chat-box");

  
  const userMsg = document.createElement("div");
  userMsg.className = "user-msg";
  userMsg.innerText = message;
  chatBox.appendChild(userMsg);

  
  const botResponse = getBotReply(message);
  const botMsg = document.createElement("div");
  botMsg.className = "bot-msg";
  botMsg.innerText = botResponse;
  chatBox.appendChild(botMsg);

  
  chatBox.scrollTop = chatBox.scrollHeight;

  
  input.value = "";
}

function getBotReply(message) {
  message = message.toLowerCase();

  if (message.includes("hello") || message.includes("hi")) {
    return "Hello! How can I help you today?";
  } else if (message.includes("attendance")) {
    return "You can view your attendance by clicking 'View Attendance' tab.";
  } else if (message.includes("mark")) {
    return "To mark attendance, go to the 'Mark Attendance' section.";
  } else if (message.includes("download") || message.includes("report")) {
    return "You can download the attendance report from the 'Download' page.";
  } else {
    return "Sorry, I didn’t understand that. Please ask something else.";
  }
}
  </script>
</body>
</html>

