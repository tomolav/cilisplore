# cilisplore

Prosjekt for å sette opp et 3-node kind cluster med cilium CNI, hubble og headlamp

cilium benyttes som ingress og kube-proxy erstattning.

# Forutsetninger

1. Docker, kind, kubectl, helm og taskfile installert
2. Følgende sysctl-settings satt:
```
fs.inotify.max_user_instances=8192
fs.inotify.max_user_watches=524288
```


# Hubble:
Url: http://hubble-ui.127.0.0.1.nip.io/

# Headlamp
Url: http://headlamp.127.0.0.1.nip.io/

For å opprette et token for headlamp pålogging:
```
kubectl create token headlamp --namespace kube-system
```


# Installasjon:
```
task up
```


# Avinstallasjon
```
task down
```
