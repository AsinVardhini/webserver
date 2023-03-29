# Developing a Simple Webserver

# AIM:

To develop a simple webserver to serve html programming pages.

## DESIGN STEPS:

### Step 1:

HTML content creation is done

### Step 2:

Design of webserver workflow

### Step 3:

Implementation using Python code

### Step 4:

Serving the HTML pages.

### Step 5:

Testing the webserver

## PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html>
<head>
<title>My webserver</title>
</head>
<body>
<h1><u>Top five web application development frameworks.</u><h1>
<ul>
<li>Django</li>
<li>Angular or Angular JS</li>
<li>Laravel.</li>
<li>Meteor. </li>
<li>ASP.NET. </li>
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
server_address = ('',80)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()

```

## OUTPUT:
![2023-03-29 (1)](https://user-images.githubusercontent.com/119417735/228418349-76db9b4f-2812-4c8d-801b-d5b43b5fc77e.png)

![2023-03-29](https://user-images.githubusercontent.com/119417735/228418417-e4d268d6-16fc-4d55-816c-e1938689d1a0.png)

## RESULT:
The program is executed succesfully.
