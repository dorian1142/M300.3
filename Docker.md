# Docker

## Inhaltsverzeichnis

[Docker](#docker)  
[Start](#start)  
[LB3](#LB3)  
[Sicherheitsaspekte](#Sicherheitsaspekte)  
[Vergleich](#Vergleich)  
[Reflexion](#Reflexion)  


<a name="Docker"/>
<a name="start"/>
<a name="LB3"/>
<a name="Sicherheitsaspekte"/>
<a name="Vergleich"/>
<a name="Reflexion"/>



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

So sah das Ganze dann auf Docker Desktop aus:

![no](https://github.com/dorian1142/M300.3/blob/master/dockerdesktop.PNG)

Damit ich die volle 'Wirkung' des LAMP Stacks demonstrieren kann, habe ich noch eine kleine DB aufgebaut und eine Tabelle erstellt.
Diese habe ich ins File `index.php` mit anderem html-Code einfliessen lassen, um folgendes Ergebnis zu erhalten:

![no](https://github.com/dorian1142/M300.3/blob/master/site.PNG)

Anscheinend hat es funktioniert :)

## Sicherheitsaspekte
Ich habe mich im KAP35 über die Sicherheitsaspekte schlau gemacht und einige Commands in meinem Git Bash getestet:

![no](https://github.com/dorian1142/M300.3/blob/master/kap35.PNG)

Mehr habe ich nicht ausgeführt. Ich habe mich jedoch noch über weitere Möglichkeiten zur Containerabsicherung schlau gemacht. Dabei sind Begriffe wie z.B. `Least Privilege` gefallen. Das bedeutet soviel wie dass man möglichst wenig Rechte möglichst wenig Usern vergibt um die Sicherheit gewährleisten zu können.

## Vergleich
Vor der LB3 habe ich absolut nichts über Docker gewusst. Jetzt kenne ich die grundlegenden Aspekte von Docker. Das bedeutet ich kenne die Basic-Commands wie man
z.B. Container erstellt, löscht oder auflistet. Ebenfalls habe ich gelernt, wie man 2 Container composet. Das ist natürlich auch mit mehr als 2 Maschinen möglich. Dazu habe ich noch die Funktionsweise von Docker noch mehrere Male angeschaut, da ich nicht wirklich den Durchblick (wie bei Vagrant) hatte. Ich habe mich auch erneut intensiv mit der SQL und PHP Technologie auseinandergesetzt. Dies hat mir den Aufbau des LAMP Stack erst ermöglicht. Ich habe dazu natürlich mehrere kleine Anleitungen angeschaut. Nach der LB3 habe ich mich noch den Sicherheitsaspekten gewidmet. Dabei habe ich viele commands und Möglichkeiten zur verbesserten Absicherung von Containern erfahren und gelernt.

## Reflexion
Docker ist sehr interessant, wenn man es erst versteht. Es hat mir viel Kopfzerbrechen bereitet, da es eine ganz andere Technologie ist, als ich mir bisher gewohnt war. Erst mal ein wenig im Thema Docker, versteht man rasch die Basics. Es hat mir Spass gemacht, obwohl es mir verdammt viel Zeit geraubt hat (Ich war täglich mindestens eine Stunde nach der Arbeit noch an der LB3). Durch die LB3 habe ich Einblicke in Docker und ebenfalls einen Refresh im Thema SQL und PHP erhalten. SQL und PHP mag ich sehr, auch wenn sie kompliziert sein können, wenn man alles zusammen agieren lassen möchte. Ich finde Vagrant einen Tick einfacher zu verstehen und umzusetzen, deshalb finde ich Vagrant auch angenehmer. Das gesamte Modul fand ich quantitativ gesehen zu gross. Ich musste täglich an den Kompetenzen arbeiten und habe es trotzdem nicht ganz geschafft. Ich hoffe es ist möglich für nächste Klassen einen etwas reduzierteren Plan zu erstellen.