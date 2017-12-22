# Openstack collectd plugin
This Openstack collectd plugin is designed to work with SignalFx. It uses the Openstack Identity v3 API and Nova v2.1 API to gather metrics.

### Proxy Information:
Since this plugin will most-likely make calls to internal servers, please make sure to properly configure no_proxy settings.
```
On CentOS/RHEL: /etc/sysconfig/collectd
On Debian/Ubuntu: /etc/default/collectd
```

### Sample contents of the file:
```
export no_proxy='<IP address, hostnames, or domains to whitelist>'
```

More info: https://www.gnu.org/software/wget/manual/html_node/Proxies.html

### Configuration:
Please take a look at the 10-openstack.conf file for an example. These are the configuration items:

```
Username "<username>"
Password "<password>"
ProjectName "<project/tenant name to montor>"
ProjectDomainId "<project domain>"
UserDomainId "<user domain (usually same as project domain)>"
AuthURL "<URL to Keystone v3 API server>"
```

### Hypervisor Metrics (need to add metric definitions and units):
```
gauge.openstack.nova.hypervisor.current_workload
gauge.openstack.nova.hypervisor.disk_available_least
gauge.openstack.nova.hypervisor.free_disk_gb
gauge.openstack.nova.hypervisor.free_ram_mb
gauge.openstack.nova.hypervisor.local_gb
gauge.openstack.nova.hypervisor.local_gb_used
gauge.openstack.nova.hypervisor.memory_mb
gauge.openstack.nova.hypervisor.memory_mb_used
gauge.openstack.nova.hypervisor.running_vms
gauge.openstack.nova.hypervisor.vcpus
gauge.openstack.nova.hypervisor.vcpus_used
gauge.openstack.nova.hypervisor.load_average_1m
gauge.openstack.nova.hypervisor.load_average_5m
gauge.openstack.nova.hypervisor.load_average_15m
```

### Instance Metrics (need to add metric definitions and units):
```
gauge.openstack.nova.server.memory
gauge.openstack.nova.server.memory-actual
gauge.openstack.nova.server.memory-rss
gauge.openstack.nova.server.vda_errors
gauge.openstack.nova.server.vda_read
gauge.openstack.nova.server.vda_read_req
gauge.openstack.nova.server.vda_write
gauge.openstack.nova.server.vda_write_req
gauge.openstack.nova.server.hdd_read
gauge.openstack.nova.server.hdd_write
gauge.openstack.nova.server.hdd_errors
gauge.openstack.nova.server.hdd_read_req
gauge.openstack.nova.server.hdd_write_req
gauge.openstack.nova.server.rx
gauge.openstack.nova.server.rx_drop
gauge.openstack.nova.server.rx_packets
gauge.openstack.nova.server.tx
gauge.openstack.nova.server.tx_drop
gauge.openstack.nova.server.tx_packets
```

### Limit Metrics (need to add metric definitions and units):
```
gauge.openstack.nova.limit.maxImageMeta
gauge.openstack.nova.limit.maxPersonality
gauge.openstack.nova.limit.maxPersonalitySize
gauge.openstack.nova.limit.maxSecurityGroupRules
gauge.openstack.nova.limit.maxSecurityGroups
gauge.openstack.nova.limit.totalSecurityGroupsUsed
gauge.openstack.nova.limit.maxServerGroupMembers
gauge.openstack.nova.limit.maxServerGroups
gauge.openstack.nova.limit.totalServerGroupsUsed
gauge.openstack.nova.limit.maxServerMeta
gauge.openstack.nova.limit.maxTotalCores
gauge.openstack.nova.limit.totalCoresUsed
gauge.openstack.nova.limit.maxTotalFloatingIps
gauge.openstack.nova.limit.totalFloatingIpsUsed
gauge.openstack.nova.limit.maxTotalInstances
gauge.openstack.nova.limit.totalInstancesUsed
gauge.openstack.nova.limit.maxTotalKeypairs
gauge.openstack.nova.limit.maxTotalRAMSize
gauge.openstack.nova.limit.totalRAMUsed
```

Original Author: Igor Marchenko (igor@signalfx.com)
# openstackplugin
