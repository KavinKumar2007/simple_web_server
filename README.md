# EX01 Developing a Simple Webserver

# Date:18.09.2025
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
~~~

from http.server import HTTPServer,BaseHTTPRequestHandler
content ='''<html>
<h1>Configuration Details of Laptop</h1>
<h2>Device Specification</h2>
<pre>Device name	TMP215-75-G2
Processor	Intel(R) Core(TM) Ultra 5 125H (1.20 GHz)
Installed RAM	16.0 GB (15.5 GB usable)
Device ID	E3F06795-1915-4187-8C56-F3F3634559FF
Product ID	00342-42784-11476-AAOEM
System type	64-bit operating system, x64-based processor
Pen and touch	No pen or touch input is available for this display
</pre>
<h2>Windows Specifications</h2>
<pre>Edition	Windows 11 Home Single Language
Version	24H2
Installed on	‎01-‎09-‎2025
OS build	26100.4946
Experience	Windows Feature Experience Pack 1000.26100.197.0
</pre>
<h2>Support</h2>
<p>Manufacturer Acer</p>

</html>'''
class myserver(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received....")
        self.send_response(200)
        self.send_header('Content-type','text/html')
        self.end_headers()
        self.wfile.write(content.encode())
print("This is my webserver")
server_address = ('', 8000)
httpd = HTTPServer(server_address, myserver)
httpd.serve_forever()

~~~
# OUTPUT:
![alt text](<Screenshot (20).png>)
# RESULT:
The program for implementing simple webserver is executed successfully.
