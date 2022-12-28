---
title: Compilando e Implementando sua Aplicação
isChild: true
anchor: compilando_e_implementando_sua_aplicacao
---

## "Compilando" e Implementando sua Aplicação {#compilando_e_implementando_sua_aplicacao_title}

Se você se pegar fazendo alterações manuais no seu esquema do banco de dados ou rodando seus testes manualmente antes de
alterar seus arquivos (manualmente), pense duas vezes! A cada tarefa manual adicional necessária para implementar uma
nova versão da sua aplicação as chances de erros fatais são potencialmente maiores, Seja lidando com uma simples
atualização, um processo completo de implementação ou até mesmo uma estratégia de integração contínua, a
[Automação de Compilação][buildautomation] é sua amiga.

Entre as tarefas que talvez você deseja automatizar estão:

* Gerenciamento de Dependências
* Compilação e Compressão de Arquivos
* Execução de Testes
* Criação de Documentação
* Empacotamento
* Implementação

### Ferramentas de implantação

Ferramentas de implantação podem ser descritas como uma coleção de scripts que tratam de tarefas comuns da 
implementação de software. As ferramentas de implantação não são parte da sua aplicação, 
elas agem na sua aplicação externamente.

Existem muitas ferramentas de código aberto disponíveis para ajudar você com o processo de implantação, algumas são
escritas em PHP, outras não. Isso não deve impedi-lo de usá-las, se elas se ajustarem melhor ao trabalho em questão.
Aqui estão alguns exemplos:

[Phing] pode controlar os processos de empacotamento, implementação e testes por meio de um simples arquivo XML.
Phing (Que é baseado em [Apache Ant]) fornece um rico conjunto de tarefas geralmente necessárias para 
instalar ou atualizar uma aplicação web e pode ser estendido com tarefas adicionais personalizadas, escritas em PHP.
É uma ferramenta solida e robusta e já existe há um bom tempo, no entanto a ferramenta pode ser vista 
como um pouco antiquada pela forma que lida com a configuração (arquivo XML).

[Capistrano] é um sistema para *programadores intermediários a
avançados* que executa comando de forma estruturada e repetitiva em uma ou mais máquinas. É pré-configurado para
implementar aplicações Ruby on Rails, entretanto você pode implementar sistemas PHP utilizando essa ferramenta.
O uso bem sucedido do Capistrano depende de um conhecimento prático com Ruby e Rake.

[Ansistrano] é um conjunto de roles do Ansible para facilmente gerenciar o processo de implantação para aplicações 
de script como PHP, Python e Ruby. É uma porta do Ansible para o [Capistrano]. Já foi bastante usado 
por muitas empresas que utilizam PHP. 

[Rocketeer] tem sua inspiração e filosofia do framework Laravel. Seu objetivo é ser rápido, elegante e 
fácil de usar com padrões inteligentes. Suporta múltiplos servidores, múltiplos ambientes, implantação atômica 
e a implantação pode ser executada em paralelo. Tudo nessa ferramenta pode ser trocado ou estendido e tudo é 
escrito em PHP.

[Deployer] é uma ferramenta de implementação escrita em PHP. É simples e funcional. 
Seus recursos incluem tarefas de execução em paralelo, implementação atômica e manter consistência 
entre os servidores.
Tutoriais de tarefas simples para Symfony, Laravel, Zend Framework e Yii estão disponíveis. O artigo do 
Younes Rafie [Easy Deployment of PHP Applications with Deployer][phpdeploy_deployer] é um ótimo tutorial 
para fazer a implantação da sua aplicação com a ferramenta.

[Magallanes] é outra ferramenta escrita em PHP com uma configuração simples feita em arquivos YAML. 
Tem suporte para múltiplos servidores e ambientes, implementação atômica e algumas 
tarefas embutidas que podem ser aproveitadas para ferramentas comuns e frameworks.

#### Leitura adicional:

* [Automatize seu projeto com Apache Ant][apache_ant_tutorial]
* [Faça deploy de aplicações PHP][deploying_php_applications] - livro pago de boas práticas e ferramentas para implantação com PHP.

### Provisionamento de Servidor

Gerenciar e configurar servidores pode ser uma tarefa complicada quando se lida com múltiplos servidores. 
Existem ferramentas para lidar com isso e automatizar a infraestrutura para 
garantir que os servidores estão corretos e configurados corretamente. 
Geralmente são integrados com grandes provedores de cloud (Amazon Web Services, Heroku, DigitalOcean, etc) 
para gerenciar instâncias, o que torna a escalabilidade de aplicações mais fácil.

[Ansible] é uma ferramenta que gerenciar sua infraestrutura por meio de arquivos YAML. 
É simples de começar a utiliza-lo e pode gerenciar aplicações complexas e de larga escala. 
Existe uma API para gerenciamento instâncias de cloud e pode gerencia-las 
por meio de um inventário dinâmico usando determinadas ferramentas.

[Puppet] é uma ferramenta que tem sua própria linguagem e tipos de arquivos para gerenciar servidores e configurações. 
Pode ser usado em um setup master/client setup ou pode ser usado no modo "master-less".
No modo master/client os clientes indicarão ao mestre central por uma nova configuração em intervalos 
definidos e se atualizarão se for necessário. No modo master-less você pode enviar as mudanças para os nós.

[Chef] é um poderoso framework de integração feito em Ruby que pode construir seu ambiente de servidor
completo ou maquinas virtuais. Se integra bem com Amazon Web Services por meio do serviço chamado OpsWorks.

#### Leitura Adicional:

* [Tutorial de Ansible][an_ansible_tutorial]
* [Ansible para DevOps][ansible_for_devops] - livro pago sobre Ansible
* [Ansible para AWS][ansible_for_aws] - livro pago sobre a integração de Ansible com Amazon Web Services
* [Série com três partes sobre implementar uma aplicação LAMP com Chef, Vagrant e EC2][chef_vagrant_and_ec2]
* ["Livro de receitas" do Chef  para instalar e configurar PHP e o sistema de gerenciamento de pacote PEAR][Chef_cookbook]
* [Série de vídeos tutoriais de Chef][Chef_tutorial

### Integração Contínua

> Integração Contínua é uma prática de desenvolvimento de software onde membros de um time integram seu trabalho com
> frequência, geralmente essa integração ocorre diariamente - levando a muitas integrações de código por dia. Muitos
> times acreditam que essa abordagem leva a reduções significativas dos problemas de integração e permite que o time
> desenvolva software de forma coesa e rápida.

*-- Martin Fowler*

Existem diferentes formas de se implementar integração contínua com PHP. [Travis CI]
tem feito um ótimo trabalho ao fazer da integração contínua uma realidade mesmo para pequenos projetos. O Travis CI é um
sistema de integração contínua na nuvem desenvolvido pela comunidade de código livre. Esta integrado com GitHub e oferece
suporte de primeira classe para muitas linguagens incluindo PHP.

#### Leitura Adicional:

* [Integração Contínua com Jenkins][Jenkins]
* [Integração Contínua com PHPCI][PHPCI]
* [Integração Contínua com PHP Censor][PHP Censor]
* [Integração Contínua com Teamcity][Teamcity]


[buildautomation]: https://wikipedia.org/wiki/Build_automation
[Phing]: https://www.phing.info/
[Apache Ant]: https://ant.apache.org/
[Capistrano]: https://capistranorb.com/
[Ansistrano]: https://ansistrano.com
[phpdeploy_deployer]: https://www.sitepoint.com/deploying-php-applications-with-deployer/
[Chef]: https://www.chef.io/
[chef_vagrant_and_ec2]: https://web.archive.org/web/20190307220000/http://www.jasongrimes.org/2012/06/managing-lamp-environments-with-chef-vagrant-and-ec2-1-of-3/
[Chef_cookbook]: https://github.com/chef-cookbooks/php
[Chef_tutorial]: https://www.youtube.com/playlist?list=PL11cZfNdwNyPnZA9D1MbVqldGuOWqbumZ
[apache_ant_tutorial]: https://code.tutsplus.com/tutorials/automate-your-projects-with-apache-ant--net-18595
[Travis CI]: https://www.travis-ci.com/
[Jenkins]: https://jenkins.io/
[PHPCI]: https://github.com/dancryer/phpci
[PHP Censor]: https://github.com/php-censor/php-censor
[Teamcity]: https://www.jetbrains.com/teamcity/
[Deployer]: https://deployer.org/
[Rocketeer]: http://rocketeer.autopergamene.eu/
[Magallanes]: https://www.magephp.com/
[deploying_php_applications]: https://deployingphpapplications.com/
[Ansible]: https://www.ansible.com/
[Puppet]: https://puppet.com/
[ansible_for_devops]: https://leanpub.com/ansible-for-devops
[ansible_for_aws]: https://leanpub.com/ansible-for-aws
[an_ansible_tutorial]: https://serversforhackers.com/an-ansible-tutorial