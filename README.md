<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Dark Chat UI</title>

<style>
    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
        font-family: Inter, Arial, sans-serif;
    }

    body {
        display: flex;
        height: 100vh;
        background: #0f0f10;
        color: #e5e5e5;
    }

    /* SIDEBAR */
    .sidebar {
        width: 260px;
        background: #151517;
        padding: 15px;
        display: flex;
        flex-direction: column;
        border-right: 1px solid #2a2a2a;
    }

    .sidebar h2 {
        font-size: 14px;
        margin-bottom: 10px;
        color: #aaa;
    }

    .chat-item {
        padding: 10px;
        margin: 5px 0;
        background: #1c1c1f;
        border-radius: 8px;
        cursor: pointer;
        font-size: 13px;
    }

    .chat-item:hover {
        background: #2a2a2e;
    }

    /* MAIN CHAT */
    .main {
        flex: 1;
        display: flex;
        flex-direction: column;
    }

    .topbar {
        padding: 15px;
        border-bottom: 1px solid #2a2a2a;
        background: #151517;
        font-size: 14px;
        color: #aaa;
    }

    .chat-area {
        flex: 1;
        padding: 20px;
        overflow-y: auto;
        display: flex;
        flex-direction: column;
        gap: 12px;
    }

    .msg {
        max-width: 70%;
        padding: 12px 14px;
        border-radius: 12px;
        line-height: 1.4;
        font-size: 14px;
        white-space: pre-wrap;
    }

    .user {
        align-self: flex-end;
        background: #2b6cff;
        color: white;
    }

    .bot {
        align-self: flex-start;
        background: #1c1c1f;
        border: 1px solid #2a2a2a;
    }

    /* INPUT */
    .input-bar {
        display: flex;
        padding: 12px;
        border-top: 1px solid #2a2a2a;
        background: #151517;
    }

    input {
        flex: 1;
        padding: 12px;
        border-radius: 10px;
        border: 1px solid #2a2a2a;
        background: #1c1c1f;
        color: white;
        outline: none;
    }

    button {
        margin-left: 10px;
        padding: 12px 16px;
        border: none;
        border-radius: 10px;
        background: #2b6cff;
        color: white;
        cursor: pointer;
    }

    button:hover {
        background: #1f5ae0;
    }
</style>
</head>

<body>

<div class="sidebar">
    <h2>Chats</h2>
    <div class="chat-item">New Chat</div>
    <div class="chat-item">Project Ideas</div>
    <div class="chat-item">Study Notes</div>
</div>

<div class="main">
    <div class="topbar">Dark Chat UI Template</div>

    <div class="chat-area" id="chat">
        <div class="msg bot">Hello! This is your AI-style chat template.</div>
        <div class="msg user">Nice, this looks clean.</div>
    </div>

    <div class="input-bar">
        <input id="input" placeholder="Type a message..." />
        <button onclick="sendMsg()">Send</button>
    </div>
</div>

<script>
function sendMsg() {
    const input = document.getElementById("input");
    const chat = document.getElementById("chat");

    if (!input.value.trim()) return;

    const userMsg = document.createElement("div");
    userMsg.className = "msg user";
    userMsg.textContent = input.value;
    chat.appendChild(userMsg);

    const botMsg = document.createElement("div");
    botMsg.className = "msg bot";
    botMsg.textContent = "This is a placeholder response.";
    
    setTimeout(() => {
        chat.appendChild(botMsg);
        chat.scrollTop = chat.scrollHeight;
    }, 500);

    input.value = "";
    chat.scrollTop = chat.scrollHeight;
}
</script>

</body>
</html>
