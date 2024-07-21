# Resolving Localhost RPC Address Configuration Issue on a Nubit Node

Running a Nubit node can be a rewarding endeavor, especially if you're interested in blockchain technology and decentralized networks. However, like any technical project, you might encounter some hiccups along the way. One common issue that many users face is related to the RPC (Remote Procedure Call) address configuration. This guide will walk you through the problem and provide a step-by-step solution to get your node up and running smoothly.

## The Problem: Localhost RPC Address Configuration Error

While setting up my Nubit node, I encountered an error related to the RPC address configuration. This issue typically arises when the node is unable to connect to the specified RPC address, which in most cases is set to `localhost`. The error message might look something like this:

![screen](https://github.com/user-attachments/assets/813aa78f-9345-40f0-9475-de0a2fef862a)

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
```

### 2. Locate the `config.toml` File

The `config.toml` file is typically located in the `.nubit-light-nubit-alphatestnet-1` directory within your home directory. Navigate to this directory with:

```bash
cd /home/your_username/.nubit-light-nubit-alphatestnet-1
```
### 3. Edit the config.toml File

Open the config.toml file using vim or your preferred text editor:

```bash
vim config.toml
```
### 4. Modify the RPC Address

Find the [RPC] section in the config.toml file. It will look like this:
```toml
[RPC]
  Address = "localhost"
  Port = "26658"
  SkipAuth = false
```
Change the Address from localhost to 0.0.0.0 to allow connections from any network interface:
```toml
[RPC]
  Address = "0.0.0.0"
  Port = "26658"
  SkipAuth = false
```
### 5. Save and Exit

To save your changes and exit vim, press Esc to ensure you are in command mode, then type :wq and press Enter.

### 6. Restart the Nubit Node
Restart your Nubit node to apply the changes using the following command:
```bash
curl -sL1 https://nubit.sh | bash
```
## Conclusion

Configuring the RPC address correctly is crucial for the proper functioning of your Nubit node. By following these steps, you should be able to resolve the localhost RPC address configuration issue and ensure that your node is accessible and operational. Running a Nubit node can be a complex but rewarding task, and troubleshooting issues like these is part of the learning process. Happy coding, and may your node run smoothly!
