# EX01 Developing a Simple Webserver
## Date: 10.10.2024

## AIM:
To develop a simple webserver to serve html pages and display the configuration details of laptop.

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
content = """
<html>
    <head>
        <title>Device Specification</title>
    </head>
    <body>
        <h1 align="center">Device Specifications(24900186)</h1>
            <ul type="circle">
                <li><b>Device name</b>	JARVIS</li>
                <li><b>Processor</b>	13th Gen Intel(R) Core(TM) i5-1335U   1.30 GHz</li>
                <li><b>Installed RAM</b>	16.0 GB (15.7 GB usable)</li>
                <li><b>Device ID</b>	F572A584-4230-4A55-BBC5-D66076BAC5FB</li>
                <li><b>Product ID</b>	00330-80000-00000-AA225</li>
                <li><b>System type</b>	64-bit operating system, x64-based processor</li>
                <li><b>Pen and touch</b>	No pen or touch input is available for this display</li>
            </ul>
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
![alt text](<Screenshot 2024-11-12 092627.png>)

![alt text](<Screenshot 2024-11-12 093006.png>)

## RESULT:
The program for implementing simple webserver is executed successfully.
