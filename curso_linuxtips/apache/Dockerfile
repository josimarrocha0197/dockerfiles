FROM debian

RUN apt-get update && apt-get install -y apache2 && apt-get clean

ENV APACHE_LOCK_DIR="/var/lock"
ENV APACHE_PID_FILE="/var/run/apache2.pid"
ENV APACHE_RUN_USER="www-data"
ENV APACHE_RUN_GROUP="www-data"
ENV APACHE_LOG_DIR="/var/log/apache2"

#COPY index.html /var/www/html
ADD index.html /var/www/html
#O ADD cumpre a mesma funcao do COPY, porem, ele pode copiar arquivos TAR e copia-os para o container ja descompactados
#Ou ate mesmo arquivos externos, hospedados em determinada URL

#USER www-data

WORKDIR /var/www/html

LABEL description="Webserver"
LABEL version="1.0.0"

#Nao e possivel definir um volume do tipo BIND dentro do dockerfile
VOLUME /var/www/html/

EXPOSE 80

#Configuracoes de ENTRYPOINT
ENTRYPOINT ["/usr/sbin/apachectl"]
CMD ["-D", "FOREGROUND"]

#CMD /usr/sbin/apachectl -D FOREGROUND


