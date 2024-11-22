How it works:

1) Local Server: The script starts a local server that listens on LOCAL_HOST:LOCAL_PORT. This can be any IP and port that you want to use.

2) Remote Forwarding: When a client connects to the local server, the script opens a connection to the remote server (REMOTE_HOST:REMOTE_PORT) and forwards any data received from the local client to the remote server, and vice versa.
3) Multithreading: Two threads are used per connection: one for forwarding data from the client to the remote server and another for forwarding data back from the remote server to the client.

To run:
Replace REMOTE_HOST with the address of the server you want to forward data to (e.g., an external IP or domain).
Adjust the port numbers (LOCAL_PORT and REMOTE_PORT) as necessary.
Save the script to a .py file, and run it using Python:

python pf.py

 or

 python3 pf.py

How to run the code :
1) Edit the Code (Optional):
Modify the REMOTE_HOST, REMOTE_PORT, and LOCAL_PORT values in the script according to your use case:

LOCAL_PORT: The port on your local machine that you want to listen on.
REMOTE_HOST: The remote server (IP or domain name) you want to forward traffic to.
REMOTE_PORT: The port on the remote server where you want to forward traffic.
Example:
If you want to forward traffic from your local machine's port 8080 to the remote server example.com on port 80, your variables should look like this:


LOCAL_HOST = '0.0.0.0'  # Listens on all interfaces
LOCAL_PORT = 8080        # Port to listen on your local machine
REMOTE_HOST = 'example.com'  # Remote server
REMOTE_PORT = 80            # Port on the remote server


Run the Script:

Open a terminal or command prompt and navigate to the directory where the port_forwarder.py script is located.

Example:
If you saved it in a folder called my_port_forwarder on your desktop:

On Windows: Open Command Prompt and run:

python3 pf.py

On macOS/Linux: Open a Terminal and run:

python3 pf.py

The script should now be running and listening on the local port (LOCAL_PORT). Any connection that hits that port will be forwarded to the remote server (REMOTE_HOST and REMOTE_PORT).


 *Test the Port Forwarding*:
To test the port forwarding, open a new terminal or command prompt and try to connect to your local server. For example, if you're forwarding to example.com on port 80, you can use a web browser or curl to connect:

Command :-->

curl http://localhost:8080

Troubleshooting:
Permission Issues:
If you get an error like PermissionError: [Errno 13] Permission denied when trying to listen on ports below 1024 (like port 80), you may need to run the script with elevated privileges (admin rights). You can do this by:

Windows: Right-click on Command Prompt and choose "Run as Administrator".
macOS/Linux: Use sudo:

sudo python3 pf.py

## Connect ME 🥷

 <a href="https://jawstar.medium.com" target="_blank">
    <img src="https://img.shields.io/badge/Medium-FFA116?style=for-the-badge&logo=medium&logoColor=Black" alt="Medium" />
  </a>



## $$ 🤑 DONATE ME 🤑 $$

<a href="https://buymeacoffee.com/jawstar_9999" target="_blank">
    <img src="https://img.shields.io/badge/buymeacoffee-FFA116?style=for-the-badge&logo=buymeacoffee&logoColor=Yellow" alt="buymeacoffee" />
  </a>