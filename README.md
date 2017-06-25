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
* premier démarrage, paramétrage du wifi et installation de l'OS (en cliquant sur l'onglet install en haut...)

## aptitude update

* vous pouvez toujours vérifier que le système est à jour

    sudo apt-get update
    sudo apt-get upgrade
    sudo apt-get dist-upgrade
    sudo apt-get install raspberrypi-ui-mods
    sudo apt-get install raspberrypi-net-mods
    
## mdp et ssh

source: http://www.raspberrypi-france.fr/premiere-utilisation-raspberry-pi/
* changement des mots de passe root et pi
* ifconfig pour relever l'ip
* install sshd


# Ecran KeDei 3.5 inch SPI TFTLCD 480x300 16bit/18bit version 6.3 2016/11/1

(en cours)

sources à traiter:
* driver écran Kedei
   * http://kedei.net/raspberry/raspberry.html
   * via post forum http://forums.framboise314.fr/viewtopic.php?t=2972
* précédent howto avec LCD_show_v5
   NDLR: on dirait que le tgz a été rappatrié sur github car le server kedei.net est lent de chez lent..
   * https://github.com/jgamblin/OsoYooTFT 
