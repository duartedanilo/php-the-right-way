---
title: Desenvolvimento Guiado por Testes
isChild: true
anchor: desenvolvimento_guiado_por_testes
---

## Desenvolvimento Guiado por Testes {#desenvolvimento_guiado_por_testes_title}

Da [Wikipedia](http://en.wikipedia.org/wiki/Test-driven_development):

> O desenvolvimento guiado por testes (TDD) é um processo de desenvolvimento que se baseia na repetição de um ciclo 
de desenvolvimento bem curto: primeiro o desenvolvedor escreve um caso de teste automatizado que falha, definindo uma 
melhoria ou uma nova função desejada, em seguida produz o código para passar no teste, e finalmente refatora o novo 
código pelos padrões aceitáveis. Kent Beck, que é creditado como quem desenvolveu ou "redescobriu" essa técnica, 
afirmou em 2003 que o TDD encoraja design simples e inspira confiança.

Existem vários tipos diferentes de testes que você pode fazer para sua aplicação:

### Testes Unitários {#testes_unitarios}

Testes unitários são uma metodologia de programação que garante que as funções, as classes e os métodos estão
funcionando como esperado, desde o momento que você os constrói até o fim do ciclo de desenvolvimento. Verificando
como os valores entram e saem em várias funções e métodos, você pode garantir que a lógica interna está funcionando
corretamente. Utilizando Injeção de Dependências e construindo classes "mock" e stubs, você pode verificar se as
dependências foram utilizadas corretamente para uma cobertura de testes ainda melhor.

Quando for criar uma classe ou função, você deveria criar um teste unitário para cada comportamento que ela deveria
ter. Num nível bem básico, você deveria garantir que são emitidos erros quando você envia argumentos errados e
garantir que tudo funciona bem se você enviar argumentos válidos.  Isso ajudará a garantir que, quando você alterar
sua classe ou sua função posteriormente no ciclo de desenvolvimento, as funcionalidades antigas continuarão
funcionando como esperado. A única alternativa a isso seria usar var_dump() em um test.php, o que não é o certo a
fazer na construção de uma aplicação - grande ou pequena.

O outro uso para testes unitários é contribuir para projetos open source. Se você puder escrever um teste que
demonstra uma funcionalidade incorreta (i.e. uma falha), em seguida consertá-la e mostrar o teste passando, os
patches serão muito mais suscetíveis a serem aceitos. Se você estiver em um projeto que aceite pull requests, você
deveria sugerir isso como um requisito.

O [PHPUnit](http://phpunit.de) é o framework de testes de fato para escrever testes unitários em aplicações PHP, mas
existem várias alternativas:

* [atoum](https://github.com/atoum/atoum)
* [Kahlan](https://github.com/crysalead/kahlan)
* [Peridot](https://peridot-php.github.io/)
* [SimpleTest](https://github.com/simpletest/simpletest)

### Testes de Integração {#testes_integracao}

Da [Wikipedia](http://en.wikipedia.org/wiki/Integration_testing):

> Testes de integração (chamado às vezes de "Integração e Teste", abreviado como "I&T") é a fase do teste do software 
na qual módulos individuais do sistema são combinados e testados como um grupo. Ela acontece após os testes unitários 
e antes dos testes de validação. Os testes de integração recebem como entrada os módulos que foram testados 
unitariamente, os agrupa em grandes blocos, aplica testes definidos em um plano de teste de integração, e entrega como 
saída o sistema integrado pronto para os testes de sistema.

Muitos das mesmas ferramentas que são usadas para testes unitários podem ser usadas para testes de integração, pois
muitos dos mesmos princípios são usados.

### Testes Funcionais {#testes_funcionais}

Algumas vezes conhecidos também como testes de aceitação, os testes funcionais consistem em utilizar ferramentas para
criar testes automatizados que usem de verdade sua aplicação, em vez de apenas verificar se unidades individuais de
código se comportam adequadamente ou se essas partes conversam entre si do jeito certo. Essas ferramentas geralmente
trabalham usando dados reais e simulam usuários verdadeiros da sua aplicação.

#### Ferramentas para Testes Funcionais {#ferramentas_para_testes_funcionais}

* [Selenium](https://www.selenium.dev/)
* [Mink](http://mink.behat.org)
* O [Codeception](http://codeception.com) é um framework de testes full-stack que inclui ferramentas para testes de 
aceitação
* O [Storyplayer](http://datasift.github.io/storyplayer/) é um framework de testes full-stack que inclui suporte para 
criação e destruição de ambientes sob demanda