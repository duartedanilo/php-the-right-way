---
title: Ferramentas Complementares para Testes
isChild: true
anchor: ferramentas_complementares_para_testes
---

## Ferramentas Complementares para Testes {#ferramentas_complementares_para_testes_title}

Além dos testes individuais e dos frameworks guiados por comportamentos, também existe uma série de frameworks
genéricos e bibliotecas auxiliares úteis para qualquer das abordagem escolhidas.

### Links para as Ferramentas

* [Selenium] é uma ferramenta para automação de navegação que pode ser 
[integrada ao PHPUnit][integrated with PHPUnit].
* [Mockery] é um Framework para Objetos Mock que pode ser integrado ao [PHPUnit] e ao [PHPSpec].
* [Prophecy] é um framework para Objetos Mock bastante obstinado porém poderoso e flexível. 
É integrado com [PHPSpec] e pode ser usado com [PHPUnit].
* [php-mock] é uma biblioteca que ajuda a criar mocks de funções nativas do PHP.
* [Infection] é uma implementação PHP do [Teste de Mutação][Mutation Testing] para ajudar a mensurar a efetividade dos testes.
* [PHPUnit Polyfills] é uma biblioteca que permite a criação de testes compatíveis entre diferentes versões do 
PHPUnit quando uma suíte de testes precisa executar entre uma variedade de versões do PHPUnit.


[Selenium]: https://www.selenium.dev/
[integrated with PHPUnit]: https://github.com/giorgiosironi/phpunit-selenium/
[Mockery]: https://github.com/padraic/mockery
[PHPUnit]: https://phpunit.de/
[PHPSpec]: https://www.phpspec.net/
[Prophecy]: https://github.com/phpspec/prophecy
[php-mock]: https://github.com/php-mock/php-mock
[Infection]: https://github.com/infection/infection
[Mutation Testing]: https://pt.wikipedia.org/wiki/Teste_de_mutação
[PHPUnit Polyfills]: https://github.com/Yoast/PHPUnit-Polyfills