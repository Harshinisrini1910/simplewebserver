# EX01 Developing a Simple Webserver
## Date:

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
<html>
    <head>
        <title> simple webserver </title>
    </head>
    <body>
       <table border="2" cellspacing="12" cellpadding="12" height="25" width="50">
       <h1> TOP FIVE SOFTWARE COMPANIES </h1>
            <tr>
                <th>Rank</th>
                <th>Company</th>
                <th>Revenue</th>
            </tr>
            <tr>
                <th>1</th>
                <th>Micro Soft</th>
                <th>$86.6</th>
            </tr>
            <tr>
                <th>2</th>
                <th>Oracle</th>
                <th>$37.1</th>
            </tr>
            <tr>
                <th>3</th>
                <th>SAP</th>
                <th>$20.9</th>
            </tr>
            <tr>
                <th>4</th>
                <th>Symantec</th>
                <th>$6.8</th>
            </tr>
            <tr>
                <th>5</th>
                <th>VMware</th>
                <th>$5.2</th>
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
<!doctype html>
<html>
<head>
<title> My Web Server</title>
</head>
<body>
<h1>Top Five Revenue from Companies</h1>
<table border=2>
<tr>
<th> Company Name </th>
<th> Revenue </th>
<th> Financial Year </th>
</tr>

<tr>
<td> Microsoft </td>
<td> 86$ </td>
<td> 2014 </td>
</tr>

<tr>
<td> Oracle </td>
<td> 37$ </td>
<td> 2013 </td>
</tr>

<tr>
<td> SAP </td>
<td> 20$ </td>
<td> 2013 </td>
</tr>

<tr>
<td> VMware </td>
<td> 5.2$ </td>
<td> 2013 </td>
</tr>

<tr>
<td> CA Technologies </td>
<td> 4.7$ </td>
<td> 2013 </td>
</tr>

</body>
</html>
'''

class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200) 
        self.send_header("content-type", "text/html")       
        self.end_headers()
        self.wfile.write(content.encode())

print("This is my webserver") 
server_address =('',8000)
httpd = HTTPServer(server_address,MyServer)
httpd.serve_forever()

```

## OUTPUT:
![Screenshot 2024-04-16 at 11 49 33 PM](https://github.com/Harshinisrini1910/simplewebserver/assets/161415847/99142d8f-91a4-4875-b764-f93d82e2751a)

![Screenshot 2024-04-16 at 11 49 33 PM](https://github.com/Harshinisrini1910/simplewebserver/assets/161415847/d2cd006c-d7e2-49d6-a9a3-58579c115b9c)


## RESULT:
The program for implementing simple webserver is executed successfully.
