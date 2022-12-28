---
isChild: true
title: Camadas de Abstração
anchor: camadas_de_abstracao_de_banco_de_dados
---

## Camadas de Abstração {#camadas_de_abstracao_de_banco_de_dados_title}

Muitos frameworks fornecem sua própria camada de abstração que pode ou não sobrepor o [PDO][1]. Estes muitas vezes 
simulam características de um sistema de banco de dados que outro banco de dados não possui envolvendo suas consultas 
em métodos PHP, dando-lhe a abstração real do banco de dados em vez de apenas a abstração da conexão como o PDO oferece.

Isto obviamente adiciona um pequeno peso, mas se você estiver construindo uma aplicação portátil que precise trabalhar 
com MySQL, PostgreSQL e SQLite, então este pequeno peso vai valer a pena pela limpeza e menos linhas de código.

Algumas camadas de abstração foram construídas utilizando o padrão de namespaces da [PSR-0][psr0] ou [PSR-4][psr4] para 
que possa ser instalado em qualquer aplicação que você queira:

* [Atlas][5]
* [Aura SQL][6]
* [Doctrine2 DBAL][2]
* [Medoo][8]
* [Propel][7]
* [Zend-db][4]


[1]: http://php.net/book.pdo
[2]: http://www.doctrine-project.org/projects/dbal.html
[4]: https://packages.zendframework.com/docs/latest/manual/en/index.html#zendframework/zend-db
[5]: https://atlasphp.io
[6]: https://github.com/auraphp/Aura.Sql
[7]: http://propelorm.org/
[8]: https://medoo.in/
[psr0]: https://www.php-fig.org/psr/psr-0/
[psr4]: https://www.php-fig.org/psr/psr-4/