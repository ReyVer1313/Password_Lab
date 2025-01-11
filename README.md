# Password Cracking Lab

This project documents the outcomes of a password cracking lab, including the use of LAN Manager settings and John the Ripper for password attacks. The lab demonstrates various password cracking techniques and their effectiveness under different configurations.

### Objectives
- Understand the role of LAN Manager policies in password security.
- Utilize John the Ripper for basic, hybrid, and full password attacks.
- Evaluate the effectiveness of password cracking techniques under various scenarios.

### Key Results

1. **LAN Manager Settings**:
   - LAN Manager authentication level was modified to enhance password security by refusing LM responses and using NTLMv2 responses only.

2. **John the Ripper Options**:
   - **Dictionary Attack**: To use a dictionary file (word list), the following option was used:  
     `--wordlist=FILE --stdin`
   - **Resuming an Interrupted Session**: The following option was used to restore a session:  
     `--restore[=NAME]`

3. **Password Attack Simulations**:
   - **Basic Password Attack**: Performed to retrieve weak passwords using default settings.  
     *Results to be analyzed from the captured output.*
   - **Hybrid Password Attack**: Combined a dictionary attack with brute force to generate permutations.  
     *Results to be analyzed from the captured output.*
   - **Full Password Attack**: Employed brute force to attempt all possible password combinations.  
     *Results to be analyzed from the captured output.*

### Tools Used
- **LAN Manager**: Configured for enhanced security settings to test password cracking resistance.
- **John the Ripper**: Used to simulate and execute password attacks.
- **Dictionary Files**: Provided word lists for dictionary-based attacks.

### Recommendations
- Implement policies to disable LAN Manager hashes and enforce NTLMv2 responses only.
- Enforce strong password policies, including complexity and length requirements, to reduce the effectiveness of password cracking.
- Regularly audit systems for weak passwords and ensure all accounts comply with organizational security standards.

### Project Resources
- **Project Link**: [Password Cracking Lab Results](https://github.com/StephVergil/Password_Lab/blob/main/PasswordLabResults-1.docx.pdf)
- [John the Ripper Documentation](https://www.openwall.com/john/)

### Conclusion
This lab highlights the importance of secure password practices and the need for robust system configurations to resist password attacks. By understanding and mitigating weaknesses, organizations can significantly improve their overall security posture.

### Disclaimer
This project was conducted in a controlled environment. Unauthorized use of these techniques or tools outside such an environment may violate ethical guidelines and legal regulations.
