<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Customer Care Chatbot</title>
  <style>
    body { font-family: Arial, sans-serif; margin: 0; padding: 0; }
    header { background: #4CAF50; color: white; padding: 15px; text-align: center; }
    .container { padding: 20px; text-align: center; }
    .chatbox { width: 300px; margin: 20px auto; border: 1px solid #ccc; border-radius: 10px; padding: 10px; }
    .messages { height: 200px; overflow-y: auto; border-bottom: 1px solid #ccc; margin-bottom: 10px; }
    input { width: 70%; padding: 8px; }
    button { padding: 8px 12px; }
  </style>
</head>
<body>

<header>
  <h1>Customer Support Chatbot</h1>
</header>

<div class="container">
  <p>Welcome! Ask your questions below 👇</p>

  <div class="chatbox">
    <div class="messages" id="messages"></div>
    <input type="text" id="userInput" placeholder="Type your message...">
    <button onclick="sendMessage()">Send</button>
  </div>
</div>

<script>
function sendMessage() {
  const input = document.getElementById("userInput");
  const messages = document.getElementById("messages");

  let userText = input.value;
  if(userText === "") return;

  messages.innerHTML += `<p><b>You:</b> ${userText}</p>`;

  let botReply = getBotReply(userText);
  messages.innerHTML += `<p><b>Bot:</b> ${botReply}</p>`;

  input.value = "";
  messages.scrollTop = messages.scrollHeight;
}

function getBotReply(input) {
  input = input.toLowerCase();

  if(input.includes("hello") || input.includes("hi")) {
    return "Hello! How can I help you today?";
  } else if(input.includes("price")) {
    return "Our pricing details are available on the website.";
  } else if(input.includes("contact")) {
    return "You can contact us at support@example.com";
  } else {
    return "Sorry, I didn't understand that. Can you rephrase?";
  }
}
</script>

</body>
</html>
