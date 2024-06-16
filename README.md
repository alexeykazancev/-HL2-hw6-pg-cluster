Цель дз развернуть postgresql кластер на базе patroni

Для этого создаем три ноды для postgresql кластер с помощью vagrant

Ansible ставит mysql-server и mysql-shell

Для создания машин запускаем команду:
vagrant up

в данном репозитории используется дебиан 11, файл бокс расположен локально. Для корректной отработки команды "вагрант ап" необходимо скачать этот файл по ссылке:
https://app.vagrantup.com/generic/boxes/debian11/versions/4.3.12/providers/virtualbox/amd64/vagrant.box 
и положить по удобновму пути , указав его в вагрантфайле

далее, для установки mysql server и шел выполнить следующие команды:
cd provision

ansible-playbook playbooks/environment.yml

проверить корректность установки ключа для логина по ssh можно командой:

vagrant ssh pgsql1

vagrant ssh pgsql2

vagrant ssh pgsql3

