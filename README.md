🔥 Impact
Remote command execution could allow an attacker to:

Read sensitive files

Gain shell access

Escalate privileges

🛡️ Mitigation
Avoid using system(), exec(), or shell_exec() with user input.

Use whitelist validation.

Escape user inputs if necessary.

Use safe libraries like subprocess.run() with shell=False.

