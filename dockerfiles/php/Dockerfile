ARG env=dev
FROM registry.prixtel.info/apis/docker-php-images/php7.2:latest




# A déplacer dans le tpl dockerfile
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer



# On ajoute les sources (a clean pour ajouter uniquement les sources de l'app et pas le reste)
ADD ./resources /app

WORKDIR /app

# On crée en projet proprement avec l'utilisateur qui va bien
RUN chown -R www-data. .  
USER www-data


RUN composer install
RUN bin/console assets:install 


# On se remet en root pour un pouvoir bouger les données sur un volume partagé. 

# voir les commands après run pour le docker-compose
USER root

### docker build --build-arg env=prod -t tonapp . 