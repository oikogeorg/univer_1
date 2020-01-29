# univer_1
docker for exercise
Δημιουργία ενός φακέλου που ονομάζεται my-webapp μέσα στο myprojects στο home directory του χρήστη.

ee06695@snf-871820:~$ mkdir -p ~/myprojects/my-webapp

Μπαίνουμε μέσα στον φάκελο που ονομάζεται ~/myprojects/my-webapp

ee06695@snf-871820:~$ cd ~/myprojects/my-webapp
ee06695@snf-871820:~$~/myprojects/my-webapp




ee06695@snf-871820:~/myprojects/my-webapp$ vim docker-compose.yml

Το περιεχόμενό του φαίνεται παρακάτω:

version: '3.3'
services:
  web:
    image: php:7.3-apache
    container_name: php73
    volumes:
      - ./php:/var/www/html/
    ports:
      - 8009:80



Στη συνέχεια ξεκινάει και να κατεβάσει τα αρχεία php,apache το container με την παρακάτω εντολή:

ee06695@snf-871820:~/ myprojects/my-webapp$ docker-compose up



Δημιουργούμε το αρχείο index.php μεσα στο φάκελο php σαν root χρήστης
.

ee06695@snf-871820:~$ cd ~/myprojects/my-webapp/php
ee06695@snf-871820:~/ myprojects/my-webapp/php/sudo nano index.php
[sudo] password for ee06695:


Το περιεχόμενο του αρχείου index.php τώρα θα είναι το παρακάτω.

<?php
echo ‘Hello from docker’;
?>


Στη συνέχεια ξανά ξεκινάει το container με την παρακάτω εντολή:

ee06695@snf-871820:~/ myprojects/my-webapp/php$ docker-compose up

Όταν χρειάζεται να σταματήσει το container, αυτό γίνεται με την παρακάτω εντολή:
ee06695@snf-871820:~/ myprojects/my-webapp/php$ docker-compose stop
Όταν χρειάζεται να ξεκινήσει πάλι το container, αυτό γίνεται με την παρακάτω εντολή:

ee06695@snf-871820:~/ myprojects/my-webapp/php$ docker-compose start



Όταν χρειάζεται να διαγραφεί το container αυτό, γίνεται με την παρακάτω εντολή:
ee06695@snf-871820:~/ myprojects/my-webapp/php$ docker-compose down
