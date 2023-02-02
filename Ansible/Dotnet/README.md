installing dotnet application
-----------------------------

1. manual steps to intall dotnet application

```
sudo apt-get update
wget https://packages.microsoft.com/config/ubuntu/22.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
rm packages-microsoft-prod.deb
sudo apt-get install -y apt-transport-https aspnetcore-runtime-7.0
sudo apt-get install -y dotnet-sdk-7.0

```
2. dotnet installation web link refer here [refer here](https://learn.microsoft.com/en-us/dotnet/core/install/linux-ubuntu#2204)
3. ansible playbook refer here [refer here](https://github.com/nkishore555/joip_docs_QT/blob/main/Ansible/Dotnet/dotnet_ubu.yml)
4. dotnet version check image refer image ![preview](../images/dotnet1.png)


