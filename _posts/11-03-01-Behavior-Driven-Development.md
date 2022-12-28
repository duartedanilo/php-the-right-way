---
title: Desenvolvimento Guiado por Comportamentos
isChild: true
anchor: desenvolvimento_guiado_por_comportamentos
---

## Desenvolvimento Guiado por Comportamentos {#desenvolvimento_guiado_por_comportamentos_title}

Existem dois tipos diferentes de Desenvolvimento Guiado por Comportamentos (BDD): o SpecBDD e o StoryBDD. O SpecBDD 
foca nos comportamentos técnicos, no código, enquanto que o StoryBDD foca nos comportamentos de negócio e de 
funcionalidades, nas interações. O PHP possui frameworks para ambos os tipos de BDD.

No StoryBDD, você escreve histórias humanamente legíveis que descrevem o comportamento da sua aplicação. Estas 
histórias podem então ser executadas como testes reais em sua aplicação. O framework usado nas aplicações PHP para 
StoryBDD é o [Behat], que foi inspirado no projeto [Cucumber] do Ruby e implementa a linguagem 
Gherkin DSL para descrever o comportamento das funcionalidades.

No SpecBDD, você escreve as especificações que descrevem como seu código real deveria se comportar. Em vez de escrever 
uma função ou método, você descreve como a função ou o método deveriam se comportar. O PHP fornece o framework [PHPSpec] 
para esse propósito. Esse framework foi inspirado no [projeto RSpec][Rspec] do Ruby.

### Links sobre BDD

* O [Behat] é inspirado pelo projeto [Cucumber] do Ruby
* O [PHPSpec] é o framework para SpecBDD do PHP
* O [Codeception] é um framework de testes full-stack que usa os princípios do BDD


[Behat]: https://behat.org/
[Cucumber]: https://cucumber.io/
[PHPSpec]: https://www.phpspec.net/
[RSpec]: https://rspec.info/
[Codeception]: https://codeception.com/