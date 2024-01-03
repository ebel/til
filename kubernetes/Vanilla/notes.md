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
### Deployment troubleshooting
* `k -n application1 get deploy`
* `k -n application1 logs deploy/api`
* `k -n application1 describe deploy api`
* `k -n application1 get cm`
* You can also describe pod associated to deployment and look at errors of bottom.

### Error Messages relating to API Server
* `stderr F Error: unknown flag: --this-is-very-wrong`
  * Bad api server manifest value - cmd
* `"transport: Error while dialing dial tcp: address this-is-very-wrong: missing port in address". Reconnecting...`
  * etcd bad etcd server value
* `"Could not process manifest file" err="/etc/kubernetes/manifests/kube-apiserver.yaml: couldn't parse as pod(Object 'apiVersion' is missing in`
  * apiVersion line is malformed.
* `Error while dialing dial tcp 127.0.0.1:23000: connect:connection refused`
  * Port on `--etcd-servers=` is wrong. should be `2379`

### Check deployments logs
* `k -n management logs deploy/<deployment-name> -c <container-name> >> /root/logs.log`

### Misc
* Use kubectl -h for command line examples
* 