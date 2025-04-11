# cilisplore

Prosjekt for å sette opp et 3-node kind cluster med cilium CNI, hubble, tetragon, kyverno og headlamp

cilium benyttes som ingress og kube-proxy erstattning.

# Forutsetninger

1. Docker, kind, kubectl, helm og taskfile installert
2. Følgende sysctl-settings satt:
```
fs.inotify.max_user_instances=8192
fs.inotify.max_user_watches=524288
```


# Cilium
Installere cilium cli
```
wget  https://github.com/cilium/cilium-cli/releases/download/v0.18.3/cilium-linux-amd64.tar.gz -O - | tar -zxvf - -C /usr/local/bin
chmod 0755 /usr/local/bin/cilium
```

# Hubble:
Installere hubble cli
```
wget https://github.com/cilium/hubble/releases/download/v1.17.2/hubble-linux-amd64.tar.gz -O -  | tar -zxvf - -C /usr/local/bin
chmod 0755 /usr/local/bin/hubble
```
Url: http://hubble-ui.127.0.0.1.nip.io/

# Headlamp
Url: http://headlamp.127.0.0.1.nip.io/

For å opprette et token for headlamp pålogging:
```
kubectl create token headlamp --namespace kube-system
```

# Tetragon
Installere tetragon cli
```
wget https://github.com/cilium/tetragon/releases/download/v1.4.0/tetra-linux-amd64.tar.gz -O - | tar -zxvf - -C /usr/local/bin
chmod 0755 /usr/local/bin/tetra
```
Ikke noe UI på dette, selve tetragon er installert og kjører, men ingen monitoring eller enforce policy.


# Installasjon:
```
task up
```


# Avinstallasjon
```
task down
```
