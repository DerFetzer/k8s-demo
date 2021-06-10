# k8s-demo

## Voraussetzungen

* minikube >=v1.20.0 (https://minikube.sigs.k8s.io/docs/start/)
* kubectl (https://kubernetes.io/docs/tasks/tools/install-kubectl/)
* [optional] Lens (https://k8slens.dev/)
* [optional] Chocolatey (https://chocolatey.org/docs/installation)

Wer Chocolatey installiert hat, kann alle benötigten Tools mit Hilfe des Scripts `choco_install_requirements.bat` installieren. Ansonsten verweise ich auf die jeweiligen Websites der Tools.

## Vorbereitung

### Minikube Cluster starten

Minikube bietet die Möglichkeit, das Cluster über diverse Driver zu betreiben. Momentan sind das bei mir `virtualbox, vmwarefusion, hyperv, vmware, docker, ssh`. Ich habe mich letztendlich für VirtualBox entschieden, weil es da für mich die wenigsten Probleme gab und man das Cluster ohne ständige Admin-Rechte einrichten und benutzen kann. Die Wahl des Drivers ist aber jedem selbst überlassen.

Das Cluster kann wie folgt gestartet werden:
```
minikube start --driver=<DRIVER>
```
Wobei `<DRIVER>` als Platzhhalter für einen aus der Liste oben steht. Lässt man die Option weg, wird ein Driver automatisch ausgewählt.
Wichtig ist, dass das Cluster mit einer minikube-Version >=v1.20.0 gestartet wird.

Nach ein paar Minuten sollte das Cluster funktionsfähig sein. Ob alles geklappt hat, kann man mit folgendem Befehl überprüfen:
```
kubectl get nodes
```
Das Ergebnis sollte ungefähr so aussehen:
```
NAME       STATUS   ROLES                  AGE   VERSION
minikube   Ready    control-plane,master   10m   v1.20.2
```

### Cluster vorbereiten

Im Anschluss wird mit dem Skript `provision_minikube.bat` das Cluster konfiguriert und benötigte Workloads installiert.