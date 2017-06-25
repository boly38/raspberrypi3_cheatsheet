# raspberrypi3_cheatsheet
note sur les commandes liées à l'installation de mon raspberry pi 3



# sources d'inspiration
* https://github.com/jgamblin/OsoYooTFT précédent howto avec LCD_show_v5

# premier démarrage

## formattage SDCard

source: https://projetsdiy.fr/decouverte-test-configuration-raspberry-pi-3/
* formatter la carte SD avec l'utilitaire de sdcard.org
* copier sur la carte les fichiers décompressés de NOOBS_v2_4_1 (récupéré sur https://www.raspberrypi.org/downloads/noobs/ )
* premier démarrage, paramétrage du wifi et installation de l'OS (en cliquant sur l'onglet install)

* vérifier que le système est à jour

    sudo apt-get update
    sudo apt-get upgrade
    sudo apt-get dist-upgrade
    sudo apt-get install raspberrypi-ui-mods
    sudo apt-get install raspberrypi-net-mods

source: http://www.raspberrypi-france.fr/premiere-utilisation-raspberry-pi/
* changement des mots de passe root et pi
* ifconfig pour relever l'ip
* install sshd


# Ecran KeDei 3.5 inch SPI TFTLCD 480x300 16bit/18bit version 6.3 2016/11/1

(en cours)
driver écran Kedei

http://kedei.net/raspberry/raspberry.html

via post forum http://forums.framboise314.fr/viewtopic.php?t=2972
