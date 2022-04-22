# Описание
1.Склонировать репозиторий git https://github.com/smirnovng/ansible_proxmox.git
2.Отредактировать файл с настройками ВМ vms.yml

В файле мы определим переменные, необходимые для авторизации в API Proxmox-авторизации:

 - api_host: m11618.contaboserver.net
 - api_user: root@pam
 - api_password: XXXXXXXXXXXX

И переменные, описывающие характеристики виртуальных машин:

 - node: m11618 - идентификатор ноды в Proxmox
 - clone_vm: template-centos7 - имя template, из которого мы будем клонировать VM
 - key_name: id_rsa.pub (имя ключа, который будет скопирован в VM)
 - словарь vms, с определением индивидуальных характеристик VM
   - name: master.example.com - FQDN
   - ipaddress: 10.21.21.51/24 - IP адрес
   - vmid: 200 - уникальный ID VM
   - cores: 2 - количество ядер
   - sockets: 1 - количество сокетов
   - memory: 1024 - размер оперативной памяти (в мегабайтах!)

3.git add vms.yml
4.git commit -a -m "комментарий"
5.git push

После чего jenkins запустит выполнение сценария

