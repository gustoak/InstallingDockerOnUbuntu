# Installing Docker on Ubuntu

Here's a step-by-step guide to installing Docker on Ubuntu and ensuring
that the user who installed it has administrative permissions for
Docker:

1\. Update the System Before installing new software, it's good practice
to update existing packages:

bash Copy code sudo apt update sudo apt upgrade 2. Install Required
Packages You need some basic packages to add new repositories and
install Docker:

bash Copy code sudo apt install apt-transport-https ca-certificates curl
software-properties-common 3. Add the Docker Repository First, add
Docker's GPG key:

bash Copy code curl -fsSL https://download.docker.com/linux/ubuntu/gpg
\| sudo apt-key add - Add Docker's repository to the APT sources list:

bash Copy code sudo add-apt-repository \"deb \[arch=amd64\]
https://download.docker.com/linux/ubuntu \$(lsb_release -cs) stable\" 4.
Install Docker Update the package list to include the new repository:

bash Copy code sudo apt update Now, install Docker:

bash Copy code sudo apt install docker-ce 5. Verify the Installation
Check if Docker is installed and running properly:

bash Copy code sudo systemctl status docker You should see that the
service is active and running.

6\. Add the User to the Docker Group To allow the user who installed
Docker to run Docker commands without sudo, add the user to the docker
group:

bash Copy code sudo usermod -aG docker \$USER Note: Replace \$USER with
the username if necessary. If you are configuring this for another user,
replace \$USER with their username.

7\. Reload Group Permissions You can either log out and log back in to
the user session or use the newgrp command to reload the group
permissions without logging out:

bash Copy code newgrp docker 8. Test the Installation Verify that Docker
is working correctly for the user without sudo:

bash Copy code docker run hello-world If everything is set up correctly,
you should see a welcome message from Docker.
