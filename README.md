# Installing Docker on Ubuntu

# Docker Installation Guide on Ubuntu

This guide will help you install Docker on Ubuntu and ensure that the user who installs it has administrative permissions without needing to use `sudo` for every command.

## Installation Steps

### 1. Update the system
First, update your package list to ensure you're installing the latest available packages:
```bash
sudo apt update
sudo apt upgrade

2. Install necessary dependencies
Install the necessary packages to allow the addition of a new HTTPS repository:

sudo apt install apt-transport-https ca-certificates curl software-properties-common

3. Add Docker's official GPG key
Run the following command to add Docker's GPG key:
