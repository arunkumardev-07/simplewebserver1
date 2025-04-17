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
# HTML content to serve
content = """
<!doctype html>
<html>
<head>
<title>My Web Server</title>
</head>
<body>
<center><h1>TCP/IP PROTOCOLS</h1></center><br>
<h3>
1. Application Layer Protocols - HTTP, FTP, DNS<br>
2. Transport Layer Protocols - TCP/UDP<br>
3. Internet Layer Protocols - IPv4/IPv6<br>
4. Link Layer Protocols - MAC<br>
</h3>
</body>
</html>
"""
class MyHandler(BaseHTTPRequestHandler):
    def do_GET(self):
        self.send_response(200)
        self.send_header("Content-type", "text/html")
        self.end_headers()
        self.wfile.write(content.encode())

# Set up and run the server
def run(server_class=HTTPServer, handler_class=MyHandler, port=8000):
    server_address = ('', port)
    httpd = server_class(server_address, handler_class)
    print(f"Serving HTTP on port {port}...")
    httpd.serve_forever()

# Run the server
if __name__ == '__main__':
    run()
content = """
<html>
<head>
<title>Top five software companies in revenue</title>
</head>
<body>
<h1 align="center">
TOP FIVE SOFTWARE COMPANIES IN REVENUE</h1>
<table align="center" border="2" cellspacing="5" cellpadding="5" width="800" height="500">
<tr>
<th>RANK</th>
<th>COMPANY NAME</th>
<th>REVENUE</th>
</tr>
<tr>
<td>1</td>
<td>Apple(AAPL)</td>
<td>$385.70 B </td>
</tr>
<tr>
<td>2</td>
<td>Alphabet(Google)</td>
<td>$307.39 B</td>
</tr>
<tr>
<td>3</td>
<td>Microsoft</td>
<td>$227.58 B</td>
</tr>
<tr>
<td>4</td>
<td>Ibm</td>
<td>$61.85 B</td>
</tr>
<tr>
<td>5</td>
<td>Oracle</td>
<td>$51.62 B</td>
</tr>
</table>
</body>
</html>

"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
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
