- Part A — the HTTP capture (U1-03a_http_login.pcap)

- Find the login submission. What username and password were sent? Paste the line from the stream where you found them.
  
  username=anna.virtanen&password=Summer2026!&remember=on

- The login form was submitted using which HTTP method — GET or POST? (Look at the packet that carries the credentials.)
  
   GET /dashboard HTTP/1.1
Host: lab-portal.local
User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:128.0) Gecko/20100101 Firefox/128.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Cookie: SESSIONID=a3f9c2e7b81d4f60a5e2c9d10f4b7e88
Connection: keep-alive

- After a successful login, the server sends back a Set-Cookie header. What is the value of the SESSIONID cookie? Why might an attacker who sees this cookie be dangerous, even without the password?

    Set-Cookie: SESSIONID=a3f9c2e7b81d4f60a5e2c9d10f4b7e88; Path=/; HttpOnly
Location: /dashboard
Content-Length: 0
Connection: keep-alive

- The dashboard page (the final server response) reveals personal details about the user. List two pieces of sensitive information visible there.
  
   Full name : Anna Virtanen and email address and password also : anna.virtanen@pohjola-logistics.local / Summer2026!&remember=on
  
- Apply the filter tls. Can you find the username and password anywhere in this capture? Why or why not?

    No the date is encrypted. Example of encrypted TLS stream :
  ....N...J......l%..k=.P...@....'..e..
........./.0.................lab-portal.local
....*...&......!}
3..(.:..)......G.....T.<.../.....K...G..D..A0..=0..%.......w.M...sj.......(!a

-  Look at the first TLS packet (the "Client Hello"). One piece of plaintext is still visible here: the name of the server the client is connecting to. What is it? (Hint: look for "Server Name" / SNI in the packet details.)

 lab-portal.local

- Even though the contents are encrypted, name one thing an eavesdropper can still learn from the HTTPS capture (think about addresses, timing, or sizes).

  IP addresses of client and server Timing of packets Size of packets Hostname via SNI

- In one sentence: why does the protocol choice (HTTP vs HTTPS) matter for confidentiality?

  Because HTTP sends data in plaintext, while HTTPS encrypts all content and protects sensitive information.

- Name one situation in your daily life where you might be sending traffic over an untrusted network (e.g. public Wi-Fi). What protects you, and what would still be exposed?

  Example: Using public Wi-Fi Protected: Content of communication (via HTTPS encryption) Exposed: IP addresses, timing, packet sizes, hostname (SNI)
  
- What surprised me most The biggest surprise was how HTTP exposes everything
 even the password — in readable text, while HTTPS hides
all content in encrypted data. It was also surprising that the server name (SNI) is still visible in TLS.
