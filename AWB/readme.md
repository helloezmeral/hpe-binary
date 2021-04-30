# HPE ECP AWB

https://docs.containerplatform.hpe.com/53/app-workbench-5-1/getting-started/AWB51_Installation.html

```bash
wget https://bluedata-catalog.s3.amazonaws.com/sdk/hpecp-workbench-5.1.tgz
sudo tar xf hpecp-workbench-5.1.tgz

# [root@prod21 AWB5.1]# ls # you will see two file exracted
# bdwb  hpecp-workbench-5.1.tgz  hpecp-workbench-img-5.1.tgz

docker load -i hpecp-workbench-img-5.1.tgz

```

- you will see the binanry, move the binanry to one of your $PATH

```
sudo chmod +x bdwb
sudo cp bdwb /usr/local/bin/
```

# Launch WebUI
```
bdwb --launchui --port 8000
bdwb --stopui
