# Kali Projects
# Cybersecurity Lab Projects

This repository contains simple lab projects designed to demonstrate fundamental cybersecurity tools and techniques.

---

## Project 1: SSH Brute Force with Hydra

**Goal:** Use Hydra to brute-force an SSH login.

### How to Run

1.  **Ensure Hydra is installed on Kali Linux:**

    ```bash
    sudo apt update
    sudo apt install hydra -y
    ```

2.  **Run the brute-force command:**
    Replace `<username>`, `<target_ip>`, and `<path_to_wordlist>` with your specific values.

    ```bash
    hydra -l <username> -P <path_to_wordlist> ssh://<target_ip>
    ```

    **Example:**

    ```bash
    hydra -l root -P /usr/share/wordlists/rockyou.txt ssh://192.168.56.10
    ```

---

## Project 2: Simple Chat with Netcat

**Goal:** Set up a basic chat server and client using Netcat.

### How to Run

1.  **On the Ubuntu machine (Server):**
    Start listening on a chosen port (e.g., `1234`).

    ```bash
    nc -l -p 1234
    ```

2.  **On the Kali Linux machine (Client):**
    Connect to the server's IP address and the specified port.

    ```bash
    nc 192.168.56.10 1234
    ```

    Once connected, anything you type on either the client or server side will be sent back and forth, enabling a simple chat.

---

## Project 3: Minimal Python HTTP Server

**Goal:** Serve files over HTTP from the current directory on an Ubuntu machine.

### How to Run

1.  **On the Ubuntu machine:**
    Navigate to the directory you want to serve, then run the Python built-in HTTP server on port `8080`.

    ```bash
    python3 -m http.server 8080
    ```

2.  **Access from Kali Linux or a web browser:**
    Open a web browser or use a tool like `curl` on Kali to access the server. Replace `192.168.56.10` with the actual IP address of your Ubuntu machine.

    ```
    [http://192.168.56.10:8080](http://192.168.56.10:8080)
    ```
