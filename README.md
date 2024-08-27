# Connecting to a Proxy Server via Terminal

This guide explains how to configure your system to connect to a proxy server using the terminal.

## Important Note

Setting up a proxy server through your system's network settings allows applications like web browsers to use the proxy. However, this method **does not** configure the terminal to use the proxy. If you need to use a proxy server for terminal commands like `apt-get`, you must configure the proxy specifically for the terminal.

## Steps to Configure Proxy for Terminal

1. Open the terminal on your machine.
2. Run the following command to open the configuration file:
   ```bash
   sudo gedit /etc/apt/apt.conf

This will open the configuration file in a text editor.

    Copy the statements below and modify them by replacing tempuser2 with your username and rgukt123 with your password:

    plaintext

    Acquire::http::Proxy "http://tempuser2:rgukt123@staffnet.rgukt.ac.in:3128/";
    Acquire::https::Proxy "http://tempuser2:rgukt123@staffnet.rgukt.ac.in:3128/";
    Acquire::socks::Proxy "http://tempuser2:rgukt123@staffnet.rgukt.ac.in:3128/";
    Acquire::ftp::Proxy "http://tempuser2:rgukt123@staffnet.rgukt.ac.in:3128/";

    Save the file and close the editor.

Verify the Proxy Configuration

To ensure that the proxy server is correctly configured, run the following command in the terminal:

bash

sudo apt-get update

If the proxy is working correctly, you should see a successful connection message.
Why Network Settings Don't Apply to the Terminal

When you configure a proxy through the network settings, it typically only applies to GUI-based applications like web browsers. The terminal operates independently of these settings and requires manual configuration to use a proxy. This is why it’s necessary to follow the steps above to ensure that terminal commands are routed through the proxy server.
