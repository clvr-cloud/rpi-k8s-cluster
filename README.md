## Downloads the Flash tool

```bash
sudo curl -L "https://github.com/hypriot/flash/releases/download/2.7.2/flash" -o /usr/local/bin/flash
sudo chmod +x /usr/local/bin/flash
```
## Downloads the k3sup tool

```bash
curl https://github.com/alexellis/k3sup/releases/download/0.12.3/k3sup-darwin-arm64
chmod +x k3sup-darwin-arm64
```

## Download and extract the ubuntu image


## Flash
```bash
flash -F cmdline.txt --userdata ssd01.yml ubuntu-22.04.1-preinstalled-server-arm64+raspi.img
```

k3sup-darwin-arm64 -F cmdline.txt --userdata ssd01.yml ubuntu-22.04.1-preinstalled-server-arm64+raspi.img


## Provision
export SSD01=192.168.4.56  (Master)

./k3sup install --ip $SSD01 --user clvr-user --cluster
<!-- ./k3sup join --ip $SSD02 --user clvr-user --server-user clvr-user --server-ip $SSD01 --server 
./k3sup join --ip $SSD03 --user clvr-user --server-user clvr-user --server-ip $SSD01 --server 
./k3sup join --ip $SSD04 --user clvr-user --server-ip $SSD01
./k3sup join --ip $SSD05 --user clvr-user --server-ip $SSD01
./k3sup join --ip $SSD06 --user clvr-user --server-ip $SSD01
./k3sup join --ip $SSD07 --user clvr-user --server-ip $SSD01 -->