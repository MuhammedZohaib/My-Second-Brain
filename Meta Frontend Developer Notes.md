### How internet Works?
Internet works by creating wired or wireless connections between different computers forming a network. But the wired systems can be very complicated so we use **network switch** which connects multiple devices and then the network switch can connect with other network switches. After multiple switches connect to each other they form `interconnected network` , which is also known as internet.

Video services are provided by the computers on the network known as servers and our devices are known as clients

### What is a web server and how it works?
A web server is a computer which runs services ranging from websites to instant messaging. To provide efficient services there several data centers built around the world. Data center can vary depending on the service the provide. such as if they store images they might have a lot of hard drives or if the process data they might have high computational power.

### Web Server Purposes:
- Website Storage and Administration
- Data Storage
- Security
- Managing Emails
- Handle Requests

Website: Collection of Webpages
Webpage: composed of images, text and other components

All the tags in the HTML are known as Markup tags.

Each line of markup is processed in sequential order from first to last. This is known as page rendering.
Browser is an application which is used to explore world wide web.  Browser sends a request to a server and the server sends back the response. Address of website we visit is known as URL (Uniform resource locator). When a request is made to a server using a URL, browser and server communicate using a protocol known as HTTP (Hyper Text Transfer Protocol).

### Web Hosting:
We can launch our own websites using a web hosting. Web Hosting is a service in which we place our websites and files on hosting companies web server.

Types of Hosting:
- Shared Hosting: Cheapest, Share Resources of the Server, Slow Performance, Best for small Websites with small number of visitors.
- Virtual Private Hosting: Sites with great demand, Resources are dedicated for each account virtually, expensive
- Dedicated Hosting: A dedicated server is provided for your website, all hardware and CPU is dedicated to your website. 
- Cloud Hosting: Runs on different physical and virtual servers, no limitations of resources, high cost based on resources used.


In order to send IP packets to other computer we need computer Internet protocol address or IP address. Network are the lines through which these IP packets travel. 
There are two versions of IP address:

- IPv4 : 4 Octal separated by dots
- IPv6 : 8 groups of hexadecimal addresses

IP packets are also known as data grains it contains a header and a payload as data. Header include source and destination IP address along with some additional information. It also contain Transmission control protocol or `UserDatagram Protocol` .
TCP (solve damages package issue) is used when the data such as text or images are used to send in order like the data cannot be damaged. While the UDP (solves corrupt packet issue) is used to transfer data which can bear some damage such as audio, video calls.

Browser use HTTP protocol to communicate with the web hosts. It stands for Hyper Text Transfer Protocol. It allows us to transfer HTML, Images, Styles and other files. It is a request-response based protocol.
It consists of a method (GET / POST), path, versions and headers.
HTTP methods are actions that client needs. which include 
- GET (Retrieve From server)
- POST (send to server)
- PUT (Update data on server)
- DELETE (Remove data on the serve)

There are multiple versions of HTTP but versions 1.1 and 2.0 are mostly used.
HTTP response is similar to HTTP request it optionally contains a body. The HTTP header contains status codes which indicate the status of the action. It ranges from 100-599. while the status message is text representation of the status code. There are five groups of status codes:

- Informational (100-199)
- Successful (200-299)
- Redirection (300-399)
- Client Error (400-499)
- Server Error (500-599)

```
100 - continue
101 - swithcing protocols
200 - ok
201 - created
202 - accepted
204 - no content
301 - moved permanently
302 - found
400 - bad request
401 - unauthorized
403 - forbidden
404 - requested resources not found
405 - method not allowed
500 - internal server error
502 - Bad Gateway
503 - Service Unavailable
```


### Protocols:

#### Dynamic Host Configuration Protocol (DHCP):

As computer connects with each other via the IP address so the DHCP is responsible for assigning a computer an IP address. Computer communicate with DHCP server using UDP and responds with an IP address.

#### Domain Name System Protocol (DNS):
When we go to a website suppose `https://google.com` , the DNS is responsible for resolving this domain name and providing the right IP address of the google web server where the files are being hosted.

#### Internet Message Access Protocol (IMAP):
Downloading emails and messages and managing them is done by this protocol. It is used to receive emails.

#### Simple Mail Transfer Protocol (SMTP):
SMTP is used for sending mails.

#### Post Office Protocol (POP):
Old protocol used to download emails to an email client. The main difference between the POP and the IMAP is that it will delete the mails from server once it is downloaded by the client. Not commonly used but used for email automation.

#### File Transfer Protocol (FTP):
When running applications and websites on the internet we need a way to transfer the files from our local computer to the server they'll run on. FTP allow to list, send, receive and delete files on the sever. For this purpose the server must run a FTP server and a FTP client on the computer.

#### Secure Shell Protocol (SSH):
When we start working on the server we'll need to log in and interact with the server remotely. SSH allows the execute command remotely on a server running SSH server. All the data is encrypted in this protocol.

#### SSH File Transfer Protocol (SFTP):
Using FTP for transferring the files is insecure as the files are not encrypted. so it utilizes the SSH to transfer files.


