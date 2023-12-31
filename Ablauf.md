# Projekt_Wetterstation 
Wetterstation Projekt mit einem Raspberry pi und einem Touch Display. Eine gewisse anzahl an Sensoren haben wir schon, die wir mit an der Hardware verbauen werden. 

- Zu allerest haben wir die SD Karte von dem Raspberry pi in ein Laptop gesteckt und auf diese dann das Betriebssystem für den pi installiert.
- anschließend OpenHub installiert ....
- .....
- .....
- Claudio führt dies fort!!



Lars hat folgendes schon erledigt: 
- SSH auf dem Raspberry Pi installieren
Öffnen Sie dazu am Raspberry Pi ein Terminal und geben Sie diesen Befehl ein:sudo apt-get install sshNun müssen Sie den SSH-Server nur noch starten. Dazu geben Sie diesen Befehl ein:sudo /etc/init.d/ssh startDamit Sie den SSH-Server nicht jedes Mal manuell starten müssen, können Sie ihn auch automatisch beim Booten aufrufen. Dazu geben Sie den folgenden Befehl in das Linux-Terminal ein:sudo update-rc.d ssh defaultsAb sofort ist der Raspberry Pi dauerhaft für den SSH-Zugriff gerüstet.


https://www.openhab.org/docs/installation/linux.html#installation

Apt Based Systems
First, add the openHAB repository key to your package manager (note /usr/share/keyrings may already exist):


curl -fsSL "https://openhab.jfrog.io/artifactory/api/gpg/key/public" | gpg --dearmor > openhab.gpg
sudo mkdir /usr/share/keyrings
sudo mv openhab.gpg /usr/share/keyrings
sudo chmod u=rw,g=r,o=r /usr/share/keyrings/openhab.gpg

danach das Stable Realse: 

echo 'deb [signed-by=/usr/share/keyrings/openhab.gpg] https://openhab.jfrog.io/artifactory/openhab-linuxpkg stable main' | sudo tee /etc/apt/sources.list.d/openhab.list

danach den package index über den Befehl:
sudo apt-get update

dann openhab installiert mit dem Befehl:
sudo apt-get install openhab

anschließend die add-on installieren: 
sudo apt-get install openhab-addons

danach: 
 Please use the following commands to launch openHAB on a system restar                                                                                                                                                                                                                                             t.
            sudo /bin/systemctl daemon-reload
            sudo /bin/systemctl enable openhab.service

[openHAB] You can start openHAB manually by executing the command:
            sudo /bin/systemctl start openhab.service



![image](https://github.com/Lars-h98/Projekt_Wetterstation/assets/142094346/2d43cd5a-6109-4fa3-8282-8c02ca32d313)


Hier eine Andere Anleitung zur installtion von Openhab: 
https://phenx.de/openhab-3-auf-raspberry-installieren-openhabian/

Diese habe ich dann angewendet! 
Ja, Sie können OpenHAB auf einer SD-Karte, auf der bereits ein Linux-Betriebssystem installiert ist (z. B. Raspbian für Raspberry Pi), mithilfe von Etcher flashen. Etcher ist ein Werkzeug zur Erstellung von bootfähigen SD-Karten und kann auch verwendet werden, um OpenHAB auf die SD-Karte zu schreiben. Hier ist, wie Sie dies tun können:

1. **Laden Sie OpenHAB herunter**:
   Gehen Sie auf die offizielle OpenHAB-Website (https://www.openhab.org/download/) und laden Sie die für Ihre Raspberry Pi-Version geeignete OpenHAB-Version herunter. Stellen Sie sicher, dass Sie die richtige Version für Ihren Raspberry Pi-Typ auswählen.

2. **Laden Sie Etcher herunter**:
   Gehen Sie auf die Etcher-Website (https://www.balena.io/etcher/) und laden Sie Etcher herunter und installieren Sie es auf Ihrem Computer.

3. **Stecken Sie die SD-Karte ein**:
   Stecken Sie die SD-Karte in Ihren Computer ein, auf der bereits das Linux-Betriebssystem installiert ist. Stellen Sie sicher, dass Sie alle wichtigen Daten auf der SD-Karte gesichert haben, da der folgende Schritt die Karte formatiert.

4. **Öffnen Sie Etcher**:
   Starten Sie Etcher auf Ihrem Computer.

5. **Wählen Sie das OpenHAB-Image aus**:
   Klicken Sie auf die Schaltfläche "Select Image" in Etcher und wählen Sie das zuvor heruntergeladene OpenHAB-Image aus.

6. **Wählen Sie das Ziellaufwerk aus**:
   Klicken Sie auf "Select Target" und wählen Sie Ihre SD-Karte als Ziellaufwerk aus. Stellen Sie sicher, dass Sie das richtige Laufwerk auswählen, da es formatiert wird.

7. **Schreiben Sie das Image**:
   Klicken Sie auf "Flash", um das OpenHAB-Image auf die SD-Karte zu schreiben. Etcher wird den Schreibvorgang durchführen. Dies kann einige Minuten dauern.

8. **Abschließen**:
   Sobald der Schreibvorgang abgeschlossen ist, entfernen Sie die SD-Karte sicher von Ihrem Computer.

Jetzt sollte Ihre SD-Karte OpenHAB und das Betriebssystem enthalten. Legen Sie die SD-Karte in Ihren Raspberry Pi ein und starten Sie ihn. Beachten Sie, dass Sie möglicherweise noch einige Konfigurationsschritte durchführen müssen, um OpenHAB zu initialisieren und einzurichten, abhängig von den Anforderungen Ihrer Anwendung. Bitte folgen Sie den offiziellen OpenHAB-Dokumentationen für weitere Anleitungen zur Konfiguration.



Anmeldedaten - Raspberry pi :
openhabian
openhabian


Anmeldedaten openhab: 
Projekt
Start123!

![image](https://github.com/Lars-h98/Projekt_Wetterstation/assets/142094346/683b5d4a-8957-45af-8567-16dd503a083c)


Anleitung zur installation für eine Maria DB Datenbank 

Natürlich, hier ist eine Schritt-für-Schritt-Anleitung, wie du MariaDB auf deinem Raspberry Pi 4 installieren kannst, auf dem bereits openHAB installiert ist.

1. **Aktualisiere deine Paketliste**

Zunächst solltest du deine Paketliste aktualisieren, um sicherzustellen, dass du die neueste Version von MariaDB installierst. Du kannst dies tun, indem du den folgenden Befehl in der Kommandozeile eingibst:

```bash
sudo apt update
```

2. **Installiere MariaDB**

Verwende den folgenden Befehl, um MariaDB zu installieren:

```bash
sudo apt install mariadb-server
```

Während der Installation wirst du aufgefordert, ein Passwort für den MariaDB-Root-Benutzer einzugeben. Stelle sicher, dass du dich an dieses Passwort erinnerst, denn du wirst es später brauchen.

3. **Sichere deine MariaDB-Installation**

Nach der Installation von MariaDB solltest du ein Skript namens `mysql_secure_installation` ausführen, das einige sicherheitsrelevante Einstellungen vornimmt. Du kannst das Skript mit dem folgenden Befehl starten:

```bash
sudo mysql_secure_installation
```

Folge den Anweisungen auf dem Bildschirm. Es wird empfohlen, alle vorgeschlagenen Sicherheitsmaßnahmen zu akzeptieren.

4. **Erstelle eine Datenbank und einen Benutzer für openHAB**

Nach der Sicherung deiner MariaDB-Installation solltest du eine Datenbank und einen Benutzer für openHAB erstellen. Du kannst dies tun, indem du die MariaDB-Shell mit dem folgenden Befehl startest:

```bash
sudo mysql -u root -p
```

Gib das Passwort ein, das du während der MariaDB-Installation festgelegt hast. 

Erstelle dann die Datenbank und den Benutzer mit den folgenden Befehlen (ersetze `your_password` durch ein sicheres Passwort deiner Wahl):

```sql
CREATE DATABASE openhab;
CREATE USER 'openhab'@'localhost' IDENTIFIED BY 'your_password';
GRANT ALL PRIVILEGES ON openhab.* TO 'openhab'@'localhost';
FLUSH PRIVILEGES;
EXIT;
```

Jetzt solltest du MariaDB auf deinem Raspberry Pi 4 installiert und für die Verwendung mit openHAB konfiguriert haben.

Bitte beachte, dass es je nach deiner spezifischen openHAB-Konfiguration notwendig sein könnte, zusätzliche Schritte zu unternehmen, um openHAB mit MariaDB zu verbinden. Diese Schritte können variieren, je nachdem, welche openHAB-Add-ons du verwendest und wie dein openHAB-System konfiguriert ist.
