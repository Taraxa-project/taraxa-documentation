---
description: Guide for running the Taraxa Node with Docker on Windows
---

# Windows

{% hint style="info" %}
These instructions are specific to Windows. Instructions are also available for [Mac](broken-reference) and [Linux](broken-reference).
{% endhint %}

## 1. Install Docker

Before running the node we need to install Docker.

You can download Docker Desktop for Windows from [here](https://desktop.docker.com/win/stable/amd64/Docker%20Desktop%20Installer.exe).

![Download Docker](<../../.gitbook/assets/1-download (1).png>)

After the download finishes you will find the executable file in your downloads folder.

![Downloaded Docker](<../../.gitbook/assets/2-downloaded (1).png>)

Open `Docker Desktop Installer.exe`. and you should see a screen similar to this:

![Open Docker](<../../.gitbook/assets/3-open (1).png>)

Press "Ok" and don't uncheck any of the default options.

Now Docker is installing:

![Install Docker](<../../.gitbook/assets/4-install (1).png>)

After the installation is finished you can click the "Close" button and Docker is going to start automatically.

![Docker Installed](../../.gitbook/assets/5-installed.png)

## 2. Install WSL 2

Docker needs to install extra dependencies for running Linux containers on Windows.

You will get a notice similar to the one below.

_NOTE: Don't close the notice window_

If you click on the provided link a new browser window will open and we can download the dependency.

![WSL Notice](../../.gitbook/assets/6-wsl-notice.png)

Click on the link under "Download the latest package"

![Download WSL 2](../../.gitbook/assets/7-wsl-download.png)

You can find the executable in your downloads folder.

![WSL 2 Downloaded](../../.gitbook/assets/8-wsl-downloaded.png)

Open the executable and click "Next" on the first screen.

![Install WSL 2](../../.gitbook/assets/9-wsl-install.png)

After the setup is complete click the "Finish" button.

![WSL 2 Installed](../../.gitbook/assets/10-wsl-finish.png)

Now you can click the "Restart" button on the original notice window.

![Restart WSL 2](../../.gitbook/assets/11-wsl-restart.png)

## 3. Starting Docker Desktop

If everything went well you will see the following message.

![Docker Desktop is starting notification](../../.gitbook/assets/12-docker-stating.png)

And if you open the Docker Desktop application you should see the following window.

![Docker Desktop App is starting](../../.gitbook/assets/13-docker-starting-2.png)

When Docker Desktop starts successfuly you will see the yellow icon turn green.

![Docker Desktop Started](../../.gitbook/assets/14-docker-started.png)

## 4. Download Taraxa scripts

In order to run the node we need a set of scripts. You can download the scripts from [this link](https://github.com/Taraxa-project/taraxa-ops).

![Download Taraxa Scripts](../../.gitbook/assets/15-download-scripts.png)

{% hint style="danger" %}
GitHub is blocked in some countries. If you can't access the previous link please refer to the [GitHub is blocked](https://docs.taraxa.io/node-setup/testnet\_node\_setup/github\_blocked) document.
{% endhint %}

Click on "Download ZIP" under the "Code" menu and the download should start.

After the download is complete you can find a new zip file in your downloads folder.

Right click on the file and select the "Extract All" option.

![Extract Scripts](../../.gitbook/assets/17-open-extract-scripts.png)

In the first screen click the "Browse" button.

![Extract Browse](../../.gitbook/assets/18-extract-scripts.png)

Now select "Desktop" from the left menu.

![Select Desktop](../../.gitbook/assets/19-extract-scripts-desktop.png)

And finally click the "Extract" button.

![Extract](../../.gitbook/assets/20-extract.png)

You should see a new folder on your Desktop.

![Extracted](../../.gitbook/assets/21-extracted.png)

## 5. Start the Taraxa Node

For starting the actual node software we need to use the PowerShell console.

Click on the start menu and type `PowerShell`.

When the application appears open it.

![Open PowerShell](../../.gitbook/assets/22-open-powershell.png)

You should see a window similar to this:

![PowerShell Opened](../../.gitbook/assets/23-powershell-opened.png)

Type the following commands one by one:

```bash
cd .\Desktop\taraxa-ops-master\taraxa_compose\
docker-compose up -d
docker-compose logs -f
```

![Go to Scripts Folder](../../.gitbook/assets/24-go-to-folder.png)

Now docker is pulling the Taraxa Node image. You should see something similar to this:

![Start the Taraxa Node](../../.gitbook/assets/25-docker-compose-up.png)

After it finishes pulling the latest version the node will start and you should see something similar to the following:

![Node running](../../.gitbook/assets/26-node-running.png)

\_NOTE: You can press `CTRL` + `C` to stop displaying the logs

## 6. Update the Taraxa Node

From time to time we will announce software updates and breaking protocol changes to the testnet via the #node-operations channel in our [Taraxa community Discord](https://discord.com/invite/WaXnwUb), Telegram channel and Twitter account.

{% content-ref url="../upgrade-a-node/" %}
[upgrade-a-node](../upgrade-a-node/)
{% endcontent-ref %}
