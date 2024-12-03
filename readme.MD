Reference: https://prometheus.io/download/
# Prometheus

* move to /opt directory
```
wget https://github.com/prometheus/prometheus/releases/download/v3.0.1/prometheus-3.0.1.linux-amd64.tar.gz
```

* Extract tar file
```
tar -xf prometheus-3.0.1.linux-amd64.tar.gz
```

* Rename if required

```
mv prometheus-3.0.1.linux-amd64 prometheus
```

* Create systemctl service
```
vim /etc/systemd/system/prometheus.service
```

* Enter below info
```
[Unit]
Description=Prometheus Server

[Service]
ExecStart=/opt/prometheus/prometheus --config.file=/opt/prometheus/prometheus.yml

[Install]
WantedBy=multi-user.target
```

```
systemctl start prometheus
```
```
systemctl enable prometheus
````

# node_exporter

* move to /opt directory
```
wget https://github.com/prometheus/node_exporter/releases/download/v1.8.2/node_exporter-1.8.2.linux-amd64.tar.gz
```

* Extract tar file
```
tar -xf node_exporter-1.8.2.linux-amd64.tar.gz
```

* Rename if required
```
mv node_exporter-1.8.2.linux-amd64 node_exporter
```

* Create systemctl service
```
vim /etc/systemd/system/node_exporter.service
```

* Enter below info
```
[Unit]
Description=Node Exporter

[Service]
ExecStart=/opt/node_exporter/node_exporter

[Install]
WantedBy=multi-user.target
```

```
systemctl start node_exporter
```
```
systemctl enable node_exporter
```

Reference: https://grafana.com/docs/grafana/latest/setup-grafana/installation/redhat-rhel-fedora/

# grafana

* move to /opt directory
```
curl -o gpg.key https://rpm.grafana.com/gpg.key
```

* import 
```
sudo rpm --import gpg.key
```

* Create repo
```
vim /etc/yum.repos.d/grafana.repo
```

* Enter below info
```
[grafana]
name=grafana
baseurl=https://rpm.grafana.com
repo_gpgcheck=1
enabled=1
gpgcheck=1
gpgkey=https://rpm.grafana.com/gpg.key
sslverify=1
sslcacert=/etc/pki/tls/certs/ca-bundle.crt
```
* install grafana
```
sudo dnf install grafana -y
```
 systemctl daemon-reload
```
systemctl start grafana-server
```
systemctl enable  grafana-server
```

Reference: https://prometheus.io/download/

# alertmanager
```
* move to /opt directory
```
wget https://github.com/prometheus/alertmanager/releases/download/v0.28.0-rc.0/alertmanager-0.28.0-rc.0.linux-amd64.tar.gz










