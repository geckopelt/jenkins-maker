jenkins-maker

Набор скриптов для автоматического развёртывания Jenkins-серверов через Ansible, в HA-режиме с балансировкой через nginx

Как это работает:

Заходим в корневой <a href="http://jenkins0.abelyakov.me:8080">Jenkins</a> (логин и пароль в личке)

Задача <a href="http://jenkins0.abelyakov.me:8080/job/SetupJenkinses/">"Настройка Jenkins-серверов через Ansible"</a> разворачивает два игрушечных Jenkins:
<li>http://jenkins1.abelyakov.me:8080
<li>http://jenkins2.abelyakov.me:8080
