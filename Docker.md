# Docker

## Inhaltsverzeichnis

[Docker](#docker)  
[Start](#start)  
[LB3](#LB3)  


<a name="Docker"/>
<a name="start"/>
<a name="LB3"/>

## Docker
Was ist Docker?
Docker ist wie Vagrant. Mit Docker kann man Containerweise Betriebssysteme / Applikationen parallel zueinander laufen lassen. Ebenfalls kann man mit `docker-compose` anhand eines `.yml` Files zwei Container miteinander verbinden und zusammenarbeiten lassen. Docker ist sehr ressourceneffizient.

Die gängigsten Docker Befehle (welche ich verwenden musste) wären folgende:

- `docker run 'name'` - erstellt einen Container
- `docker ps -a` - Zeigt laufende Container und die dazugehörigen Informationen wie ID, Image etc.