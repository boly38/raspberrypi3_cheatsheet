# raspberrypi3_cheatsheet
note sur les commandes liées à l'installation de mon raspberry pi 3




# premier démarrage

Au premier démarrage je pensais naïvement avoir linux accessible sur mon écran LCD au premier boot, mais non rien sur la carte SD.
* Heureusement, l'adaptateur SD => micro SD est fournit.
* aussin un câble HDM me permet de voir l'UI du rasp sur ma télé en attendant d'avoir le SSH ou l'écran LCD qui fonctionne...


## formattage SDCard

source: https://projetsdiy.fr/decouverte-test-configuration-raspberry-pi-3/
* formatter la carte SD avec l'utilitaire de sdcard.org ([win](https://www.sdcard.org/downloads/formatter_4/eula_windows/index.html) ou [mac](https://www.sdcard.org/downloads/formatter_4/eula_mac/index.html) )
* copier sur la carte les fichiers décompressés de `NOOBS_v2_4_1.zip` (dernière version à récupérer sur https://www.raspberrypi.org/downloads/noobs/ )

## clavier bluetooth fourni
![Clavier bluetooth](https://raw.githubusercontent.com/boly38/raspberrypi3_cheatsheet/master/IMG_20170625_205327.jpg "Clavier bluetooth")

* il faut déclipser le compartiment arrière pour accéder aux piles et au dongle USB=>Bluetooth
* fonctionne avec les 2 piles AAA: la connexion en USB directement ne semble pas fonctionner
* lorsqu'aucune synchro bluetooth n'a pu se faire le clignotant jaune s'arrête

## installation
* au premier démarrage, l'écran permet :
   * paramétrage du wifi
   * choix de la langue
   * installation de l'OS (en cliquant sur l'onglet install en haut...)

## aptitude update

* vous pouvez toujours vérifier que le système est à jour
```
    sudo apt-get update
    sudo apt-get upgrade
    sudo apt-get dist-upgrade
    sudo apt-get install raspberrypi-ui-mods
    sudo apt-get install raspberrypi-net-mods
```

## mdp et ssh

source: http://www.raspberrypi-france.fr/premiere-utilisation-raspberry-pi/
* changement des mots de passe root et pi
```
sudo passwd root
sudo passwd pi
```
* ifconfig pour relever l'ip
```
ifconfig
```
* install sshd, [tout y est aussi](http://www.raspberrypi-france.fr/premiere-utilisation-raspberry-pi/#Parametrage-de-la-connexion-SSH)

## lancer une application graphique depuis le pécé
* installer Xming ([choisir public domain releases](http://www.straightrunning.com/XmingNotes/))
* se connecter avec putty avec le X11 forwarding ([exemple](http://jmdefais.pagesperso-orange.fr/techn_jm/robot/robot_pi/putty.htm))
* test
```
xclock&
```


# Ecran KeDei 3.5 inch SPI TFTLCD 480x300 16bit/18bit version 6.3 2016/11/1

Cette section décrit comment faire fonctionner l'écran LCD KeDei.


Sources utilisées pour cette section:
* driver écran Kedei
   * http://kedei.net/raspberry/raspberry.html (download très très lent)
   * via post forum http://forums.framboise314.fr/viewtopic.php?t=2972
* précédent howto avec LCD_show_v5 : https://github.com/jgamblin/OsoYooTFT 


![arrière écran KeDei](https://raw.githubusercontent.com/boly38/raspberrypi3_cheatsheet/master/IMG_20170625_193519.jpg "arrière écran KeDei")

![plug écran KeDei](https://raw.githubusercontent.com/boly38/raspberrypi3_cheatsheet/master/IMG_20170625_193544.jpg "plug écran KeDei")

* récupérer le driver dernière version
* s'il est sur le pécé vous pouvez le transférer via scp (j'utilise git bash et le port ssh 65530)
```
scp -P 65530 LCD_show_v6_1_3.tar.gz pi@192.168.0.38:~/
``` 

* driver
```
sudo mkdir /opt/ecranLCD
sudo mv LCD_show_v6_1_3.tar.gz /opt/ecranLCD/
cd /opt/ecranLCD/
sudo tar -xzvf LCD_show_v6_1_3.tar.gz
cd LCD_show_v6_1_3/
 ./LCD35_v
```
* après reboot vous devriez avoir l'écran LCD.
* a priori la commande suivante restore le HDMI au besoin (non testé)
```
./LCD_restore
```


