#Desafio 02 exercicio 01

*criado o arquivo exceldesafio.php:
    - linha 3 - criado a variavel "dados" com nome/sobrenome/idade;
    - linha 5 a 10 - criado a variavel "pessoa" e alimentada com os dados;
    - linha 12 - criado a variavel "arquivo" e chamada a função fopen para criar um arquivo de planilha;
    - linha 14 - chamada a função fputcsv para inserir os "dados" no "arquivo";
    - linha 16 - usado o foreach para alimentar os dados da "pessoa" no "arquivo"
    - linha 20 - função fclose para finalizar



<?php

$dados = ["nome", "sobrenome","idade"];

$pessoa = [
    ['nome'=>"Alexandre", 'sobrenome'=>"Heigi", 'idade'=>"41"],
    ['nome'=>"Gabriel", 'sobrenome'=>"Heigi", 'idade'=>"14"],
    ['nome'=>"Maria Clara", 'sobrenome'=>"Yumi", 'idade'=>"6"],
    ['nome'=>"Erika", 'sobrenome'=>"Araujo", 'idade'=>"41"],
];

$arquivo = fopen("file.csv", "w");

fputcsv($arquivo, $dados, ";");

foreach($pessoa as $p){
    fputcsv($arquivo, $p, ";");
}

fclose($arquivo);
    


?>


