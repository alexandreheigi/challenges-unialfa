# ex6
    

´´´php

    $servidor = "localhost";
    $usuario  = "root";
    $senha    = "";
    $banco    = "ex6";

    try {
        $pdo = new PDO("mysql:host={$servidor};dbname={$banco};port=3306;charset=utf8;",$usuario,$senha);
        echo "Login efetuado com sucesso!";
    } catch (Exception $e) {
        echo "<p>Erro ao tentar conectar</p>";
        echo $e->getMessage();
    }

´´´

