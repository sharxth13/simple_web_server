# EX01 Developing a Simple Webserver

# Date:19.11.2026
# AIM:
To develop a simple webserver to serve html pages and display the configuration details of laptop.

# DESIGN STEPS:
## Step 1:
HTML content creation.

## Step 2:
Design of webserver workflow.

## Step 3:
Implementation using Python code.

## Step 4:
Serving the HTML pages.

## Step 5:
Testing the webserver.

# PROGRAM:
```
from http.server import BaseHTTPRequestHandler, HTTPServer
content='''
<html>
<head>
    <title>TIMETABLE</title>
    <style>
        table,tr,th,td,text{
            border:3px solid rgb(28, 158, 165);
            border-collapse:collapse;
            color: red;
            text-align:center;
            padding: 10px;
            margin-left: auto;
            margin-right: auto;
            margin-top: 50px;
            }
    </style>
</head>
<body>
 <h1>TIMETABLE</h1>
<table>
    <tr>
        <th>Time</th>
        <th>Monday</th>
        <th>Tuesday</th>
        <th>Wednesday</th>
        <th>Thursday</th>
        <th>Friday</th>
        <th>Saturday</th>
    </tr>

<tr>
        <td>8:00 - 9:30 AM</td>
        <td>Web Application</td>
        <td>Web Application</td>
        <td>Calculus and Matrix Algebra</td>
        <td>Computer Architect</td>
        <td>Python Programming</td>
        <td>Cyber Law and Compliance</td>
    </tr>

<tr>
        <td>9:45 AM - 11:15 AM</td>
        <td>Python Programming</td>
        <td>Computer Architect</td>
        <td>Free slot</td>
        <td>Japanese N5</td>
        <td>Free slot</td>
        <td>Career Development</td>
    </tr>
    <tr>
        <td>11:15 - 1:15 PM</td>
        <td colspan="6">Lunch Break</td>
    </tr>

<tr>
        <td>1:15 -2:45 PM</td>
        <td>Free slot</td>
        <td>Calculus and Matrix Algebra</td>
        <td>Free slot</td>
        <td>Cyber Law and Compliance</td>
        <td>Free slot</td>
        <td>Web Application</td>
    </tr>

<tr>
        <td>3:00 - 4:30 PM</td>
        <td>Free slot</td>
        <td>Python Programming</td>
        <td>Free slot</td>
        <td>Free slot</td>
        <td>Free slot</td>
        <td>Japanese N5</td>
    </tr>
</table>

</body>
</html>

class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received")
        self.send_response(200)
        self.send_header('content-type','text/html')
        self.end_headers()
        self.wfile.write(content.encode())
print("this is my webserver")
server_address=('',8000)
httpd=HTTPServer(server_address,MyServer)
httpd.serve_forever()

```
# OUTPUT:
![alt text](<Screenshot 2026-11-19 134214.png>)

![alt text](<Screenshot 2026-11-19 134214.png>)
# RESULT:
The program for implementing simple webserver is executed successfully.
