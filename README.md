# Resolving Localhost RPC Address Configuration Issue on a Nubit Node

Running a Nubit node can be a rewarding endeavor, especially if you're interested in blockchain technology and decentralized networks. However, like any technical project, you might encounter some hiccups along the way. One common issue that many users face is related to the RPC (Remote Procedure Call) address configuration. This guide will walk you through the problem and provide a step-by-step solution to get your node up and running smoothly.

## The Problem: Localhost RPC Address Configuration Error

While setting up my Nubit node, I encountered an error related to the RPC address configuration. This issue typically arises when the node is unable to connect to the specified RPC address, which in most cases is set to `localhost`. The error message might look something like this:

![error](https://github.com/user-attachments/assets/83e7c586-27c6-4311-afaf-5bc5aa141e43)

in the last line you can see the error service/rpc: invalid addess: no suitable address found


This error can occur due to several reasons:
1. **Incorrect RPC address in the `config.toml` file**: The default configuration might not match your server's network settings.
2. **Firewall or network settings**: The VPS or local machine might have restrictions that prevent connections to `localhost`.
3. **Service not running**: The RPC service might not be started correctly.

## The Solution: Correcting the RPC Address Configuration

To resolve this issue, follow these steps:

### 1. Access Your VPS or Local Machine

Log in to your server or local machine using SSH or terminal. Use the following command:

```bash
ssh your_username@your_vps_ip
