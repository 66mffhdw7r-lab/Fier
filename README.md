# Exploits<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>FIERLESS Hub - Premium Roblox Scripts</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: linear-gradient(135deg, #0f172a 0%, #1e293b 50%, #0f172a 100%);
            color: #ffffff;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            position: relative;
            overflow-x: hidden;
        }

        /* Animated background effects */
        body::before {
            content: '';
            position: fixed;
            width: 100%;
            height: 100%;
            background-image: 
                radial-gradient(circle at 15% 30%, rgba(239, 68, 68, 0.08) 0%, transparent 50%),
                radial-gradient(circle at 85% 70%, rgba(59, 130, 246, 0.08) 0%, transparent 50%),
                radial-gradient(circle at 50% 50%, rgba(168, 85, 247, 0.05) 0%, transparent 60%);
            animation: pulse 10s ease-in-out infinite;
            pointer-events: none;
            z-index: 0;
        }

        @keyframes pulse {
            0%, 100% { opacity: 0.4; }
            50% { opacity: 0.7; }
        }

        .container {
            position: relative;
            z-index: 1;
            width: 100%;
            max-width: 1400px;
            margin: 0 auto;
            padding: 20px;
            display: flex;
            flex-direction: column;
            align-items: center;
            flex: 1;
        }

        /* Header Styles */
        .header {
            text-align: center;
            margin: 50px 0 40px;
            animation: slideDown 0.7s ease;
        }

        @keyframes slideDown {
            from {
                opacity: 0;
                transform: translateY(-40px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .logo {
            font-size: 4em;
            font-weight: 900;
            background: linear-gradient(135deg, #ef4444, #f97316, #ef4444);
            background-size: 200% auto;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: gradientShift 3s ease infinite;
            letter-spacing: 4px;
            margin-bottom: 15px;
            filter: drop-shadow(0 0 30px rgba(239, 68, 68, 0.4));
        }

        @keyframes gradientShift {
            0%, 100% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
        }

        .tagline {
            font-size: 1.4em;
            color: #cbd5e1;
            font-weight: 500;
            letter-spacing: 1px;
        }

        /* Verification Container */
        .verification-container {
            background: linear-gradient(145deg, rgba(30, 41, 59, 0.95), rgba(15, 23, 42, 0.95));
            backdrop-filter: blur(20px);
            border: 2px solid rgba(239, 68, 68, 0.3);
            border-radius: 24px;
            padding: 45px;
            max-width: 550px;
            width: 100%;
            box-shadow: 
                0 25px 70px rgba(0, 0, 0, 0.6),
                0 0 0 1px rgba(255, 255, 255, 0.05) inset;
            animation: scaleIn 0.6s ease;
            margin-bottom: 40px;
        }

        @keyframes scaleIn {
            from {
                opacity: 0;
                transform: scale(0.92);
            }
            to {
                opacity: 1;
                transform: scale(1);
            }
        }

        .verify-header {
            text-align: center;
            margin-bottom: 35px;
        }

        .verify-header h2 {
            font-size: 2.2em;
            background: linear-gradient(135deg, #ef4444, #f97316);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 12px;
            font-weight: 800;
        }

        .verify-header p {
            color: #94a3b8;
            font-size: 1.05em;
            line-height: 1.5;
        }

        /* Robot Captcha */
        .robot-captcha {
            background: linear-gradient(145deg, rgba(15, 23, 42, 0.9), rgba(30, 41, 59, 0.7));
            border: 2px solid rgba(100, 116, 139, 0.4);
            border-radius: 14px;
            padding: 22px;
            margin-bottom: 28px;
            display: flex;
            align-items: center;
            gap: 18px;
            cursor: pointer;
            transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
        }

        .robot-captcha:hover {
            border-color: #ef4444;
            transform: translateY(-3px);
            box-shadow: 0 10px 30px rgba(239, 68, 68, 0.2);
        }

        .captcha-checkbox {
            width: 32px;
            height: 32px;
            border: 3px solid #64748b;
            border-radius: 8px;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
            flex-shrink: 0;
        }

        .captcha-checkbox.checked {
            background: linear-gradient(135deg, #10b981, #059669);
            border-color: #10b981;
            animation: checkPop 0.4s ease;
        }

        @keyframes checkPop {
            0% { transform: scale(1); }
            50% { transform: scale(1.15); }
            100% { transform: scale(1); }
        }

        .captcha-checkbox.checked::after {
            content: '✓';
            color: white;
            font-size: 22px;
            font-weight: bold;
        }

        .captcha-label {
            color: #e2e8f0;
            font-size: 1.15em;
            font-weight: 500;
            user-select: none;
        }

        /* Math Captcha */
        .math-captcha {
            background: linear-gradient(145deg, rgba(15, 23, 42, 0.9), rgba(30, 41, 59, 0.7));
            border: 2px solid rgba(100, 116, 139, 0.4);
            border-radius: 14px;
            padding: 25px;
            margin-bottom: 28px;
        }

        .captcha-question {
            color: #f1f5f9;
            font-size: 1.3em;
            margin-bottom: 18px;
            text-align: center;
            font-weight: 700;
            letter-spacing: 0.5px;
        }

        .captcha-input {
            width: 100%;
            background: rgba(15, 23, 42, 0.9);
            border: 2px solid rgba(100, 116, 139, 0.5);
            border-radius: 12px;
            padding: 16px;
            color: #ffffff;
            font-size: 1.2em;
            text-align: center;
            transition: all 0.3s ease;
            font-weight: 600;
        }

        .captcha-input:focus {
            outline: none;
            border-color: #ef4444;
            box-shadow: 0 0 25px rgba(239, 68, 68, 0.3);
            background: rgba(15, 23, 42, 1);
        }

        .error-message {
            color: #fca5a5;
            text-align: center;
            margin-top: 15px;
            font-weight: 600;
            display: none;
            animation: shake 0.5s ease;
            font-size: 1.05em;
        }

        @keyframes shake {
            0%, 100% { transform: translateX(0); }
            25% { transform: translateX(-12px); }
            75% { transform: translateX(12px); }
        }

        .verify-button {
            width: 100%;
            background: linear-gradient(135deg, #10b981, #059669);
            border: none;
            border-radius: 14px;
            padding: 20px;
            color: #ffffff;
            font-size: 1.35em;
            font-weight: 800;
            cursor: pointer;
            transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
            text-transform: uppercase;
            letter-spacing: 2px;
            box-shadow: 0 12px 35px rgba(16, 185, 129, 0.4);
        }

        .verify-button:hover:not(:disabled) {
            transform: translateY(-4px);
            box-shadow: 0 18px 45px rgba(16, 185, 129, 0.5);
            background: linear-gradient(135deg, #059669, #047857);
        }

        .verify-button:active:not(:disabled) {
            transform: translateY(-2px);
        }

        .verify-button:disabled {
            background: linear-gradient(135deg, #475569, #334155);
            cursor: not-allowed;
            box-shadow: none;
            opacity: 0.6;
        }

        /* Scripts Section */
        .scripts-section {
            display: none;
            width: 100%;
            animation: fadeInUp 0.9s ease;
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(40px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .scripts-header {
            text-align: center;
            margin-bottom: 40px;
        }

        .scripts-header h2 {
            font-size: 2.5em;
            background: linear-gradient(135deg, #ef4444, #f97316);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            font-weight: 800;
            margin-bottom: 10px;
        }

        .scripts-header p {
            color: #94a3b8;
            font-size: 1.1em;
        }

        .scripts-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(380px, 1fr));
            gap: 28px;
            margin-bottom: 50px;
        }

        .script-card {
            background: linear-gradient(145deg, rgba(30, 41, 59, 0.95), rgba(15, 23, 42, 0.9));
            backdrop-filter: blur(10px);
            border: 2px solid rgba(239, 68, 68, 0.25);
            border-radius: 18px;
            padding: 28px;
            transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
            box-shadow: 0 12px 35px rgba(0, 0, 0, 0.4);
            position: relative;
            overflow: hidden;
        }

        .script-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 4px;
            background: linear-gradient(90deg, #ef4444, #f97316);
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .script-card:hover {
            transform: translateY(-6px);
            border-color: #ef4444;
            box-shadow: 0 18px 50px rgba(239, 68, 68, 0.35);
        }

        .script-card:hover::before {
            opacity: 1;
        }

        .script-title {
            font-size: 1.5em;
            background: linear-gradient(135deg, #ef4444, #f97316);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 14px;
            font-weight: 800;
            letter-spacing: 0.5px;
        }

        .script-desc {
            color: #cbd5e1;
            margin-bottom: 18px;
            line-height: 1.7;
            font-size: 1.02em;
        }

        .script-code {
            background: rgba(15, 23, 42, 0.95);
            border: 1px solid rgba(100, 116, 139, 0.4);
            border-radius: 12px;
            padding: 16px;
            color: #10b981;
            font-family: 'Courier New', 'Consolas', monospace;
            font-size: 0.92em;
            resize: none;
            width: 100%;
            height: 85px;
            margin-bottom: 14px;
            transition: all 0.3s ease;
        }

        .script-code:focus {
            outline: none;
            border-color: #ef4444;
            box-shadow: 0 0 20px rgba(239, 68, 68, 0.2);
        }

        .copy-btn {
            width: 100%;
            background: linear-gradient(135deg, #ef4444, #dc2626);
            border: none;
            border-radius: 12px;
            padding: 14px;
            color: #ffffff;
            font-weight: 700;
            cursor: pointer;
            transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
            text-transform: uppercase;
            letter-spacing: 1px;
            font-size: 1.05em;
            box-shadow: 0 8px 25px rgba(239, 68, 68, 0.3);
        }

        .copy-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 12px 35px rgba(239, 68, 68, 0.45);
            background: linear-gradient(135deg, #dc2626, #b91c1c);
        }

        .copy-btn:active {
            transform: translateY(-1px);
        }

        /* Footer */
        .footer {
            background: linear-gradient(180deg, rgba(15, 23, 42, 0) 0%, rgba(15, 23, 42, 0.95) 50%);
            backdrop-filter: blur(10px);
            border-top: 2px solid rgba(239, 68, 68, 0.25);
            padding: 40px 20px;
            text-align: center;
            color: #94a3b8;
            margin-top: auto;
            width: 100%;
        }

        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
        }

        .footer-content p {
            margin-bottom: 10px;
            line-height: 1.6;
        }

        .footer-content strong {
            color: #ef4444;
            font-weight: 700;
        }

        .footer-links {
            margin-top: 20px;
            display: flex;
            justify-content: center;
            gap: 30px;
            flex-wrap: wrap;
        }

        .footer-links a {
            color: #ef4444;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
            font-size: 1.05em;
        }

        .footer-links a:hover {
            color: #f97316;
            transform: translateY(-2px);
            text-shadow: 0 0 15px rgba(239, 68, 68, 0.5);
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .logo {
                font-size: 3em;
                letter-spacing: 2px;
            }

            .tagline {
                font-size: 1.1em;
            }

            .verification-container {
                padding: 30px 25px;
            }

            .scripts-grid {
                grid-template-columns: 1fr;
            }

            .footer-links {
                flex-direction: column;
                gap: 15px;
            }
        }

        @media (max-width: 480px) {
            .logo {
                font-size: 2.2em;
            }

            .verify-header h2 {
                font-size: 1.8em;
            }

            .verification-container {
                padding: 25px 20px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1 class="logo">FIERLESS HUB</h1>
            <p class="tagline">Premium Roblox Scripts & Utilities</p>
        </div>

        <div class="verification-container" id="verificationBox">
            <div class="verify-header">
                <h2>🔒 Access Verification</h2>
                <p>Complete both verifications to unlock premium scripts</p>
            </div>

            <!-- I'm Not a Robot Captcha -->
            <div class="robot-captcha" id="robotCaptcha">
                <div class="captcha-checkbox" id="captchaCheckbox"></div>
                <span class="captcha-label">I'm not a robot</span>
            </div>

            <!-- Math Captcha -->
            <div class="math-captcha">
                <p class="captcha-question" id="mathQuestion"></p>
                <input type="text" class="captcha-input" id="mathInput" placeholder="Enter your answer" autocomplete="off">
                <p class="error-message" id="errorMsg">❌ Incorrect answer. Please try again!</p>
            </div>

            <button class="verify-button" id="verifyBtn" disabled>Verify Access</button>
        </div>

        <div class="scripts-section" id="scriptsSection">
            <div class="scripts-header">
                <h2>🎮 Premium Scripts</h2>
                <p>Copy and execute in your Roblox executor</p>
            </div>

            <div class="scripts-grid">
                <div class="script-card">
                    <h3 class="script-title">⚡ Instant UGC Bypass</h3>
                    <p class="script-desc">Full anti-cheat bypass with instant UGC features, complete script with everything included</p>
                    <textarea class="script-code" readonly>loadstring(game:HttpGet("https://pastebin.com/80Wzk9vf"))()</textarea>
                    <button class="copy-btn" onclick="copyScript(this)">Copy Script</button>
                </div>

                <div class="script-card">
                    <h3 class="script-title">🧟 Zombie Invasion Script</h3>
                    <p class="script-desc">Zombie Kill aura, ESP, Instant proximity points, Anti-AFK & more powerful features</p>
                    <textarea class="script-code" readonly>loadstring(game:HttpGet("https://pastefy.app/mV6UKZlO/raw"))()</textarea>
                    <button class="copy-btn" onclick="copyScript(this)">Copy Script</button>
                </div>

                <div class="script-card">
                    <h3 class="script-title">💎 UGC Steal Points Script</h3>
                    <p class="script-desc">Invisible Kill aura, Spin kill, Advanced hitbox expander for maximum efficiency</p>
                    <textarea class="script-code" readonly>loadstring(game:HttpGet("https://pastefy.app/x5qMjfoJ/raw"))()</textarea>
                    <button class="copy-btn" onclick="copyScript(this)">Copy Script</button>
                </div>

                <div class="script-card">
                    <h3 class="script-title">🏃 Obby AFK or Play Script</h3>
                    <p class="script-desc">Auto Checkpoint, ESP, Auto ads, Speed boost & comprehensive obby automation</p>
                    <textarea class="script-code" readonly>loadstring(game:HttpGet("https://pastebin.com/raw/XhB8Fs56"))()</textarea>
                    <button class="copy-btn" onclick="copyScript(this)">Copy Script</button>
                </div>

                <div class="script-card">
                    <h3 class="script-title">🎯 Aimbot Universal</h3>
                    <p class="script-desc">Universal aimbot for all Roblox shooting games with precision targeting</p>
                    <textarea class="script-code" readonly>loadstring(game:HttpGet("https://pastefy.app/sGkkduky/raw"))()</textarea>
                    <button class="copy-btn" onclick="copyScript(this)">Copy Script</button>
                </div>

                <div class="script-card">
                    <h3 class="script-title">📦 Hitbox Expander Universal</h3>
                    <p class="script-desc">Expands hitboxes universally for easier targeting and improved accuracy</p>
                    <textarea class="script-code" readonly>loadstring(game:HttpGet("https://pastefy.app/hcfMqbE8/raw"))()</textarea>
                    <button class="copy-btn" onclick="copyScript(this)">Copy Script</button>
                </div>

                <div class="script-card">
                    <h3 class="script-title">🛡️ Universal Anti-Cheat Bypass</h3>
                    <p class="script-desc">Bypasses anti-cheat detections universally across multiple Roblox games</p>
                    <textarea class="script-code" readonly>loadstring(game:HttpGet("https://pastefy.app/tFfdliPb/raw"))()</textarea>
                    <button class="copy-btn" onclick="copyScript(this)">Copy Script</button>
                </div>
            </div>
        </div>
    </div>

    <div class="footer">
        <div class="footer-content">
            <p><strong>FIERLESS Hub</strong> © 2025 | Premium Roblox Scripts & Utilities</p>
            <p style="margin-top: 8px; font-size: 0.95em;">For Educational Purposes Only. All scripts are property of their respective owners.</p>
            <div class="footer-links">
                <a href="https://www.youtube.com/@Fierless" target="_blank">📺 YouTube: Fierless</a>
                <a href="https://www.roblox.com/users/profile?username=WHOMPWHOMPMANCRY" target="_blank">🎮 Roblox: WHOMPWHOMPMANCRY</a>
            </div>
        </div>
    </div>

    <script>
        // State management
        let robotVerified = false;
        let mathAnswer = 0;

        // Initialize captchas
        function initCaptchas() {
            // Generate random math problem with varied difficulty
            const operations = [
                { a: Math.floor(Math.random() * 20) + 5, b: Math.floor(Math.random() * 15) + 3, op: '+' },
                { a: Math.floor(Math.random() * 15) + 15, b: Math.floor(Math.random() * 10) + 2, op: '-' },
                { a: Math.floor(Math.random() * 10) + 3, b: Math.floor(Math.random() * 9) + 2, op: '×' }
            ];
            
            const selected = operations[Math.floor(Math.random() * operations.length)];
            
            if (selected.op === '+') {
                mathAnswer = selected.a + selected.b;
            } else if (selected.op === '-') {
                mathAnswer = selected.a - selected.b;
            } else {
                mathAnswer = selected.a * selected.b;
            }
            
            document.getElementById('mathQuestion').textContent = `🧮 What is ${selected.a} ${selected.op} ${selected.b}?`;
        }

        // Robot captcha handler
        document.getElementById('robotCaptcha').addEventListener('click', function() {
            if (!robotVerified) {
                document.getElementById('captchaCheckbox').classList.add('checked');
                robotVerified = true;
                checkVerificationComplete();
            }
        });

        // Math input handler
        document.getElementById('mathInput').addEventListener('input', function() {
            document.getElementById('errorMsg').style.display = 'none';
            checkVerificationComplete();
        });

        // Allow Enter key to submit
        document.getElementById('mathInput').addEventListener('keypress', function(e) {
            if (e.key === 'Enter' && !document.getElementById('verifyBtn').disabled) {
                document.getElementById('verifyBtn').click();
            }
        });

        // Check if both verifications are complete
        function checkVerificationComplete() {
            const mathInput = document.getElementById('mathInput').value.trim();
            const verifyBtn = document.getElementById('verifyBtn');
            
            if (robotVerified && mathInput !== '') {
                verifyBtn.disabled = false;
            } else {
                verifyBtn.disabled = true;
            }
        }

        // Verify button handler
        document.getElementById('verifyBtn').addEventListener('click', function() {
            const userAnswer = parseInt(document.getElementById('mathInput').value);
            
            if (userAnswer === mathAnswer && robotVerified) {
                // Success animation
                document.getElementById('verificationBox').style.transition = 'all 0.5s ease';
                document.getElementById('verificationBox').style.opacity = '0';
                document.getElementById('verificationBox').style.transform = 'scale(0.95)';
                
                setTimeout(() => {
                    document.getElementById('verificationBox').style.display = 'none';
                    document.getElementById('scriptsSection').style.display = 'block';
                }, 500);
            } else {
                document.getElementById('errorMsg').style.display = 'block';
                document.getElementById('mathInput').value = '';
                document.getElementById('mathInput').focus();
                
                // Shake animation on error
                const input = document.getElementById('mathInput');
                input.style.animation = 'none';
                setTimeout(() => {
                    input.style.animation = 'shake 0.5s ease';
                }, 10);
            }
        });

        // Copy script function with modern clipboard API
        function copyScript(button) {
            const textarea = button.previousElementSibling;
            const text = textarea.value;
            
            // Modern clipboard API
            if (navigator.clipboard && navigator.clipboard.writeText) {
                navigator.clipboard.writeText(text).then(() => {
                    showCopySuccess(button);
                }).catch(() => {
                    fallbackCopy(textarea, button);
                });
            } else {
                fallbackCopy(textarea, button);
            }
        }

        // Fallback copy method
        function fallbackCopy(textarea, button) {
            textarea.select();
            textarea.setSelectionRange(0, 99999);
            
            try {
                document.execCommand('copy');
                showCopySuccess(button);
            } catch (err) {
                alert('Failed to copy. Please copy manually.');
            }
            
            window.getSelection().removeAllRanges();
        }

        // Show copy success feedback
        function showCopySuccess(button) {
            const originalText = button.textContent;
            button.textContent = '✓ Copied!';
            button.style.background = 'linear-gradient(135deg, #10b981, #059669)';
            button.style.transform = 'scale(1.05)';
            
            setTimeout(() => {
                button.textContent = originalText;
                button.style.background = '';
                button.style.transform = '';
            }, 2000);
        }

        // Initialize on load
        window.addEventListener('load', function() {
            initCaptchas();
            document.getElementById('mathInput').focus();
        });
    </script>
</body>
</html>
