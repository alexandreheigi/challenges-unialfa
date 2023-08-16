#### Dentro do login.php:

~~~php
if ($_POST) {
        session_start();

        $login = $_POST["login"] ?? NULL;
        $senha = $_POST["senha"] ?? NULL;


        if(isset($login) && isset($senha)){
            $_SESSION["usuario"] = array(
                "login" => $login,
                "senha" =>$senha
            );
        }

        echo "<script>location.href='index.php'</script>";
        exit;
    }
?>
~~~

~~~html
<!DOCTYPE html>
<html lang="pt_br">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Login</title>
    <link href="vendor/fontawesome-free/css/all.min.css" rel="stylesheet" type="text/css">
    <link href="vendor/datatables/dataTables.bootstrap4.min.css" rel="stylesheet" type="text/css">
    <link href="https://fonts.googleapis.com/css?family=Nunito:200,200i,300,300i,400,400i,600,600i,700,700i,800,800i,900,900i"
    rel="stylesheet">
    <link href="css/sb-admin-2.min.css" rel="stylesheet">
    <link rel="stylesheet" type="text/css" href="css/style.css">
    <link rel="stylesheet" type="text/css" href="css/lightbox.min.css">

    <link rel="stylesheet" type="text/css" href="vendor/summernote/summernote.min.css">
    <link rel="stylesheet" type="text/css" href="vendor/summernote/summernote-bs4.min.css">
    <link rel="stylesheet" href="css/sweetalert2.min.css"></script>
</head>
<body>
<div class="login">
    <h1 class="text-center">Faça Login</h1>
    <form method="post">
        <label for="login">Login:</label>
        <input type="text" name="login" id="login" class="form-control" 
        required placeholder="Preencha esse campo">

        <br>

        <label for="senha">Senha:</label>
        <input type="password" name="senha" id="senha" class="form-control" 
        required placeholder="Preencha esse campo">

        <br>

        <button type="submit" class="btn btn-primary w-100">Fazer Login</button>
    </form>
</div>
</body>
</html>
~~~

#### Dentro do index.php

~~~php
<title>Login</title>
<?php
session_start();

if (isset($_SESSION['usuario'])) {
    $login = $_SESSION['usuario']['login'];
    $senha = $_SESSION['usuario']['senha'];

    echo "Login e senha:";
    echo "<br>";
    print_r($login);
    echo "<br>";
    print_r($senha);
    exit;
}
    echo "Login e senha não existem.";
?>
~~~