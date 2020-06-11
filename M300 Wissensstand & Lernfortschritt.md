# M300 Wissensstand und Lernfortschritt

## Linux
Linux ist das in Smartphones am meisten verwendete OS neben iOS. Ursprünglich wollte Linus Torvalds Linux ausschliesslich für Desktops entwickeln, was aufgrund der ‚Faulheit‘ der Menschen nie realisiert wurde. Linux ist nicht von Anfang an einfach zu verstehen und es unterscheidet sich grundlegend von Windows. Windows ist bspw. Auf den meisten Desktops und Laptops bereits vorinstalliert, wie macOS. Linux wird an sich nicht bereits auf Geräten vorinstalliert verkauft. Jedoch hat sich Linux im Bereich Server und Smartphone-OS bereits sehr bewährt. Von Linux gibt es etliche Distros, von Ubuntu über Debian bis Kali & Raspi. Diese werden in allen unterschiedlichen Bereichen wie dem Verwalten von Domänen bis zum Ethical Hacking / Penetration testing oder dem Projektunterricht (Raspi) verwendet.

![no](https://github.com/dorian1142/M300.3/blob/master/Linux.PNG)

## Virtualisierung
Virtualisierungsmethoden werden seit längerem verwendet und werden auch bereits abgelöst, da schon effizientere Massnahmen u.A. zum verringern von Energieverbrauch existieren. Die bekanntesten Virtualisierungssoftwares sind: Virtualbox, VMware (ebenfalls ESXi), Hyper-V (Auf allen Windows 10 Pro Geräten bereits vorinstalliert, sofern man Intel VTx aktiviert hat). 

![no](https://github.com/dorian1142/M300.3/blob/master/Hypervisor.PNG)

Auf dem obigen Bild sieht man die Funktionsweise von Virtualisierungsmassnahmen. Auf dem Physischen Gerät wird ein Hypervisor (Hyper-V oder VMware Player z.B.) installiert, auf welchem dann beliebige OS mit beliebig viel Speicherplatz und CPU Rechenleistung aufgesetzt werden können.

## Vagrant
Vagrant ist mit Docker etc. praktisch Virtualisierung 2.0. Es unterscheidet sich nicht gross von der bisher allseits bekannten Virtualisierungsmethode via Hypervisor. Der grösste Unterschied liegt lediglich darin, dass die VM nicht manuell, sondern aus einem vorgefertigten Config-File erstellt wird. Dieses File kann so aussehen:

![no](https://github.com/dorian1142/M300.3/blob/master/vagrant.PNG)

Das ist das Standard Vagrant File, ich habe noch keine Veränderungen daran vorgenommen. Wenn man jetzt mit vagrant up in einer Shell den Prozess zum Aufbau einer VM startet, werden alle Informationen, die im Vagrantfile enthalten sind in eine VM des bevorzugten Hypervisors geschrieben. So sieht meine VM auf Virtualbox aus:

![no](https://github.com/dorian1142/M300.3/blob/master/VagrantVM.PNG)

Die VM heisst so wie man den eigenen Ordner benannt hat, indem sich das Vagrantfile befindet. Alle Konfigurationen der VM sind Vagrantfile-Default. Die VM kann Datenverlustfrei wieder per Befehl vagrant detroy abgebaut werden. Davor sollte man aber einen vagrant halt Befehl absetzen, welcher die VM ausschaltet. Um ein Vagrant fähiges System aufzubauen muss man Vagrant aus dem internet herunterladen, einen Ordner, indem man die Vagrantfiles haben möchte, erstellen und vagrant init ausführen. Vagrant init initiiert (erstellt) ein Vagrantfile. Via SSH kann man auch von ausserhalb auf die VM zugreifen. Um dies zu erreichen, muss man lediglich im Bash den Vagrant Ordner öffnen, vagrant ssh absetzen und dann sich anmelden. Voraussetzung ist natürlich, dass die Maschine per vagrant up zum Laufen gebracht wurde.

## Git
Git wurde ebenfalls von Linus Torvalds entwickelt. Es ist ein Distributed Version Controlling System. Auf Deutsch: Ein System, auf welchem man die Versionen kontrollieren, verwalten und konfigurieren und anschliessend mit der Welt via Github oder Gitlab teilen kann. Es ist sehr umständlich und kompliziert für Beginner (wie mich z.B.). Um bspw. Github verwenden zu können, benötigt man erstmal einen eigenen Account. Danach kann man auf der Weboberfläche von Github ein Repository erstellen. Mein Repo heisst M300.3.

![no](https://github.com/dorian1142/M300.3/blob/master/gitverlauf.PNG)

Ich habe ein git Repo auf meinem Client lokal erstellt und mit einem Readme.md File versehen, sodass ich den Überblick nicht verliere.

![no](https://github.com/dorian1142/M300.3/blob/master/repo.PNG)

Dazu verwende ich fork als Versionsverwaltungsoberfläche. Ich komme mit dem unübersichtlichen Bash nicht so gut klar, deshalb fork.

![no](https://github.com/dorian1142/M300.3/blob/master/fork.PNG)

## Lernfortschritte
Bisher habe ich sehr viel neues gelernt aber auch altes ‚refresht‘. Vagrant war schon 2-3 mal das Thema in der Schule und auch im Basislehrjahr. Dazu gelernt habe ich nicht viel. Ich habe aber in diesem Modul endlich zu 100% verstanden, wie es funktioniert, was vor dem Modul nie der Fall war. Ebenfalls nicht neu aber sehr umständlich ist git. Ich habe git bereits öfters behandelt und auch in der Arbeit oft mit Gitlab gearbeitet. Dort habe ich auch (dank Steve Küng) mit 3.partei Programmen wie Fork gearbeitet. Fork erleichtert die Arbeit wesentlich, da es eine übersichtliche Benutzeroberfläche bietet. Das sind all meine bisherigen Lernfortschritte.