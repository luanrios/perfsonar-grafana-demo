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
