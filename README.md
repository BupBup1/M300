# M300

## Voraussetzung
    - GitBash
    - SSH-Key
    - TBZ Cloud

### SSH-Key erstellen (lokal)
Die SSH-Keys werden auf dem lokalen Laptop erstellt. Auf Windows muss noch <a href="https://www.w3schools.com">GIT/BASH</a>
installiert werden.<br>

<code>ssh-keygen -t rsa -b 4096 -C "beispiel@beispiel.com"</code>

    - Enter a file in which to save the key (~/.ssh/id_rsa):
    [Press enter]
    - Enter passphrase (empty for no passphrase): [Passwort]
    - Enter same passphrase again: [Passwort wiederholen]

Der Public und Privat Key sind nun in folgendem Verzeichnis gespeichert:<br>
<code>C:\Users\Thomas\.ssh</code>

Public Key kopieren und bei Github hinzufügen. <br>
Github.com -> Profil -> Settings -> SSH und GPG keys -> SSH keys



### Verbindung auf TBZ Cloud

In Gitbash oder CMD lokal folgenden Befehl ausführen:<br>
<code>ssh -i C:\Users\Thomas\.ssh\ssh ubuntu@10.4.43.31</code>

### SSH Zugriff auf TBZ Cloud konfigurieren

Public Key in das File schreiben
echo public_key_string >> ~/.ssh/authorized_keys

Berechtigungen rekursiv ändern
chmod -R go= ~/.ssh

Owner auf eigenen User ändern
chown -R ubuntu:ubuntu ~/.ssh

### Webserver starten

<code>cd M300</code>

<code>vagrant up</code>

### Webserver stoppen

<code>cd M300</code>

<code>vagrant destroy -f</code>

### Weitere Schritte mit Vagrant

https://github.com/ser-cal/M300-Vagrant-Webserver#nginx-webserver-deklarativ-aufsetzen

### 

<code>vagrant global-status</code>

  
### Docker Commands

Zeigt alle verfügbaren Befehle von Docker an<br>
<code>docker image</code>

Container löschen <br>
<code>docker image rm [ID]</code>
<code>docker rmi [ID]</code>

Container stoppen <br>
<code>docker stop</code>

Liste aller laufenden Docker Container
<code>docker ps</code>

Liste aller laufenden und gestoppten Container
<code>docker ps -a</code>


### Debugging

Zeigt alle installierten Layer<br>
<code>docker image inspect [ID]<code>


### Docker

<code>docker pull ubuntu/mysql</code>

<code>docker run -d --name mysql-container -e TZ=UTC -p 30306:3306 -e MYSQL_ROOT_PASSWORD=My:S3cr3t/ ubuntu/mysql:8.0-22.04_beta</code>






