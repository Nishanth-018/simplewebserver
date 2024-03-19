# EX01 Developing a Simple Webserver
## Date:25/02/2024

## AIM:
To develop a simple webserver to serve html pages.

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
<!DOCTYPE html>
<html>
<head>
<title> TOP SOFTWARE COMPANIES IN REVENUE </title>
</head>
<body>
<center><h1>TOP SOFTWARE COMPANIES IN REVENUE</h>
    <hr>
    <table bgcolor="cyan" border="10" cellspacing="10" height="100" width="75">
        <tr align="center">
            <th bgcolor="green">Rank</th>
            <th bgcolor="green">Company</th>
            <th bgcolor="green">Revenue</th>
            <th bgcolor="green">Headquarters</th>
            <th bgcolor="green">Market cap</th>
            <th bgcolor="green">1yr trailing Return</th>
        </tr>
        <tr align="center">
            <th bgcolor="red">1</th>
            <td bgcolor="yellow">Microsoft</td>
            <td bgcolor="yellow">$203 billion</td>
            <td bgcolor="yellow">United States</td>
            <td bgcolor="yellow">$1.82 trillion</td>
            <td bgcolor="yellow">-24.61%</td>
        </tr>
        <tr align="center">
            <th bgcolor="red">2</th>
            <td bgcolor="yellow">Oracle</td>
            <td bgcolor="yellow">$46.07</td>
            <td bgcolor="yellow">United States</td>
            <td bgcolor="yellow">$219 billion</td>
            <td bgcolor="yellow">-9.39</td>
        </tr>
        <tr align="center">
            <th bgcolor="red">3</th>
            <td bgcolor="yellow">SAP SE</td>
            <td bgcolor="yellow">$32.97 billion</td>
            <td bgcolor="yellow">Germany</td>
            <td bgcolor="yellow">$122 billion</td>
            <td bgcolor="yellow">-22.08</td>
        </tr>
        <tr align="center">
            <th bgcolor="red">4</th>
            <td bgcolor="yellow">Salesforce</td>
             <td bgcolor="yellow">$$30.29</td>
            <td bgcolor="yellow">New York</td>
            <td bgcolor="yellow">$130 billion</td>
            <td bgcolor="yellow">-48.41</td>
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
![Screenshot 2024-03-15 093942](https://github.com/Nishanth-018/simplewebserver/assets/149347651/bce9ce73-f2fd-485b-a4aa-8da591d0cbe6)
![Screenshot 2024-03-15 094557](https://github.com/Nishanth-018/simplewebserver/assets/149347651/3ff2ec29-4b44-4e5d-9241-077881e55fe9)



## RESULT:
The program for implementing simple webserver is executed successfully.
