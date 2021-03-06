# M300 Wissensstand und Lernfortschritt

## Inhaltsverzeichnis

[Linux](#linux)  
[Virtualisierung](#virtualisierung)  
[Vagrant](#vagrant)  
[Git](#git)  
[LB2](#LB2)  
[ScotchBox](#scotchbox)  
[UFW](#UFW)  
[Proxy](#Proxy)  
[Rechte](#Rechte)  
[SSH](#SSH)  
[Lernfortschritte](#lernfortschritte)  

   
<a name="linux"/>
<a name="virtualisierung"/>
<a name="vagrant"/>
<a name="git"/>
<a name="LB2"/>
<a name="scotchbox"/>
<a name="UFW"/>
<a name="Proxy"/>
<a name="Rechte"/>
<a name="SSH"/>
<a name="lernfortschritte"/>



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

Das ist das Standard Vagrant File, ich habe noch keine Veränderungen daran vorgenommen. Wenn man jetzt mit `vagrant up` in einer Shell den Prozess zum Aufbau einer VM startet, werden alle Informationen, die im Vagrantfile enthalten sind in eine VM des bevorzugten Hypervisors geschrieben. So sieht meine VM auf Virtualbox aus:

![no](https://github.com/dorian1142/M300.3/blob/master/VagrantVM.PNG)

Die VM heisst so wie man den eigenen Ordner benannt hat, indem sich das Vagrantfile befindet. Alle Konfigurationen der VM sind Vagrantfile-Default. Die VM kann Datenverlustfrei wieder per Befehl `vagrant detroy` abgebaut werden. Davor sollte man aber einen `vagrant halt` Befehl absetzen, welcher die VM ausschaltet. Um ein Vagrant fähiges System aufzubauen muss man Vagrant aus dem internet herunterladen, einen Ordner, indem man die Vagrantfiles haben möchte, erstellen und vagrant init ausführen. Vagrant init initiiert (erstellt) ein Vagrantfile. Via SSH kann man auch von ausserhalb auf die VM zugreifen. Um dies zu erreichen, muss man lediglich im Bash den Vagrant Ordner öffnen, `vagrant ssh` absetzen und dann sich anmelden. Voraussetzung ist natürlich, dass die Maschine per `vagrant up` zum Laufen gebracht wurde.

## Git
Git wurde ebenfalls von Linus Torvalds entwickelt. Es ist ein Distributed Version Controlling System. Auf Deutsch: Ein System, auf welchem man die Versionen kontrollieren, verwalten und konfigurieren und anschliessend mit der Welt via Github oder Gitlab teilen kann. Es ist sehr umständlich und kompliziert für Beginner (wie mich z.B.). Um bspw. Github verwenden zu können, benötigt man erstmal einen eigenen Account. Danach kann man auf der Weboberfläche von Github ein Repository erstellen. Mein Repo heisst M300.3.

![no](https://github.com/dorian1142/M300.3/blob/master/gitverlauf.PNG)

Ich habe ein git Repo auf meinem Client lokal erstellt und mit einem `Readme.md` File versehen, sodass ich den Überblick nicht verliere.

![no](https://github.com/dorian1142/M300.3/blob/master/repo.PNG)

Dazu verwende ich fork als Versionsverwaltungsoberfläche. Ich komme mit dem unübersichtlichen Bash nicht so gut klar, deshalb fork.

![no](https://github.com/dorian1142/M300.3/blob/master/fork.PNG)

## LB2
Ich habe das Vagrant File, welches Signor Calisto uns zur Verfügung gestellt hat kopiert und in ein von mir erstelltes Vagrant File eingefügt. Ich musste noch das db.sh File in mein lokales Vagrant repo kopieren, damit das Script einwandfrei ausgeführt werden kann. Schlussendlich habe ich es geschafft, die VM database und webserver zum Laufen zu bringen.

![no](https://github.com/dorian1142/M300.3/blob/master/databasestart.PNG)

Anschliessend habe ich noch den webserver gestartet

![no](https://github.com/dorian1142/M300.3/blob/master/webstart.PNG)

Zum testen ob die Verbindung funktioniert, habe ich lokal im Browser `http://localhost:8080/adminer.php` eingegeben mit den angegebenen Credentials. Jedoch hat das Login nicht auf Anhieb funktioniert, da ich den Namen der Database (der verlangt wird) nicht kannte:

![no](https://github.com/dorian1142/M300.3/blob/master/adminer.PNG)

## ScotchBox
Um diese Maschine bei mir lokal zum Laufen zu bringen musste ich lediglich `vagrant init scotch/box \ --box-version 3.5` und einen `vagrant up` Befehl ausführen.

![no](https://github.com/dorian1142/M300.3/blob/master/scotchbox.PNG)

Davor musste ich noch ein neues lokales Repo erstellen, um dort das neue VagrantFile erstellen zu können. Dies heisst `/ScotchBox` und befindet sich auf meinem `/Desktop`.

## UFW
Die UFW ist eine super easy Firewall, für jeden schnell verständlich. Ich habe die Anleitung von Herrn Rohr so befolgt, dass ich schlussendlich dieses Ergebnis erhalten habe:

![no](https://github.com/dorian1142/M300.3/blob/master/webUFWstatus.PNG)

Zu sehen (oben) sind die aktiven Rules der UFW auf dem Webserver 192.168.55.101.

![no](https://github.com/dorian1142/M300.3/blob/master/dbUFWdelete.PNG)

Hier sind die Rules von der DB VM, es ist nur eine einzige die man im Vorfeld beim Bearbeiten der Anleitung erstellen musste. Danach musste man die Rule wieder löschen.

Hier noch ein curl von meinem lokalen Client auf die Webserver IP:

![no](https://github.com/dorian1142/M300.3/blob/master/curlLocal.PNG)

Ich habe die IP Adresse in Chrome auf meinem Client eingegeben und folgendes erhalten:

![no](https://github.com/dorian1142/M300.3/blob/master/curlLocalGUi.PNG)

## Proxy
Ich habe den Proxy Service heruntergeladen (er war bereits vorinstalliert) & die Folgende Linie in `/etc/apache2/apache2.conf` hinzugefügt: 

![no](https://github.com/dorian1142/M300.3/blob/master/additionallineServerName.PNG)

Danach habe ich noch den Reverseproxy anhand der Anleitung konfiguriert im File `001-reverseproxy.conf`.

![no](https://github.com/dorian1142/M300.3/blob/master/reverseproxya.PNG)

## Rechte
Im Kapitel 25 wird zwar erklärt was Rechte & Privilegien auf UNIX Systemen sind und wie man diese verändert, jedoch habe ich keinen Auftrag gefunden..

## SSH
Den Auftrag SSH habe ich versucht zu erledigen, leider habe ich es nicht wirklich geschafft, den public key auf die database Maschine zu transferieren.

![no](https://github.com/dorian1142/M300.3/blob/master/sshtrynew.PNG)

Auf dem Bild sieht man wie ich versucht habe, den erstellten public key im Verzeichnis /root/.ssh/id_rsa auf die VM database zu kopieren, leider ohne Erfolg.

## Lernfortschritte
Bisher habe ich sehr viel neues gelernt aber auch altes ‚refresht‘. Vagrant war schon 2-3 mal das Thema in der Schule und auch im Basislehrjahr. Dazu gelernt habe ich nicht viel. Ich habe aber in diesem Modul endlich zu 100% verstanden, wie es funktioniert, was vor dem Modul nie der Fall war. Ebenfalls nicht neu aber sehr umständlich ist git. Ich habe git bereits öfters behandelt und auch in der Arbeit oft mit Gitlab gearbeitet. Dort habe ich auch (dank Steve Küng) mit 3.partei Programmen wie Fork gearbeitet. Fork erleichtert die Arbeit wesentlich, da es eine übersichtliche Benutzeroberfläche bietet. Am 11. Juni habe ich noch mehr über Vagrant gelernt und viele AHA Effekte erlebt. Zum Beispiel habe ich das Vagrantfile für den Webserver und DB server bearbeitet. Oder als ich das File `Scotchbox` von der vagrant cloud heruntergeladen und gestartet habe. Ich finde Vagrant ist eine super Sache. Ich hatte zu Beginn Verständnisschwierigkeiten, diese sind jetzt nicht mehr da. Wenn ich jetzt in der Zeit der vorherigen Module zurückschaue, hätte ich mit Vagrant so viel Zeit sparen können... Am 15. Juni habe ich weiter am Auftrag gearbeitet und viel über die UFW gelernt. Sie ist super Handy und ich hätte anfangs des Kapitels 25 nicht gedacht, dass es so easy sein würde. Ich habe die gängigsten Befehle der UFW kennengelernt und angewandt. Ich habe gelernt, wie man einen Proxy und Reverse Proxy auf Ubuntu aufsetzt und wie man das config File richtig verwendet. Anschliessend habe ich mich noch der Literatur des Themas Rechte & Privilegien gewidmet, dort habe ich ebenfalls einige neue Dinge gelernt, jedoch habe ich das meiste davon bereits gekannt/gewusst. Da dort kein Auftrag zu finden war, bin ich mit dem Thema SSH weitergefahren. Beim Thema SSH bin ich nicht sehr weit gekommen. Immerhin habe ich gelernt, wie man per bash einen ssh public key erstellt. Leider funktionierte der Transfer des Keys nicht, weshalb ich zu anderen Hausaufgaben switchte, von denen wir im Moment reichlich zu erledigen haben.

## Vergleich Vorwissen - Wissenszuwachs
In dieser LB habe ich wirklich viel gelernt. Sehr viel, was ich zu 100% auch später in meinem Berufsleben gerne anwenden werde / möchte. Dazu gehört unter anderem endlich ein gutes Verständnis von Vagrant, welches ich vor der LB nicht hatte. Ich hatte immer offene Fragen bezüglich Vagrant, die jetzt alle beantwortet wurden. Im Bereich Git habe ich ebenfalls viel neues dazugelernt. Unter anderem das erstellen dieses Markdowns, das erstellen und initiaten eines Repositorys auf einem Client. Wenn man es beherrscht (wie Marcello gesagt hat) macht es einen heiden Spass zu verwenden und damit zu **_experimentieren_** und herum zu `spielen`. Ich habe Git zwar schon im vorhinein gekannt, jedoch habe ich es nie wirklich ausführlich lernen können. Jetzt hatte ich die Zeit und habe es auch gelernt. Anschliessend habe ich auch noch gelernt, dass man jegliche Scripts aller Arten in ein Vagrantfile einpflegen kann. So bestand ja die LB2 aus der webserver und database vm, wobei die DB vm ein db.sh script beinhaltete mit SQL Inhalt. Das finde ich toll, es öffnet einem milliarden von Möglichkeiten, so viele einzelne Prozesse zusammenhängen und als eines laufen lassen zu können. Vagrant bietet nochmals mehr Vorteile als bereits erwähnt, in der Vagrant Cloud kann man sich von 3. Parteien erstelle Vagrantfiles herunterladen und ausführen, je nach Gusto. So habe ich z.B. einen Lampstack im Nullkomanichts ausführen können ohne komplizierte Downloads der verschiedenen Services. Dieser Lamp Stack heisst ScotchBox und ist frei zugänglich. Ebenfalls (ja ich sage oft ebenfalls und 'ich habe gelernt' in diesem Abschnitt des MDs) habe ich gelernt was die UFW ist und wie man sie anwendet. Jetzt beherrsche ich die einfachsten Befehle wie man die UFW konfigurieren und Ports aktiveren oder Rules löschen kann via Bash. Nachdem ich die UFW durchgenommen habe, habe ich mich dem Thema Proxy gewidmet und meinen Webserver erfolgreich zu einem Proxyserver umgewandelt.