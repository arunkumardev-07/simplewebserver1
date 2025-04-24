# EX01 Developing a Simple Webserver
## Date: 18/04/2025

## AIM:
To develop a simple webserver to serve html pages and display the list of protocols in TCP/IP Protocol Suite.


## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Serving the HTML pages.

### Step 5:
Testing the webserver.

## PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content="""
<!DOCTYPE html>

<html>
<head>
    <title>TCP/IP Protocol Suite</title>
    <style>
        
    </style>
</head>
<body>

    <h1>TCP/IP Protocol Suite</h1>

    <table>
        <tr>
            <th>LAYER</th>
            <th>PROTOCOLS (EXAMPLES)</th>
            <th>FUNCTION</th>
        </tr>
        <tr>
            <td>Application Layer</td>
            <td>HTTP, HTTPS, FTP, SMTP, DNS, DHCP</td>
            <td>Provides network services to applications</td>
        </tr>
        <tr>
            <td>Transport Layer</td>
            <td>TCP, UDP</td>
            <td>Manages end-to-end communication</td>
        </tr>
        <tr>
            <td>Internet Layer</td>
            <td>IP (IPv4, IPv6), ICMP, ARP, IGMP</td>
            <td>Handles addressing and routing</td>
        </tr>
        <tr>
            <td>Network Access Layer</td>
            <td>Ethernet, Wi-Fi, PPP, SLIP</td>
            <td>Manages physical data transmission</td>
        </tr>
    </table>

</body>
</html>
"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('content-type','text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',8000)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()


```

## OUTPUT:
![Screenshot 2025-04-17 004415](https://github.com/user-attachments/assets/99054911-a8a3-417b-a360-c4fe53232d96)

![Screenshot 2025-04-17 004526](https://github.com/user-attachments/assets/2a5bebcf-502b-4810-8081-acfa7c41c497)


## RESULT:
The program for implementing simple webserver is executed successfully.
