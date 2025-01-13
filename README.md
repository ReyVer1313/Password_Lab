# Password Cracking Lab: Comprehensive Analysis and Insights

This project presents an in-depth exploration of password cracking techniques, focusing on the role of LAN Manager settings and the application of **John the Ripper** for various password attacks. Through simulations and analysis, the lab evaluates the effectiveness of different password cracking strategies under various configurations, offering insights into improving password security.

---

## Objectives

1. **LAN Manager Policies**: Understand and modify LAN Manager authentication settings to enhance password security.
2. **John the Ripper Usage**: Utilize this powerful password cracking tool for:
   - Basic attacks.
   - Hybrid attacks (combining dictionary and brute-force methods).
   - Full brute-force password attacks.
3. **Evaluate Password Security**: Assess the success rate of cracking attempts and their implications for system security.

---

## Key Findings

### 1. **LAN Manager Settings**
   - **Initial Configuration**: LAN Manager authentication settings were configured to allow LM hashes, making systems vulnerable to legacy password cracking techniques.
   - **Enhanced Configuration**:
     - Disabled LAN Manager hashes.
     - Enforced **NTLMv2 responses only**, strengthening password security.
   - **Observations**: Systems configured with legacy LM responses proved significantly more vulnerable to password cracking compared to those using NTLMv2.

---

### 2. **John the Ripper Techniques**
   - John the Ripper was employed to simulate various attack types. Below are the configurations and outcomes:

#### **2.1 Dictionary Attack**
   - **Purpose**: Quickly identify weak passwords using a precompiled list of common passwords (dictionary file).
   - **Command Used**:
     ```bash
     john --wordlist=<dictionary-file> --stdin <hash-file>
     ```
   - **Outcome**: Cracked weak and commonly used passwords almost instantly, highlighting the importance of avoiding predictable passwords.

#### **2.2 Hybrid Attack**
   - **Purpose**: Combine dictionary attacks with brute-force techniques to generate permutations (e.g., adding numbers or symbols).
   - **Command Used**:
     ```bash
     john --wordlist=<dictionary-file> --rules <hash-file>
     ```
   - **Outcome**: Cracked moderately complex passwords that included predictable patterns, such as "password123" or "welcome@2023".

#### **2.3 Full Brute-Force Attack**
   - **Purpose**: Attempt all possible combinations of characters for maximum coverage.
   - **Command Used**:
     ```bash
     john --incremental <hash-file>
     ```
   - **Outcome**:
     - Successfully cracked shorter passwords within a reasonable time frame.
     - Significantly more time-intensive for longer passwords, demonstrating the importance of password length in resisting brute-force attacks.

---

### 3. **Password Attack Simulations**
   - **Weak Passwords**: Cracked almost immediately with dictionary and hybrid attacks.
   - **Moderate Passwords**: Cracked using hybrid attacks within a reasonable time frame.
   - **Strong Passwords**:
     - Resisted dictionary and hybrid attacks.
     - Required extensive computational resources for brute-force cracking, often making it infeasible.

---

## Key Insights and Recommendations

### **Password Security Best Practices**
1. **Disable Legacy Protocols**:
   - Avoid using LAN Manager hashes due to their vulnerability.
   - Enforce NTLMv2-only authentication for better security.
   
2. **Adopt Strong Password Policies**:
   - Require passwords with a minimum length of 12–16 characters.
   - Enforce complexity by including upper- and lowercase letters, numbers, and special symbols.

3. **Implement Multi-Factor Authentication (MFA)**:
   - Adds an additional layer of security, making it significantly harder for attackers to compromise accounts even if passwords are cracked.

4. **Regular Audits**:
   - Use tools like John the Ripper to periodically test for weak passwords in controlled environments.
   - Ensure all accounts comply with organizational password standards.

5. **User Awareness and Training**:
   - Educate users on the risks of reusing passwords or choosing weak, predictable patterns.
   - Encourage the use of password managers for generating and storing complex passwords.

---

## Tools and Resources

### **Tools Used**
- **LAN Manager (LM)**:
  - Configured to demonstrate the vulnerabilities of legacy authentication protocols and the strength of NTLMv2.
- **John the Ripper**:
  - A powerful password cracking tool for testing and evaluating password security.
- **Dictionary Files**:
  - Custom and publicly available wordlists used for dictionary and hybrid attacks.

### **References**
- [John the Ripper Documentation](https://www.openwall.com/john/)
- [NTLM Overview](https://learn.microsoft.com/en-us/windows-server/security/kerberos/ntlm-overview)  
- [LAN Manager Authentication Level](https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-10/security/threat-protection/security-policy-settings/network-security-lan-manager-authentication-level)

---

## Practical Scenarios

- **Real-World Applications**:
  - Testing organizational systems for weak passwords.
  - Educating security teams on the vulnerabilities of legacy protocols and the effectiveness of strong passwords.
- **Advanced Configurations**:
  - Customizing John the Ripper rules for targeted password patterns.
  - Analyzing hash types to determine the appropriate cracking approach.

---

## Conclusion

This lab underscores the importance of adopting strong password policies and securing authentication protocols. By simulating attacks with tools like John the Ripper, organizations can identify vulnerabilities, educate users, and implement effective countermeasures to protect sensitive data.

### Key Takeaways:
- Legacy protocols like LAN Manager significantly weaken system security and must be replaced with modern standards.
- Weak passwords remain a critical vulnerability, easily exploited through dictionary and hybrid attacks.
- Strong, unique passwords, combined with MFA, greatly reduce the likelihood of compromise.

---

## Disclaimer

- **Controlled Environment**: 
  - All experiments were conducted in a secure, controlled setting to avoid unethical or unauthorized use.
- **Ethical and Legal Compliance**:
  - Unauthorized use of password cracking tools or techniques may breach ethical guidelines and legal regulations.

---

## Author

**Stephanie Vergil**  
For detailed results and additional resources, visit the [project repository](https://github.com/StephVergil/Password_Lab/blob/main/PasswordLabResults-1.docx.pdf).
