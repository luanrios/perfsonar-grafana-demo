# perfsonar-grafana-demo

## VM specs

| Spec | Value |
| --- | --- |
| OS | CentOS 7 |
| RAM | 4096 MB |

## Pre-Installation

1. Clone code
```bash
yum install git -y
git clone https://github.com/luanrios/perfsonar-grafana-demo.git
cd perfsonar-grafana-demo
```

2. Copy Grafana repo
```bash
cp grafana.repo /etc/yum.repos.d/grafana.repo
```

## Installation

1. Grafana
```bash
yum update -y
yum install grafana -y
```

2. Auth
```bash
pass=$(cat /etc/perfsonar/elastic/auth_setup.out | grep admin | cut -d " " -f 2)
sed 's/password: \'\'/password: \'$pass\'/g' datasources.yml
```

3. Datasources
```bash
cp datasources.yml /etc/grafana/provisioning/datasources
chown grafana:grafana /etc/grafana/provisioning/datasources/datasources.yml
```

4. Dashboards
```bash
cp dashboard-providers.yml /etc/grafana/provisioning/dashboards
chown grafana:grafana /etc/grafana/provisioning/dashboards/dashboard-providers.yml
cp -r dashboards /var/lib/grafana
chown -R grafana:grafana /var/lib/grafana/dashboards
```
