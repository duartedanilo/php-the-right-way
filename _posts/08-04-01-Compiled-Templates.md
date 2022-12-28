---
isChild: true
title: Templates Compilados
anchor: compiled_templates
---

## Templates Compilados {#compiled_templates_title}

Enquanto o PHP evoluiu para uma linguagem orientada a objetos madura, ele 
[não melhorou muito](http://fabien.potencier.org/templating-engines-in-php.html) como uma linguagem de templates.
Templates compilados, como [Twig](http://twig.sensiolabs.org/) ou [Smarty](http://www.smarty.net/)*, preenchem este 
vazio oferecendo uma nova sintaxe que foi direcionada especificamente para templating. De escape automático, à herança 
e estruturas de controle simplificadas, templates compilados são projetados para ser mais fácil de escrever, simples de 
ler e mais seguro de usar.
Templates compilados pode ser até compartilhados entre diferentes linguagens, [Mustache](http://mustache.github.io/) 
vem sendo um bom exemplo disso. Uma vez que esses templates devem ser compilados há uma pequena queda de performance, 
no entanto, este é mínimo quando o cache apropriado é usado.

** Enquanto Smarty oferece escape automático, este recurso NÃO está habilitado por padrão.*

### Exemplo simples de um template compilado

Utilizando a biblioteca [Twig](http://twig.sensiolabs.org/).

{% highlight html+jinja %}
{% raw %}
{% include 'header.html' with {'title': 'User Profile'} %}

<h1>User Profile</h1>
<p>Hello, {{ name }}</p>

{% include 'footer.html' %}
{% endraw %}
{% endhighlight %}

### Exemplo de templates compilados usando herança

Utilizando a biblioteca [Twig](http://twig.sensiolabs.org/).

{% highlight html+jinja %}
{% raw %}
// template.php

<html>
<head>
    <title>{% block title %}{% endblock %}</title>
</head>
<body>

<main>
    {% block content %}{% endblock %}
</main>

</body>
</html>
{% endraw %}
{% endhighlight %}

{% highlight text %}
{% raw %}
// user_profile.php

{% extends "template.html" %}

{% block title %}User Profile{% endblock %}
{% block content %}
    <h1>User Profile</h1>
    <p>Hello, {{ name }}</p>
{% endblock %}
{% endraw %}
{% endhighlight %}