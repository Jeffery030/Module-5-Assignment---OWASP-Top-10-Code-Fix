### **Broken Access Control**
 
1. **Issue**: The supply of the user ID in the URL allows anyone to access any profile without checks.

   **Fixed**: Authenticated requests ensure users can only access their own data unless they're admins.

 
2. **Issue**: Similar problem with user ID directly from the URL exposing private information.

 
   **Fixed**: Implemented checks to ensure users can only access their own data.
 

3. **Issue**: MD5 is broken, unsalted, and too fast for secure password hashing.

   **Fixed**: Used BCrypt to hash passwords with a salt to enhance security.

4. **Issue**: SHA-1 is broken and fast, exposing passwords to brute force attacks.

   **Fixed**: Used bcrypt for better password handling.
  
### **Injection**
 
5. **Issue**: Direct concatenation of user input leads to SQL injection.

   **Fixed**: Switched to parameterized queries to prevent SQL injection attacks.



6. Send the key problems associated with how drivers can theoretically be exploited by an attacker. Bypassing injection operations to JSON could lead to security vulnerabilities or data disclosure. To address this, we verified and reinforced the requirements from users to ensure that input is sanitized and safe patterns are matched.

 
7. In this scenario, there is no authorization or verification for input. Anyone who knows an email address can reset anyone's password. To prevent this, we implemented a system where users can request a single-use password reset code. This code is hashed and sent via email. Once the user clicks the link to reset their password, they can create a new password that the server verifies. After a successful reset, the code is deleted.
 
2. Verify the token on the reset endpoint, then:

8. A third-party script can compromise the integrity of this code by running JavaScript in the browser. If the content delivery network (CDN) is compromised, your site is vulnerable. To mitigate this risk, consider implementing strict source verification and enforcing Subresource Integrity (SRI) to confirm that packages are valid.
 

9. In this code, there is unrestricted user input from the URL, allowing requests to internal APIs and host addresses, which can be easily exploited by attackers. To combat this, implement a whitelist of allowed user domains and validate URLs. Additionally, limit the IP addresses that can be accessed.
 

 
**Identification and Authentication Failures**
 
10. One issue here is the insecure handling of passwords, as anyone can view the code and see the passwords, which makes them vulnerable. Passwords should be hashed using secure algorithms instead of being stored in plain text. It's also important to verify user access securely.

Implement a proper hashing mechanism for storing passwords and ensure that the user’s input is securely verified against the hashed password.


