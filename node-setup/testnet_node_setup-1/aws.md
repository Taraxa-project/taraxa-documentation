---
description: Guide for running the Taraxa Node with Docker on Amazon Web Services (AWS)
---

# AWS

## 1. Register to AWS unless you already have Amazon Web Services account

You should create account on Amazon Web Services [https://portal.aws.amazon.com/billing/signup](https://portal.aws.amazon.com/billing/signup)

Please note that account confirmation usually takes about 24 hours

## 2. Create an Access key ID and secret access key

To create access keys for an IAM user:

* Sign in to the AWS Management Console and open the IAM console at [https://console.aws.amazon.com/iam/](https://console.aws.amazon.com/iam/)
* In the navigation pane, choose Users.
* Create new user with `Access type` set to `Programmatic access` or choose the name of the user whose access keys you want to create, and then choose the Security credentials tab.
* In the Access keys section, choose Create access key.
* To view the new access key pair, choose Show. You will not have access to the secret access key again after this dialog box closes. Your credentials will look something like this:

```
  Access key ID: AKIAIOSFODNN7EXAMPLE
  Secret access key: wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY
```

Make a note of that keys. We will use it in the next step.

## 3. Creating a Taraxa Node

{% hint style="danger" %}
If you are running this on Windows you will first need to install Windows Subsystem for Linux. You can use [this guide](https://docs.microsoft.com/en-us/windows/wsl/install-win10).
{% endhint %}

Export your AWS access keys to your environment so that the node creation script can access it without prompting you for it:

```bash
export AWS_ACCESS_KEY_ID=YOUR_ACCESS_KEY_ID
export AWS_SECRET_ACCESS_KEY=YOUR_SECRET_ACCESS_KEY
```

Otherwise, the installation script will ask you for access keys interactively

Then you can download and run the node creation script using this command:

```bash
bash -c "$(curl -fsSL https://raw.githubusercontent.com/Taraxa-project/taraxa-ops/master/scripts/one-click-AWS.sh)"
```

Look carefully at the output of the script, if everything went well, the script will write the AWS region in which the node was deployed, the IP address of the node and the command to connect to the node via SSH.

Now you should see a new server in your [AWS Console](https://console.aws.amazon.com/ec2/v2/home?#Instances) (select the correct region in which your node was deployed).

_NOTE: It takes a few minutes after the droplet starts to install the Taraxa Node software._

## 4. Check the logs

You can use the following commands inside the created server to check if the node is up and running:

```bash
sudo docker ps
sudo docker logs -f taraxa_compose_node_1
```
