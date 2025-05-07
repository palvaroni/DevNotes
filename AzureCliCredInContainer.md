To use Azure CLI credentials for authentication in a Docker container open a WSL terminal and run:
```
cd /mnt/c/users/<your-username>
mkdir .azure-for-docker
AZURE_CONFIG_DIR=./.azure-for-docker az login
```
Then mount the created directory into container.

Reference: https://endjin.com/blog/2022/09/using-azcli-authentication-within-local-containers
