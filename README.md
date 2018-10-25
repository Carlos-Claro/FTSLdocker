# FTSLdocker
Potos do minicurso de docker na UTFPR FTSL 2018



Containers, maquinas zeradas e limpas, sempre que iniciar uma nova etapa...
quando destroi um container os dados fisicos estão salvos na pasta do pc principal, que esta ligado via compartilhamento.

- instruções
https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-18-04
https://hub.docker.com/

- requisitos


- comandos de criação do docker

docker images (verifica as images disponiveis)
docker info
docker run hello-world (instala uma image hello)
docker search ubuntu (pesquisa images de ubuntu)
docker pull ubuntu (instala a versao do ubuntu, sem parametro, é a ultima)
docker images
docker run -it ubuntu (roda e acessa a maquina via terminal)
docker run --name moda-foka -it ubuntu (renomeia o container)
docker ps (verifica maquinas ligadas)
docker ps -a(verifica maquinas existentes)
docker rm upbeat_fermi (deleta da lista de existentes)
docker start [id] (inicia o container)
docker attach [id] (acessa novamente esta maquina)
docker run -it ubuntu:16.04 /bin/bash (cria uma maquina com 16.04)
*faz modificaçoes na maquina*
1  ls 
    2  cd moda-foka/
    3  ls
    4  apt install git vim apache2
    5  echo 'ServerName localhost' | tee /etc/apache2/conf-available/fqdn.conf
    6  a2enconf fqdn
    7  service apache2 reload
    8  service apache2 status
    9  echo 'ServerName localhost' | tee /etc/apache2/conf-available/fqdn.conf 
   10  service apache2 restart
   11  service apache2 status
   12  history
*fim modificaçoes na maquina*
docker ps
docker commit 2f5b5bdd9fee ubuntugoku (salva esta imagem como uma imagem nova...)
docker run -it ubuntugoku /bin/bash (executa container) (para sair e deixar rodando digita ctrl + p + q)
docker commit --change 'CMD ["apache2ctl","-D FOREGROUND "]' -c 'Expose 85' 8e8b88209131 apache2 (commit change com apache)
docker images
docker run -d -p 5000:80 apache2 (inicia a maquina com apache 2 na porta 5000)

