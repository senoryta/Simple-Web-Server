# Developing a Simple Webserver
## AIM:
To develop a simple webserver to serve html pages.

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
    <h1>Top 5 Revenue Generating Companies<h1>
    <UL TYPE=“circle”>
    <LI> Flipkart </LI>    
    <LI> SBI </LI>
    <LI> Infosys </LI>
    <LI> ONGC </LI>
    <LI> ITC </LI>
    </UL>
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

## OUTPUT:
<img width="960" alt="Screenshot 2023-09-09 093154" src="https://github.com/Kathir-2703/FWAD-EXP-1/assets/64436376/791a015c-4c90-4a42-82b7-84d49577ef6f">
<img width="960" alt="Screenshot 2023-09-09 093120" src="https://github.com/Kathir-2703/FWAD-EXP-1/assets/64436376/9409aac7-d82d-4031-a8bb-863e238d895e">

## RESULT:
The program for implementing simple webserver is executed successfully.
