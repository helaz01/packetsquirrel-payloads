
# Payload Library for the Packet Squirrel by Hak5

This repository contains payloads and extensions for the Hak5 Packet Squirrel, developed by the Hak5 Community. 

Have a great payload?  Submit it by forking the payload repository and submitting a pull request!A

Learn more about Github pull requests [here](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests) or from the Hak5 Bash Bunny tutorial [here](https://www.youtube.com/watch?v=H6z9BXevsZg).

## Packet Squirrel Versions

The Packet Squirrel Mark II expands on the capabilities of the original Packet Squirrel, introducing new commands and more flexible networking configurations.

Payloads for the original Packet Squirrel can be found in the `legacy-mk1` directory.  These payloads may not work without modification on the Packet Squirrel Mark II.

## About the Packet Squirrel

The Packet Squirrel Mark II by Hak5 is a stealthy pocket-sized man-in-the-middle.

This Ethernet multi-tool is designed to give you covert remote access, painless packet captures, and secure VPN connections with the flip of a switch.

-   [Purchase at Hak5](https://hak5.org/products/packet-squirrel "Purchase at Hak5")
-   [Documentation](https://docs.hak5.org/packet-squirrel-mark-ii "Documentation")
-   [Forums](https://forums.hak5.org/forum/94-packet-squirrel/ "Forums")
-   [Discord](https://hak5.org/discord "Discord")

![Packet Squirrel](https://cdn.shopify.com/s/files/1/0068/2142/products/Packet_Squirrel_300x.jpg)

## Updating 

If you've downloaded this repository via `git`, you can update to the latest versions of the payloads with `git pull`.  If you downloaded as a zip or other file, please download the latest from [github](https://github.com/hak5/packetsquirrel-payloads/).

## Disclaimer

Generally, payloads may execute commands on your device. As such, it is possible for a payload to damage your device. Payloads from this repository are provided AS-IS without warranty. While Hak5 makes a best effort to review payloads, there are no guarantees as to their effectiveness or safety. As with any script, you are advised to proceed with caution.

## Legal

Payloads from this repository are provided for educational purposes only.  Hak5 gear is intended for authorized auditing and security analysis purposes only where permitted subject to local and international laws where applicable. Users are solely responsible for compliance with all laws of their locality. Hak5 LLC and affiliates claim no responsibility for unauthorized or unlawful use.

## Contributing

Once you have developed your payload, you are encouraged to contribute to this repository by submitting a Pull Request. Reviewed and Approved pull requests will add your payload to this repository, where they may be publicly available.

Please adhere to the following best practices and style guide when submitting a payload.

Hak5 reserves the right to modify payloads to meet the guidelines when necessary, or to decline to include a payload in the public repository.

Please ensure that any default configuration values do not point to actual services!  Do not include *your* passwords or login information in submitted payloads!

### Naming Conventions

Please give your payload a unique and descriptive name. Do not use spaces in payload names. Each payload should be placed into its own directory, with `-` or `_` used in place of spaces, in one of the categories such as exfiltration, phishing, remote_access or recon.  Please do not create your own category.

The payload itself should be named `payload`.

Additional files and documentation can be included in the payload directory.  Documentation should be in `README.md` or `README.txt`.

### Comments

Payloads should begin with comments specifying at the very least the name of the payload and author. Additional information such as a brief description, the target, any dependencies / prerequisites and the LED status used is helpful.

    # Title: Meterpreter-via-SSH
	# Description: Covert meterpreter shell via overt SSH connection
	# Author: Zappus
	# Version: 1.0
	# Category: Remote-Access
	# Net Mode: NAT
	# Firmware: 1.2
	#
	# LED State Descriptions
	# Magenta Solid - Configuring NETMODE
	# LED OFF - Waiting for BUTTON
	# Red Blink 2 Times - SSH Connection Failed
	# Amber Blink 5 Times - SSH Connection Successful
	# Red Blink 1 Time - Meterpreter Failed
	# Cyan Blink 1 Time - Meterpreter Successful

### Configuration Options

Configurable options should be specified in variables at the top of the payload.txt file

    # Options
    SSH_USER="username"
	SSH_HOST="hostname"
	MSF_PORT=31337

### LED

The payload should use common payload states rather than unique color/pattern combinations when possible with an LED command preceding the Stage or `NETMODE`.

	LED SETUP
	NETMODE NAT

Common payload states include a `SETUP`, with may include a `FAIL` if certain conditions are not met. This is typically followed by either a single `ATTACK` or multiple `STAGEs`. More complex payloads may include a `SPECIAL` function to wait until certain conditions are met. Payloads commonly end with a `CLEANUP` phase, such as moving and deleting files or stopping services. A payload may `FINISH` when the objective is complete and the device is safe to eject or turn off. These common payload states correspond to `LED` states.

