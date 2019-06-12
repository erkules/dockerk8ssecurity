# Security (Laufzeit und Aufruf)

Wir beschäftigen und nur mit
Laufzeit und Aufruf
Kein Netzwerk
Keine Zertifikate
Keine Tenantisolation
Keine Cgroups
Keine Authentifizierung
Keine Secrets
...


# Szenarian

Mounten!
Capabilities/Sudo
Read-Only


# Topics

* Laufzeit
* Aufruf


# Docker

~~~
docker container run --read-only --tm -ti alpine 
docker container run --rm --security-opt=no-new-privileges --user 1000 -ti erkules/ping
docker container run --rm --security-opt apparmor=docker-no-ping -ti alpine
docker container run --rm --security-opt apparmor=docker-bin -ti alpine
~~~



# Etwas Docker Swarm Mode

# K8s

Leider können wir in Docker(auch Swarm Mode)
nicht den Aufruf reglementeiren.

Mounten hat auch ganz andere Szenarien

Secrets/ConfigMaps/HostPath

PodSecurityPolicies
Ermöglichen, dass 





Reste:

Taints/Tolerations
NetworkPolicies
ServiceMesh



# Apparmor

~~~
#/sbin/apparmor_parser --replace --write-cache /etc/apparmor.d/no_raw_net
~~~
