---
description: Guide for running the Taraxa Node with Docker on Windows
---

# Windows

## 1. Install Docker

Before running the node we need to install Docker.

You can download Docker Desktop for Windows from [here](https://desktop.docker.com/win/stable/amd64/Docker%20Desktop%20Installer.exe).

![Download Docker](../.gitbook/assets/node-setup/windows/1-download.png)

After the download finishes you will find the executable file in your downloads folder.

![Downloaded Docker](../.gitbook/assets/node-setup/windows/2-downloaded.png)

Open `Docker Desktop Installer.exe`. and you should see a screen similar to this:

![Open Docker](../.gitbook/assets/node-setup/windows/3-open.png)

Press "Ok" and don't uncheck any of the default options.

Now Docker is installing:

![Install Docker](../.gitbook/assets/node-setup/windows/4-install.png)

After the installation is finished you can click the "Close" button and Docker is going to start automatically.

![Installed Docker](../.gitbook/assets/node-setup/windows/5-installed.png)

## 2. Install WSL 2

Docker  needs to install extra dependencies for running Linux containers on Windows.

You will get a notice similar to the one below.

*NOTE: Don't close the notice window*

If you click on the provided link a new browser window will open and we can download the dependency.

![WSL Notice](../.gitbook/assets/node-setup/windows/6-wsl-notice.png)

Click on the link under "Download the latest package"

![Download WSL 2](../.gitbook/assets/node-setup/windows/7-wsl-download.png)

You can find the executable in your downloads folder.

![Downloaded WSL 2](../.gitbook/assets/node-setup/windows/8-wsl-downloaded.png)

Open the executable and click "Next" on the first screen.

![WSL 2 Install](../.gitbook/assets/node-setup/windows/9-wsl-install.png)

After the setup is complete click the "Finsh" button.

![WSL 2 Installed](../.gitbook/assets/node-setup/windows/10-wsl-finish.png)

Now you can click the "Restart" button on the original notice window.

![WSL 2 Restart](../.gitbook/assets/node-setup/windows/11-wsl-restart.png)

## 3. Starting Docker Desktop

If everything went well you will see the following message.

![Docker Desktop is starting](../.gitbook/assets/node-setup/windows/12-docker-stating.png)

And if you open the Docker Desktop application you should see the following window.

![Docker Desktop App is starting](../.gitbook/assets/node-setup/windows/13-docker-starting-2.png)

When Docker Desktop starts successfuly you will see the yellow icon turn green.

![Docker Desktop Started](../.gitbook/assets/node-setup/windows/14-docker-started.png)

## 4. Download Taraxa scripts

In order to run the node we need a set of scripts. You can download the scripts from [this link](https://github.com/Taraxa-project/taraxa-ops).

![Download Taraxa Scripts](../.gitbook/assets/node-setup/windows/15-download-scripts.png)

Click on "Download ZIP" under the code menu and the download should start.

After the download is complete you can find a new zip file in your downloads folder.

Right click on the file and select the "Extract All" option.

![Extract Scripts](../.gitbook/assets/node-setup/windows/17-open-extract-scripts.png)

In the first screen click the "Browse" button.

![Extract Browse](../.gitbook/assets/node-setup/windows/18-extract-scripts.png)

Now select "Desktop" from the left menu.

![Select Desktop](../.gitbook/assets/node-setup/windows/19-extract-scripts-desktop.png)

And finally click the "Extract" button.

![Extract](../.gitbook/assets/node-setup/windows/20-extract.png)

You should see a new folder on your Desktop.

![Extracted](../.gitbook/assets/node-setup/windows/21-extracted.png)

## 5. Start the Taraxa Node

For starting the actual node software we need to use the PowerShell console.

Click on the start menu and type `PowerShell`.

When the application appears open it.

![Open PowerShell](../.gitbook/assets/node-setup/windows/22-open-powershell.png)

You should see a window similar to this:

![PowerShell Opened](../.gitbook/assets/node-setup/windows/23-powershell-opened.png)

Type the following commands one by one:

```
cd .\Desktop\taraxa-ops-master\scripts\
docker-compose up
```

![Go to Scripts Folder](../.gitbook/assets/node-setup/windows/24-go-to-folder.png)

Now docker is pulling the Taraxa Node image. You should see something similar to this:

![Start the Taraxa Node](../.gitbook/assets/node-setup/windows/25-docker-compose-up.png)

After it finishes pulling the latest version the node will start and you should see something similar to the following:

![Node running](../.gitbook/assets/node-setup/windows/26-node-running.png)

## 6. Update the Taraxa Node

From time to time we will release new versions of the node software. Try to keep it up to date using the following commands:

```
cd .\Desktop\taraxa-ops-master\scripts\
docker-compose stop
docker-compose rm -f
docker-compose pull
docker-compose u
```

![Update node](../.gitbook/assets/node-setup/windows/27-update-node.png)