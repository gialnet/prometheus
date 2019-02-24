# prometheus
Install and configure Prometheus

>Node Exporter: Install and Config Ubuntu

sudo useradd node_exporter -s /sbin/nologin

wget https://github.com/prometheus/node_exporter/releases/download/v0.17.0/node_exporter-0.17.0.linux-amd64.tar.gz

tar xvf v0.17.0/node_exporter-0.17.0.linux-amd64.tar.gz

sudo cp node_exporter-0.17.0.linux-amd64/node_exporter /usr/sbin/

Create a systemd service file /etc/systemd/system/node_exporter.service

```
[Unit]
Description=Node Exporter

[Service]
User=node_exporter
EnvironmentFile=/etc/sysconfig/node_exporter
ExecStart=/usr/sbin/node_exporter $OPTIONS

[Install]
WantedBy=multi-user.target
```
