Install Openvpn_exporter
=========

Эта роль предназначена для установки на OpenVPN Server экспортера для сбора метрик работы сервера. Будет установлен openvpn_exporter и создан сервис в consul

Requirements
------------

* Прокатать роли common и consul_agent_install
* Для полноценного сбора метрик, необходимо чтобы в конфиге openvpn сервера (exL/etc/openvpn/server.conf) были следующие строки:
  - status /var/log/openvpn/openvpn-status.log
  - status-version 3