# DESAFIO 3

* Iniciado o PHP
* criado uma variavel mensagem e o texto a ser criptografado
* criado uma variavel encripted e chamado a extenção sodium para criptografar em hexadecimal
* usando o echo para imprimir a mensagem
* criado outra variavel descripted e chamado o sodium para descriptografar a mensagem


### Código

```php

    $mensagem = "Alexandre Heigi";
    echo $mensagem;

    echo '<br>';

    $encripted = sodium_bin2hex($mensagem);
    echo $encripted;

    echo '<br>';

    $descripted = sodium_hex2bin($encripted);
    echo $descripted;
 ```


