# CVE-2025-63892
👤 Discoverer

Minhajul Taivin (Offensive Security Researcher @ Red Team Bangladesh)
https://www.linkedin.com/in/minhajultaivin

🚨 Security Advisory: Stored XSS Vulnerability in Student Grades Management System  
# CVE ID: CVE-2025-63892  
Severity: High  
Weakness: CWE-79 — Cross-Site Scripting (Stored)

# 📝 Summary  
A *stored Cross-Site Scripting (XSS)* vulnerability was identified in the *Classroom module* of *SourceCodester Student Grades Management System v1.0*.  
The application fails to sanitize user-supplied HTML inputs in the *Description* field when creating a classroom.  
Malicious JavaScript is executed whenever an administrator or teacher views the affected classroom page.

# 🎯 Affected Component  
`/classroom.php` — Classroom Description Field

# 🧪 Proof of Concept  
A teacher-level attacker can inject a payload such as: `<><img src=1 onerror=alert(1)>`
This payload executes automatically when the classroom page is viewed.

⚡ Impact

• Arbitrary JavaScript Execution

• Session Hijacking / Account Takeover

• User Impersonation

• Potential Remote Code Execution via Browser Exploitation

• Phishing & Credential Theft

🔧 Remediation

• Implement strict input sanitization on HTML fields

• Apply output encoding before rendering user data

• Enforce a Content Security Policy (CSP)

• Validate rich-text fields against XSS-safe libraries



📦 Affected Product

SourceCodester Student Grades Management System v1.0

