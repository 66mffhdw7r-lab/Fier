<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1.0">
<title>FIERLESS Hub - Roblox Exploit Collection</title>
<style>
    body {
        background-color: #0d0d0d;
        color: #fff;
        font-family: 'Fredoka One', Arial, sans-serif;
        margin: 0;
        padding: 0;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        min-height: 100vh;
        text-align: center;
    }

    .header {
        margin-top: 40px;
    }

    .title {
        font-size: 3em;
        color: #ff4040;
        text-shadow: 0 0 15px rgba(255, 64, 64, 0.8);
        letter-spacing: 2px;
    }

    .subtitle {
        font-size: 1.3em;
        color: #ccc;
        margin-top: -8px;
    }

    .verification-box {
        background-color: #181818;
        border: 3px solid #ff4040;
        border-radius: 20px;
        padding: 20px;
        width: 85%;
        max-width: 420px;
        margin: 25px auto;
        box-shadow: 0 4px 18px rgba(255, 64, 64, 0.3);
        transition: 0.3s;
    }

    .verification-box:hover {
        transform: scale(1.02);
        box-shadow: 0 0 25px rgba(255, 64, 64, 0.5);
    }

    .verify-title {
        font-size: 2em;
        color: #ff4040;
        margin-bottom: 15px;
    }

    .verify-text {
        color: #aaa;
        font-size: 1em;
    }

    input[type="text"] {
        background-color: #252525;
        border: 2px solid #ff4040;
        color: #fff;
        padding: 10px;
        border-radius: 8px;
        width: 80%;
        margin: 10px 0;
    }

    .verify-button {
        background-color: #00ff66;
        color: #000;
        border: none;
        padding: 12px 22px;
        border-radius: 8px;
        font-size: 1.1em;
        font-weight: bold;
        cursor: pointer;
        transition: 0.3s;
    }

    .verify-button:hover {
        background-color: #00cc52;
    }

    .scripts-section {
        display: none;
        width: 90%;
        max-width: 640px;
        margin: 20px auto;
        animation: fadeIn 0.8s ease;
    }

    @keyframes fadeIn {
        from { opacity: 0; }
        to { opacity: 1; }
    }

    .script-item {
        background-color: #1b1b1b;
        border: 2px solid #ff4040;
        border-radius: 15px;
        padding: 15px;
        margin-bottom: 20px;
        box-shadow: 0 2px 10px rgba(0,0,0,0.5);
    }

    .script-title {
        color: #ff4040;
        font-size: 1.4em;
        margin-bottom: 6px;
    }

    .script-desc {
        color: #bbb;
        font-size: 1em;
        margin-bottom: 10px;
    }

    textarea {
        background-color: #252525;
        border: 1px solid #ff4040;
        color: #fff;
        width: 100%;
        height: 80px;
        border-radius: 8px;
        padding: 10px;
        resize: none;
    }

    .copy-button {
        background-color: #ff4040;
        color: #fff;
        border: none;
        padding: 8px 15px;
        border-radius: 8px;
        cursor: pointer;
        transition: 0.3s;
    }

    .copy-button:hover {
        background-color: #cc0000;
    }

    footer {
        color: #777;
        font-size: 0.9em;
        margin: 30px 0 10px;
    }

    footer a {
        color: #ff4040;
        text-decoration: none;
        margin: 0 10px;
    }

    footer a:hover {
        text-decoration: underline;
    }
</style>
</head>
<body>
    <div class="header">
        <h1 class="title">FIERLESS Hub</h1>
        <p class="subtitle">Premium Roblox Scripts & Utilities</p>
    </div>

    <div class="verification-box" id="verifyBox">
        <h2 class="verify-title">Human Verification</h2>
        <p class="verify-text">Prove you’re not a bot! Solve the math question and emoji challenge.</p>
        <p id="captcha-question"></p>
        <input type="text" id="captcha-input" placeholder="Enter number here">

        <p id="emoji-question"></p>
        <input type="text" id="emoji-input" placeholder="Enter emoji name (e.g. star, heart)">
        <br>

        <button class="verify-button" onclick="verifyUser()">VERIFY USER</button>
        <p id="error-message" style="color:#ff4040;display:none;margin-top:8px;">❌ Incorrect — try again!</p>
    </div>

    <div class="scripts-section" id="scripts">
        <div class="script-item">
            <h3 class="script-title">Claim UGC = 222 Kills</h3>
            <p class="script-desc">Instant UGC, Bypass Anti-Cheat +More</p>
            <textarea id="script7">loadstring(game:HttpGet("https://pastebin.com/raw/80Wzk9vf"))()</textarea>
            <button class="copy-button" onclick="copyScript('script7')">Copy Script</button>
        </div>

        <div class="script-item">
            <h3 class="script-title">Zombie Invasion</h3>
            <p class="script-desc">Kill Aura, ESP, Instant Proximity Point, Anti-AFK +More</p>
            <textarea id="script1">loadstring(game:HttpGet("https://pastefy.app/mV6UKZlO/raw"))()</textarea>
            <button class="copy-button" onclick="copyScript('script1')">Copy Script</button>
        </div>

        <div class="script-item">
            <h3 class="script-title">UGC Steal Points</h3>
            <p class="script-desc">Invis Kill Aura, Spin Kill, Hitbox Expander</p>
            <textarea id="script2">loadstring(game:HttpGet("https://pastefy.app/x5qMjfoJ/raw"))()</textarea>
            <button class="copy-button" onclick="copyScript('script2')">Copy Script</button>
        </div>

        <div class="script-item">
            <h3 class="script-title">Obby AFK or Play</h3>
            <p class="script-desc">Auto Checkpoint, ESP, Auto Ads +More</p>
            <textarea id="script3">loadstring(game:HttpGet("https://pastebin.com/raw/XhB8Fs56"))()</textarea>
            <button class="copy-button" onclick="copyScript('script3')">Copy Script</button>
        </div>

        <div class="script-item">
            <h3 class="script-title">Aimbot Universal</h3>
            <p class="script-desc">Universal aimbot for Roblox games</p>
            <textarea id="script4">loadstring(game:HttpGet("https://pastefy.app/sGkkduky/raw"))()</textarea>
            <button class="copy-button" onclick="copyScript('script4')">Copy Script</button>
        </div>

        <div class="script-item">
            <h3 class="script-title">Hitbox Expander Universal</h3>
            <p class="script-desc">Expands hitboxes universally</p>
            <textarea id="script5">loadstring(game:HttpGet("https://pastefy.app/hcfMqbE8/raw"))()</textarea>
            <button class="copy-button" onclick="copyScript('script5')">Copy Script</button>
        </div>

        <div class="script-item">
            <h3 class="script-title">Universal Bypass Anti-Cheat</h3>
            <p class="script-desc">Bypasses Roblox anticheat systems</p>
            <textarea id="script6">loadstring(game:HttpGet("https://pastefy.app/tFfdliPb/raw"))()</textarea>
            <button class="copy-button" onclick="copyScript('script6')">Copy Script</button>
        </div>
    </div>

    <footer>
        FIERLESS Hub © 2025 | Educational Use Only<br>
        <a href="https://www.youtube.com/@fierless" target="_blank">YouTube: @fierless</a>
    </footer>

<script>
    const emojis = ["⭐", "❤️", "🔥", "💧", "⚡"];
    const emojiNames = ["star", "heart", "fire", "water", "lightning"];
    let num1 = Math.floor(Math.random() * 10) + 1;
    let num2 = Math.floor(Math.random() * 10) + 1;
    let answer = num1 + num2;
    let emojiIndex = Math.floor(Math.random() * emojis.length);

    document.getElementById('captcha-question').innerText = `What is ${num1} + ${num2}?`;
    document.getElementById('emoji-question').innerText = `Type the name of this emoji: ${emojis[emojiIndex]}`;

    function verifyUser() {
        let userAnswer = parseInt(document.getElementById('captcha-input').value);
        let emojiAnswer = document.getElementById('emoji-input').value.trim().toLowerCase();
        if (userAnswer === answer && emojiAnswer === emojiNames[emojiIndex]) {
            document.getElementById('verifyBox').style.display = 'none';
            document.getElementById('scripts').style.display = 'block';
        } else {
            document.getElementById('error-message').style.display = 'block';
        }
    }

    function copyScript(id) {
        let el = document.getElementById(id);
        el.select();
        document.execCommand("copy");
        alert("✅ Script copied to clipboard!");
    }
</script>
</body>
</html>
