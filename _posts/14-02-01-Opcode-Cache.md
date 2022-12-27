---
title: Cache opcode
isChild: true
anchor: cache_opcode
---

## Cache opcode {#cache_de_opcode_title}

Quando um arquivo PHP é executado, deve ser primeiramente compilado para [opcodes](https://php-legacy-docs.zend.com/manual/php4/en/internals2.opcodes) (intruções de linguagem de máquina para CPU). Se o código fonte não for alterado, os opcodes serão os mesmos, então o passo da compilação será um gasto de recursos de CPU. 

Um cache opcode previne compilação redundante alocando opcodes em memória e reutilizando-os em sucessivas chamadas. Tipicamente será checada a assinatura ou tempo de modificação do arquivo primeiro, caso tenha ocorrido alguma mudança.

Provavelmente um cache opcode trará melhora significativa na velocidade da sua aplicação. Desde o PHP 5.5 existe o [Zend OPcache][opcache-book] embutido. Dependendo do seu pacote/distribuição, geralmente é ativado por padrão - verifique [opcache.enable](https://www.php.net/manual/pt_BR/opcache.configuration.php#ini.opcache.enable) e saída do `phpinfo()` para ter certeza. Para versões mais recentes tem uma extensão no PECL.

Leia mais sobre o cache opcode:

* [Zend OPcache][opcache-book] (embutido no PHP desde a versão 5.5)
* Zend OPcache (anteriormente conhecido como Zend Optimizer+) agora é [open source][Zend Optimizer+]
* [APC] - PHP 5.4 e anteriores
* [XCache]
* [WinCache] (extensão para MS Windows Server)
* [lista de aceleradores para PHP na Wikipedia][PHP_accelerators]
* [PHP Preloading] - PHP >= 7.4


[opcache-book]: https://www.php.net/manual/pt_BR/book.opcache.php
[APC]: https://www.php.net/manual/pt_BR/book.apcu.php
[XCache]: https://github.com/lighttpd/xcache
[Zend Optimizer+]: https://github.com/zendtech/ZendOptimizerPlus
[WinCache]: https://www.iis.net/downloads/microsoft/wincache-extension
[PHP_accelerators]: https://wikipedia.org/wiki/List_of_PHP_accelerators
[PHP Preloading]: https://www.php.net/manual/pt_BR/opcache.preloading.php