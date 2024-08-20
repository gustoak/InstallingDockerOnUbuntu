
# Docker Installation Guide on Ubuntu

This guide will help you install Docker on Ubuntu and ensure that the user who installs it has administrative permissions without needing to use `sudo` for every command.

## Installation Steps

### 1. Update the system
First, update your package list to ensure you're installing the latest available packages:
```bash
sudo apt update
sudo apt upgrade
```
### 2. Install necessary dependencies
Install the necessary packages to allow the addition of a new HTTPS repository:

```bash
sudo apt install apt-transport-https ca-certificates curl software-properties-common
```
3. Add Docker's official GPG key
Run the following command to add Docker's GPG key:
```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```
4. Add the Docker repository to APT
Now, add the Docker repository:

```bash Copy code
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null5.
```
Update APT again
After adding the new repository, update the package list:

```bash Copy code
sudo apt update
```
6. Install Docker
Now, install Docker with the following command:

```bash Copy code
sudo apt install docker-ce
```
7. Verify Docker installation
Check if Docker is running properly:

```bash Copy code
sudo systemctl status docker
If Docker is running correctly, you should see an output indicating that the service is active.
```
8. Add the user to the docker group
To avoid the need for sudo when running Docker commands, add your user to the docker group:

```bash Copy code
sudo usermod -aG docker $USER

Note: Replace $USER with the specific username if you want to add a different user.
```
9. Restart your session
For the changes to take effect, log out and log back in or reboot your system:

```bash Copy code
newgrp docker
```
10. Test without sudo
Finally, test Docker by running a simple container without sudo:

``` bash Copy code
docker run hello-world
```
If the container runs successfully, Docker has been installed correctly, and the user has administrative permissions without needing to use sudo.
