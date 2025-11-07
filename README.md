# Pwnagotchi Cyber Viking Integration

Welcome to the Pwnagotchi Cyber Viking Cooperation project! 🚀 This script is designed to download and process Wi-Fi network data caputered by Pwnagotchi, processed with wpa-sec, and inject the networks into your Bjorn system. Additionally, it integrates with Discord to send the collected networks to your server! 🌐
Optional ofcourse 🤓.

![Pwnagotch&BjornCoop](/assets/colab.png)

But that's not all—prepare yourself for an epic journey as Pwnagotchi teams up with the legendary cyber Viking, **Bjorn**, to hack the planet together! ⚔️

## Features
- Downloads Wi-Fi network data from [wpa-sec.stanev.org](https://wpa-sec.stanev.org/).
- Processes the data and removes duplicate networks.
- Sends the unique networks to Discord using a webhook (optional).
- Injects the networks into your system with `nmcli`.
- Uses environment variables for configuration.
- If you already know the network you want to test just put it's SSID and PASSWORD in order: `SSID:PASSWORD`
and run the script.

## Screens

![processing](/assets/injecting.png)


## Installation

### Requirements
- Python 3.x
- `requests` library
- `python-dotenv` library
- Bjorn with Internet connection

### Steps to Install

1. Install required Python libraries:

    64bit OS

    ```bash
    sudo apt update && sudo apt install python3-dotenv -y
    ```

    32bit OS

    ```bash
        sudo apt update && sudo pip install python-dotenv --break-system-packages
    ```

2. Clone the repository:
    ```bash
    git clone https://github.com/LOCOSP/BjornWpaSecHarvester.git
    cd BjornWpaSecHarvester
    ```


3. Create a `.env` file in the root directory of the project.

    ```bash
    nano .env
    ```

4. Populate the `.env` file with the following variables:

    ```env
    COOKIE_VALUE= #wpa-sec key here 
    URL=https://wpa-sec.stanev.org/?api&dl=1
    DISCORD_WEBHOOK_URL= #discord webhook here

    #if you don't want to use wpa-sec service leave it blank but than my-cracked.txt required.
    #if you don't want to use discord webhooks leave it blank.
    ```

    Make sure to replace the placeholders with your actual values:
    - `COOKIE_VALUE`: The value of [wpa-sec Key](https://wpa-sec.stanev.org/?get_key) .
    - `URL`: The URL from which to download the Wi-Fi network data.
    - `DISCORD_WEBHOOK_URL`: The Discord webhook URL to send the processed file.


5. **`my-cracked.txt`** file is needed if you are not using wpa-sec service. 

    `nano my-cracked.txt`

    enter your known networks in format:
    ```
    SSID:PASSWORD
    SSID:PASSWORD
    ```

6. You're ready to go! Run the script:

    ```bash
    python3 BjornWpaSecHarvester.py
    ```

## Note

- Ensure that `nmcli` is installed and available on your system. This tool is used to inject the networks into your Wi-Fi configuration.

## Bjorn's Blessing 🏰⚔️

You've just embarked on a journey of great conquest! Pwnagotchi and Bjorn, the cyber Viking, have joined forces to bring you the most secure and automated Wi-Fi network processing system! With their powers combined, no Wi-Fi network is safe from their reach! ⚡

Get ready for a legendary partnership where Pwnagotchi handles the tech and Bjorn handles... well, everything else! 😎

Let the **cyber Viking revolution** begin! 🔥

### Contributions

Feel free to contribute to the project! Open an issue or submit a pull request if you have any improvements or fixes to share.

---

Bjorn and Pwnagotchi wish you smooth and secure network hunting! 🛡️🌍
