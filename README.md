# RPI-K8S-Cluster

[![Slack](https://slack.clvr.cloud/badge.svg)](https://slack.clvr.cloud)

Provisioning scripts for the Kubernetes Cluster using RPIs


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

## Provision
```bash
export SSD01=192.168.4.56  (Master)
./k3sup-darwin-arm64 install --ip $SSD01 --user clvr-user --cluster
./k3sup join --ip $SSD02 --user clvr-user --server-user clvr-user --server-ip $SSD01 --server 
./k3sup join --ip $SSD03 --user clvr-user --server-user clvr-user --server-ip $SSD01 --server 
./k3sup join --ip $SSD04 --user clvr-user --server-ip $SSD01
./k3sup join --ip $SSD05 --user clvr-user --server-ip $SSD01
./k3sup join --ip $SSD06 --user clvr-user --server-ip $SSD01
./k3sup join --ip $SSD07 --user clvr-user --server-ip $SSD01
```

## Contribute

We would be happy to accept PRs! If you want to work on something, it'd be good to talk beforehand to make sure nobody else is working on it. You can reach us [on slack](https://slack.clvr.cloud), or in the [issues section](https://github.com/clvr-cloud/rpi-k8s-cluster/issues).

If you want to code but don't know where to start, check out the issues labelled ["help wanted"](https://github.com/clvr-cloud/rpi-k8s-cluster/issues?q=is%3Aopen+is%3Aissue+label%3A%22help+wanted%22+sort%3Areactions-%2B1-desc).

Please note that all interactions in [@clvr-cloud](https://github.com/clvr-cloud) fall under our [Code of Conduct](CODE_OF_CONDUCT.md).

## License

[MIT](LICENSE) © 2019 CLVR Cloud Ltd