# Lab Vagrant Multi-OS com Servidores Web

Laboratório usando Vagrant para provisionar e configurar três máquinas virtuais com diferentes sistemas operacionais e servidores web. O projeto simula um ambiente heterogêneo para estudo e testes.

Servidor 1: Ubuntu 20.04 (Focal) com Nginx, acessível na porta 8080 e IP público 192.168.15.5. <br>
Servidor 2: Ubuntu 18.04 (Bionic) com Apache, acessível na porta 8090 e IP público 192.168.15.6. <br>
Servidor 3: CentOS 7 com Apache, acessível na porta 8095 e IP privado 192.168.56.5. <br>
<br>
O provisionamento inclui atualização dos pacotes e instalação automática dos servidores web (Nginx e Apache). <br>
Há sincronização de pastas locais para simular o deploy de um site no servidor.
