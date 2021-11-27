# Developing a Simple Webserver
## AIM:
To develop a simple webserver to top 5 programing launguages.

## DESIGN STEPS:
### Step 1: 
HTML content creation
### Step 2:
Design of webserver workflow
### Step 3:
Implementation using Python code
### Step 4:
Serving the HTML pages.
### Step 5:
Testing the webserver

## PROGRAM:
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html>
<head>
<title>My webserver</title>
</head>
<body>
<h1>top 5 programing launguages</h1>
Python
<br>

Python is an interpreted, object-oriented, high-level programming language with dynamic semantics. Its high-level built in data structures
<br>

C / C++ 
<br>

C (/ˈsiː/, as in the letter c) is a general-purpose, procedural computer programming language supporting structured programming, lexical variable scope, and recursion, with a static type system
<br>

JAVA
<br>

Java is a programming language and computing platform first released by Sun Microsystems in 1995. It has evolved from humble beginnings to power a large share of today’s digital world
<br>

R Language
<br>

R Programming Language for Statistical Computing and Graphical Representation
<br>

Kotlin
<br>

A modern programming language
that makes developers happier.
<br>

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
server_address = ('',8080)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()


## OUTPUT:
![serverside1](./images/serverside1.png)
![serverside2](./images/serverside2.png)
![clientside](./images/clientside.png)


## RESULT:
