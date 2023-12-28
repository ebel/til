### kubectl commands
* `watch crictl ps`
* `journctl`
* `crictl ps` + `crictl logs`
* `docker ps` + `docker logs`
* `journalctl | grep apiserver`
* `cat /var/log/syslog | grep apiserver`
### Locations to remember
* `/etc/kubernetes/manifests/kube-apiserver.yaml`
* `/var/log/pods`
* `/var/logs/comtainers`
* `var/log/syslog`

### Error Messages relating to API Server
* `stderr F Error: unknown flag: --this-is-very-wrong`
  * Bad api server manifest value - cmd
* `"transport: Error while dialing dial tcp: address this-is-very-wrong: missing port in address". Reconnecting...`
  * etcd bad etcd server value
* 
