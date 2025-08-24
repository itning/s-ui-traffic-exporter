<h3 align="center">s-ui Traffic Exporter</h3>
<div align="center">

[![GitHub stars](https://img.shields.io/github/stars/itning/s-ui-traffic-exporter.svg?style=social&label=Stars)](https://github.com/itning/s-ui-traffic-exporter/stargazers)
[![GitHub forks](https://img.shields.io/github/forks/itning/s-ui-traffic-exporter.svg?style=social&label=Fork)](https://github.com/itning/s-ui-traffic-exporter/network/members)
[![GitHub watchers](https://img.shields.io/github/watchers/itning/s-ui-traffic-exporter.svg?style=social&label=Watch)](https://github.com/itning/s-ui-traffic-exporter/watchers)
[![GitHub followers](https://img.shields.io/github/followers/itning.svg?style=social&label=Follow)](https://github.com/itning?tab=followers)


</div>

<div align="center">

[![GitHub issues](https://img.shields.io/github/issues/itning/s-ui-traffic-exporter.svg)](https://github.com/itning/s-ui-traffic-exporter/issues)
[![GitHub license](https://img.shields.io/github/license/itning/s-ui-traffic-exporter.svg)](https://github.com/itning/s-ui-traffic-exporter/blob/master/LICENSE)
[![GitHub last commit](https://img.shields.io/github/last-commit/itning/s-ui-traffic-exporter.svg)](https://github.com/itning/s-ui-traffic-exporter/commits)
[![GitHub repo size in bytes](https://img.shields.io/github/repo-size/itning/s-ui-traffic-exporter.svg)](https://github.com/itning/s-ui-traffic-exporter)
[![Hits](https://hitcount.itning.com?u=itning&r=s-ui-traffic-exporter)](https://github.com/itning/hit-count)

</div>

---

[中文](https://github.com/itning/s-ui-traffic-exporter/blob/main/README-cn.md)

# Introduction

Function: Report traffic information from s-ui to Prometheus.

Implementation effect:

![](./pic/a.png)

In s-ui:

![](./pic/b.png)

# Usage

```shell
./s-ui-traffic-exporter-linux-amd64 --web.listen-address=":9100" 
```

```text
# HELP name_traffic_download_bytes_total Total bytes downloaded by each name.
# TYPE name_traffic_download_bytes_total counter
name_traffic_download_bytes_total{enable="true",name="zGZuZfFc"} 1.819867959e+09
# HELP name_traffic_upload_bytes_total Total bytes uploaded by each name.
# TYPE name_traffic_upload_bytes_total counter
name_traffic_upload_bytes_total{enable="true",name="zGZuZfFc"} 7.16911518e+08
```

The default location for the s-ui SQLite database is: `/usr/local/s-ui/db/s-ui.db`.

If not in the default location, it can be modified via a parameter, for example: `--db-path=/home/xui.db`.

Supports TLS: `--web.config.file=web-config.yml`.

For specific configuration details: [exporter-toolkit web-configuration](https://github.com/prometheus/exporter-toolkit/blob/master/docs/web-configuration.md).

# Acknowledgments

![JetBrains Logo (Main) logo](https://resources.jetbrains.com/storage/products/company/brand/logos/jb_beam.svg)