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

from http.server import HTTPServer,BaseHTTPRequestHandler

content="""
<!DOCTYPE html>
<html>
    <head>
        <title> Saveetha Engineering college</title>
    </head>
    <body text="000000" bgcolor="F5BDFFS">  
            <h1 align="center"> Saveetha Engineering college</h1>
            <h2 align="right"> Autonomous</h2>
                <ul type="square">
                    <li> CSE(cyber security)</li>
                    <li> CSE(Iot)</li>
                    <li> AIDS</li>
                    <li> AIML</li>
                    <a href="http://www.saveetha.ac.in">visit our website</a>
                    
                </ul>

            </body>
    </head>
</html> 
"""

class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
       print("Get request received...")
       self.send_response(200)
       self.send_header('content-type','text/html; charset=utf-8')
       self.end_headers()
       self.wfile.write(content.encode())

print("This is my webserver")
server_address=('',8000)
httpd = HTTPServer(server_address, MyServer)
httpd.serve_forever()


## OUTPUT:
![web](https://user-images.githubusercontent.com/119417735/228305431-a70bf995-f8b8-421d-ba95-1233cd175c01.png)

![webou](https://user-images.githubusercontent.com/119417735/228306772-1e481da3-4a5e-4fdb-a4ec-b5a1fe29c27d.png)

## RESULT:
The program is executed succesfully.
