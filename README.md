# TGTG Scanner

Scanns favorite TGTG Magic Bags for new available items and notifies via mail, IFTTT or pushSafer.

## Disclaimer

TGTG forbids the use of their plattform the way this tool does. In their Terms and Conditions it says: "The Consumer must not misuse the Platform (including hacking or 'scraping')."

If you use this tool you do it at your own risk. TGTG may stop you from doing so and may even delete your account.

I would recommend to create a new account for the scanner.

## Installation

You can install this tool on any computer.
It is recommended to install the tool on a NAS like Synology or a Raspberry Pi. You can also use a virtual cloud server. Starting at 1,00 €/Month at Strato.de or try AWS free tier.

If you have any problems or questions feel free to create a new issue or even contribute to the project.

You have the following three options to install the scanner, ascending in complexity:

### Use prebuild Release

This is the simplest but least flexible solution for most OS.

1. Download latest Release from https://github.com/Der-Henning/tgtg/releases for your OS
2. Unzip Archiv
3. Edit ```config.ini``` as described in the file
4. Run scanner

You can run the scanner manually if you need it or add it to your autostart or create a service.

### Run with Docker

My prefered method with a pre build multi-arch linux image.

1. Install Docker and docker-compose
2. Edit ```docker-compose.yml``` as described in the file
3. Run ```docker-compose up -d```

### Run from source

Method for pros and developers.

1. Install python3
2. Run ```pip3 install -r requirements.txt```
3. Create ```/src/config.ini``` as described in the file ```config.template.ini```
4. Register ```python {install directory}/src/scanner.py``` as a service or just run it manually

### Running

When the scanner is started it will send a test notification on all configured notifiers. If you don't reveive any notifications, please check your configuration.

## Developing

For developement I recommend using docker. The Makefile depends on docker and docker-compose.

```make start-dev``` starts scanner in python container.

```make image``` builds docker image

```make bash``` starts python image with mounted project

### Building executables

The executables are build with pyinstaller.

```pip install -r requirements.txt```

```pip install pyinstaller```

```pyinstaller scanner.spec```

---

<a href="https://www.buymeacoffee.com/henning" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png" alt="Buy Me A Coffee" width="200"></a>