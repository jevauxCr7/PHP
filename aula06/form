<!DOCTYPE html>
<html>
<head>
    <title>Aula 06</title>
    <script src="script.js" defer></script>
</head>
<body>
    <h1>Aula do dia 17/12</h1>
    <fieldset>
        <legend>Formulário</legend>
        <form action="tabela.php" method="post" id="filtro">
            <label for="categoria">Categoria:</label>
            <br>
            <select id="categoria" name="categoria" >
            <option value="">Escolha a sua categoria:</option>
                <?php
                    $categorias = array(
                        "MA" => "Mamíferos",
                        "AV" => "Aves",
                        "BA" => "Bactérias"
                    );
                    foreach($categorias as $chave => $valor){
                        if($chave == $_POST['categorias']){
                            echo "<option value ='" . $chave ."' selected>" . $valor . "</option>";
                        }
                        else{
                            echo "<option value ='" . $chave ."'>" . $valor . "</option>";
                        }
                    }
                ?>
            </select>
            <div id="caixaTipo">
                <br>
                <label for="tipo">Tipos:</label>
                <br>
                <select id="tipo" name="tipo">
                </select>
                <br>
            </div>
            <br>
            <button type="submit" id="Filtrar" name="Filtrar">Filtrar</button>
        </form>
    </fieldset>
</body>
</html>
