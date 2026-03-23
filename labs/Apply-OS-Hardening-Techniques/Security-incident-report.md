# Security Incident Report

## Section 1: Identify the network protocol involved in the incident
The primary network protocol involved in the incident is HTTP. The browser uses HTTP to request the webpage and download the malicious file. DNS is also involved in resolving the domain names yummyrecipesforme.com and greatrecipesforme.com to their respective IP addresses before the HTTP requests are made. Both of these protocols operate at the TCP/IP application layer.

## Section 2: Document the incident
The incident was discovered after multiple customers reported issues while using the website yummyrecipesforme.com. They noticed that the website automatically downloaded a file, redirected them to a different website, and caused their computers to run slower.

After conducting an investigation, it became apparent that a former employee performed a brute force attack to gain access to the web host. The admin panel was protected with a default password, which made it easy to bypass. After security was notified of the issue, a testing environment was created to observe the behavior of yummyrecipesforme.com.

During the DNS query, the website prompted a download of a malware file. After the file was executed, the browser was redirected to greatrecipesforme.com through another DNS query. The browser then initiated an HTTP request to the IP address for greatrecipesforme.com.

Further analysis showed that malicious JavaScript code had been added to the website’s source code. This code prompted users to download an executable file. The downloaded file contained a script that redirected users from yummyrecipesforme.com to greatrecipesforme.com.

## Section 3: Recommend one remediation for brute force attacks
My recommendation for mitigation is to implement stronger passwords for the admin panel, while also limiting the number of login attempts, requiring frequent password changes, and not allowing previous passwords to be reused.

Additional security controls should include enforcing the principle of least privilege and establishing guidelines for offboarding employees. There should also be a team monitoring login attempts and other related logs, along with implementing a SIEM solution.