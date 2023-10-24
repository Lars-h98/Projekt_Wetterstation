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




Anmeldedaten:
projekt
Start123!

