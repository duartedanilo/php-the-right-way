---
title: Servidores Virtuais ou Dedicados
isChild: true
anchor: servidores_virtuais_ou_dedicados
---

## Servidores Virtuais ou Dedicados {#servidores_virtuais_ou_dedicados_title}

Se você estiver confortável com administração de sistemas, ou estiver interessado em aprender sobre isso, os
servidores virtuais ou dedicados te dão controle completo do ambiente de produção da sua aplicação.

### nginx e PHP-FPM

O PHP, por meio do seu Gerenciador de Processos FastCGI (FPM), funciona muito bem junto com o [nginx],
que é um servidor web leve e de alta performance. Ele usa menos memória do que o Apache e pode lidar melhor como
muitas requisições concorrentes. Ele é importante especialmente em servidores virtuais que não tem muita memória
sobrando.

* [Leia mais sobre o nginx][nginx]
* [Leia mais sobre o PHP-FPM][phpfpm]
* [Leia mais sobre como configurar de forma segura o nginx e o PHP-FPM][secure-nginx-phpfpm]

### Apache e PHP

O PHP e o Apache tem um longo histórico juntos. O Apache é amplamente configurável e tem muitos
[módulos][apache-modules] disponíveis para estender suas funcionalidades. Ele é uma escolha
popular para servidores compartilhados e pela configuração fácil em frameworks PHP e aplicativos open source como, o
Wordpress. Infelizmente, o Apache utiliza mais recursos do que o nginx por padrão e não pode lidar com tantos
visitantes ao mesmo tempo.

O Apache tem várias configurações possíveis para executar o PHP. A mais comum e mais fácil para configurar é a
[prefork MPM] com o mod_php5. Mesmo não sendo a mais eficiente em
memória, é a mais simples para começar a usar. Essa é provavelmente a melhor escolha se você não quiser entrar muito
profundamente nos aspectos de administração do servidor. Observe que, se você usar o mod_php5, terá que usar o prefork 
MPM.

Alternativamente, se você quiser extrair mais performance e estabilidade do seu Apache então você poderia se
beneficiar do mesmo sistema FPM que o nginx e executar o [worker MPM]
ou o [event MPM] com o mod_fastcgi ou com o mod_fcgi. Essa
configuração será significativamente mais eficiente em relação a memória e muito mais rápida, mas gera mais trabalho.

* [Leia mais sobre o Apache][apache]
* [Leia mais sobre os Multi-Processing Modules][apache-MPM]
* [Leia mais sobre o mod_fastcgi][mod_fastcgi]
* [Leia mais sobre o mod_fcgid][mod_fcgid]
* [Leia mais sobre o mod_proxy_fcgi][mod_proxy_fcgi]
* [Leia mais sobre a configuração do Apache e PHP-FPM com mod_proxy_fcgi][tutorial-mod_proxy_fcgi]


[nginx]: https://nginx.org/
[phpfpm]: https://secure.php.net/install.fpm
[secure-nginx-phpfpm]: https://nealpoole.com/blog/2011/04/setting-up-php-fastcgi-and-nginx-dont-trust-the-tutorials-check-your-configuration/
[apache-modules]: https://httpd.apache.org/docs/2.4/mod/
[prefork MPM]: https://httpd.apache.org/docs/2.4/mod/prefork.html
[worker MPM]: https://httpd.apache.org/docs/2.4/mod/worker.html
[event MPM]: https://httpd.apache.org/docs/2.4/mod/event.html
[apache]: https://httpd.apache.org/
[apache-MPM]: https://httpd.apache.org/docs/2.4/mod/mpm_common.html
[mod_fastcgi]: https://blogs.oracle.com/opal/post/php-fpm-fastcgi-process-manager-with-apache-2
[mod_fcgid]: hhttps://httpd.apache.org/mod_fcgid/
[mod_proxy_fcgi]: https://httpd.apache.org/docs/current/mod/mod_proxy_fcgi.html
[tutorial-mod_proxy_fcgi]: https://serversforhackers.com/video/apache-and-php-fpm