<h1>jenkins-maker</h1>

<h2>1. Описание набора скриптов</h2>
Набор скриптов для автоматического развёртывания Jenkins-серверов через Ansible, в HA-режиме с балансировкой через nginx.

<h2>2. Развёртывание Jenkins-серверов</h2>
Заходим в корневой <a href="http://jenkins0.abelyakov.me:8080">Jenkins</a> (логин и пароль в личке)

Задача <a href="http://jenkins0.abelyakov.me:8080/job/SetupJenkinses/">"Настройка Jenkins-серверов через Ansible"</a> разворачивает два игрушечных Jenkins, 
с преконфигурированным пользователем demo и преконфигурированной джобой <a href="http://jenkins1.abelyakov.me:8080/job/Hello">"Hello"</a>

URL'ы серверов: <a href="http://jenkins1.abelyakov.me:8080">первый</a>, <a href="http://jenkins2.abelyakov.me:8080">второй</a>

Jenkins-сервера делят между собой один и тот же JENKINS_HOME через Amazon EFS

<h2>3. Развёртывание Nginx-proxy</h2>

Для обеспечения более высокой доступности Jenkins автоматически разворачивается Nginx-прокси.

Серверы Jenkins доступны через <a href="http://jenkins-proxy.abelyakov.me">прокси</a> в режиме ip_hash (nginx старается проксировать запросы одного пользователя к одному и тому же серверу, при условии, что он доступен,
в обратной ситуации он пытается перенаправлять к другому)

Ссылка на джобу: <a href="http://jenkins0.abelyakov.me:8080/job/SetupProxies">Настройка Proxy через Ansible</a>

<h2>4. Дополнительные комментарии</h2>
Так как эта инфраструктура игрушечная, то перезагрузить конфигурацию Jenkins из файловой системы можно из браузера ($JENKINS_URL/reload) или Jenkins Script Console:
<pre>
hudson.model.Hudson.instance.reload();
</pre>
В боевой системе перезагрузку конфигурации (POST-запросом) можно было бы поручить, например, Zabbix. Для пользователей подмена рабочего сервера Jenkins прошла бы совершенно незаметно.
