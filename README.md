# EX01 Developing a Simple Webserver
## Date: 23.9.2025

## AIM:
To develop a simple webserver to serve html pages and display the Device Specifications of your Laptop.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Import the necessary modules.

### Step 5:
Define a custom request handler.

### Step 6:
Start an HTTP server on a specific port.

### Step 7:
Run the Python script to serve web pages.

### Step 8:
Serve the HTML pages.

### Step 9:
Start the server script and check for errors.

### Step 10:
Open a browser and navigate to http://127.0.0.1:8000 (or the assigned port).

## PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html>
    <head>
       <title>
        sumi's Page
       </title>
    </head>
    <body>
        <h1><b>
            Device Specification(SUMI)
            </b>
        </h1>
        <table BORDER="5">
        <tr>
        <th>S.NO</th>
        <th>DEVICE NAME</th>
        <th>RAM</th>
        <th>DEVICE ID</th>
        <th>PRODUCT ID</th>
        <th>SYSTEM TYPE</th>
        </tr>
        <tr>
            <td>1</td>
        <td>SUMI</td>
        <td>AMD Ryzen AI 7 350 w/Radeon 860M</td>
        <td>32.0GB</td>
        <td>00356-24813-95686-AAOEM</td>
        <td>64-bit operating system,x64-based processor</td>
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
## OUTPUT :
![alt text](<Screenshot 2025-09-23 143845.png>)
![alt text](<Screenshot 2025-09-23 144058.png>)

## RESULT:
The program for implementing simple webserver is executed successfully.
