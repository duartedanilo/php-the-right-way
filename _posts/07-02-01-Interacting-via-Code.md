---
isChild: true
title: Interagindo com o banco de dados
anchor: interagindo_com_o_banco_de_dados
---

## Interagindo com o banco de dados {#interagindo_com_o_banco_de_dados_title}

Quando os desenvolvedores começam a aprender PHP, muitas vezes acabam misturando a interação com o banco de dados com a 
camada de apresentação, usando código que pode parecer com isso:

{% highlight php %}
<ul>
<?php
foreach ($db->query('SELECT * FROM table') as $row) {
    echo "<li>".$row['field1']." - ".$row['field1']."</li>";
}
?>
</ul>
{% endhighlight %}

Esta é uma má prática por várias razões, principalmente por ser difícil de depurar, testar, ler e ainda pode gerar na 
saída um monte de campos se não houver um limite.

Embora existam muitas outras soluções para fazer isso - dependendo se você preferir a 
[OOP](/#programacao_orientada_objetos) ou [programação funcional](/#programacao_funcional) - deve haver algum elemento 
de separação.

Considere o passo mais básico:

{% highlight php %}
<?php
function getAllFoos($db) {
    return $db->query('SELECT * FROM table');
}

foreach (getAllFoos($db) as $row) {
    echo "<li>".$row['field1']." - ".$row['field1']."</li>"; // BAD!!
}
{% endhighlight %}

Este é um bom começo. Coloque estes dois itens em dois arquivos diferentes e você terá alguma separação limpa.

Crie uma classe para colocar este método e você terá um "Modelo". Criando um arquivo `.php` simples para colocar a 
lógica de apresentação e você terá uma "View", que é quase um [MVC] - uma arquitura OOP comum para a maioria dos 
[frameworks](/#frameworks).

**foo.php**

{% highlight php %}
<?php
$db = new PDO('mysql:host=localhost;dbname=testdb;charset=utf8', 'username', 'password');

// Deixe seu modelo disponível
include 'models/FooModel.php';

// Crie uma instância
$fooList = new FooModel($db);

// Mostre a view
include 'views/foo-list.php';
{% endhighlight %}


**models/FooModel.php**

{% highlight php %}
<?php
class Foo()
{
    protected $db;

    public function __construct(PDO $db)
    {
        $this->db = $db;
    }

    public function getAllFoos() {
        return $this->db->query('SELECT * FROM table');
    }
}
{% endhighlight %}

**views/foo-list.php**

{% highlight php %}
<?php foreach ($fooList as $row): ?>
    <?= $row['field1'] ?> - <?= $row['field1'] ?>
<?php endforeach ?>
{% endhighlight %}

Isto é essenciamente o mesmo que a maioria dos frameworks modernos fazem, todos sejam eles um pouco mais manual. Você 
pode não precisar de tudo a todo momento, mas misturando muita lógica de apresentação e interação com o banco de dados 
pode ser um problema real se você quiser [testes unitários](/#testes_unitarios) em sua aplicação.

[MVC]: http://code.tutsplus.com/tutorials/mvc-for-noobs--net-10488