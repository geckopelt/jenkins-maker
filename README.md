<h1>jenkins-maker</h1>

<h2>Описание набора скриптов</h2>
Набор скриптов для автоматического развёртывания Jenkins-серверов через Ansible, в HA-режиме с балансировкой через nginx

<h2>Развёртывание Jenkins-серверов</h2>
Заходим в корневой <a href="http://jenkins0.abelyakov.me:8080">Jenkins</a> (логин и пароль в личке)

Задача <a href="http://jenkins0.abelyakov.me:8080/job/SetupJenkinses/">"Настройка Jenkins-серверов через Ansible"</a> разворачивает два игрушечных Jenkins, 
с преконфигурированным пользователем demo и преконфигурированной джобой <a href="http://jenkins1.abelyakov.me:8080">"Hello"</a>

URL'ы серверов: <a href="http://jenkins1.abelyakov.me:8080">первый</a>, <a href="http://jenkins2.abelyakov.me:8080">второй</a>
