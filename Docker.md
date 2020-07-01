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

![no](https://github.com/dorian1142/M300.3/blob/master/dockerrun.PNG)

- `docker rm 'name'` - Löscht Container (Bei Name muss die Container ID eingegeben werden)

![no](https://github.com/dorian1142/M300.3/blob/master/dockerrm.PNG)

Bei einer erfolgreichen Ausführung wird die Container ID ausgegeben.

- `docker-compose` - Um 2 Container zusammenarbeiten lassen zu können
Ein `dockercompose.yml` File ist essentiell bei der Ausführung des Befehls, da im .yml File die nötigen Informationen zur Komposition notiert sind.

## Start
Zu Beginn hatte ich grosse Schwiwerigkeiten mit Docker. Ich verstand die Befehle nicht wirklich und wusste nicht was genau im Hintergrund nach der Ausführung eines Docker-Befehls geschah. Danach habe ich mich ein wenig auf Youtube umgesehen und selbst herumexperimentiert (u.A. mit der Docker Desktop Applikation).

Danach habe ich meine ersten Versuche gestartet:

![no](https://github.com/dorian1142/M300.3/blob/master/dockerfirsttry.PNG)

## LB3
Als LB3 habe ich einen kleinen LAMP Stack ausgewählt. Dieser war nicht in der Beispielliste zu finden. Ich habe mich von einem kleinen Tutorial inspirieren lassen.

Als erstes musste ich einen Folder erstellen, wo all die Docker Dateien darin gespeichert werden. Diesen Ordner habe ich `Docker` genannt, er befindet sich auf meinem Desktop.

![no](https://github.com/dorian1142/M300.3/blob/master/dockerinhalt.PNG)

Dazu habe ich das nötige `html` directory erstellt (auf dem Bild ersichtlich). 

Anschliessend habe ich den `php-apache` Ordner erstellt, indem sich auch das dazugehörige Dockerfile befindet, da `php-apache` als Apache-Webserver dienen wird. Das gleiche habe ich mit dem Ordner `mariadb` gemacht.

Gleich danach habe ich das `index.php` File in den Ordner `html` geschrieben.

Anschliessend habe ich dasselbe mit dem MariaDB Container gemacht und die beiden im `compose.yml` File zusammengefasst.
Um das Kompilieren erfolgreich durchzuführen muss man den Befehl `docker-compose up` ausführen. 

Damit ich die volle 'Wirkung' des LAMP Stacks demonstrieren kann, habe ich noch eine kleine DB aufgebaut und eine Tabelle erstellt.
Diese habe ich ins File `index.php` mit anderem html-Code einfliessen lassen, um folgendes Ergebnis zu erhalten:



