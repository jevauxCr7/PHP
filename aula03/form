<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <script src="script.js" defer></script>
    <title>Formulario</title>
</head>
<body>
    <?php
        $cidadesEstados = array(
            "AC" => array("Rio Branco", "Cruzeiro do Sul", "Sena Madureira", "Tarauacá"),
            "AL" => array("Maceió", "Arapiraca", "Palmeira dos Índios", "Rio Largo"),
            "AP" => array("Macapá", "Santana", "Laranjal do Jari", "Oiapoque"),
            "AM" => array("Manaus", "Parintins", "Itacoatiara", "Manacapuru"),
            "BA" => array("Salvador", "Feira de Santana", "Vitória da Conquista", "Camaçari"),
            "CE" => array("Fortaleza", "Caucaia", "Juazeiro do Norte", "Sobral"),
            "DF" => array("Brasília"),
            "ES" => array("Vitória", "Vila Velha", "Serra", "Cariacica"),
            "GO" => array("Goiânia", "Aparecida de Goiânia", "Anápolis", "Rio Verde"),
            "MA" => array("São Luís", "Imperatriz", "Timon", "Caxias"),
            "MT" => array("Cuiabá", "Várzea Grande", "Rondonópolis", "Sinop"),
            "MS" => array("Campo Grande", "Dourados", "Três Lagoas", "Corumbá"),
            "MG" => array("Belo Horizonte", "Uberlândia", "Contagem", "Juiz de Fora"),
            "PA" => array("Belém", "Ananindeua", "Santarém", "Marabá"),
            "PB" => array("João Pessoa", "Campina Grande", "Santa Rita", "Patos"),
            "PR" => array("Curitiba", "Londrina", "Maringá", "Ponta Grossa"),
            "PE" => array("Recife", "Jaboatão dos Guararapes", "Olinda", "Caruaru"),
            "PI" => array("Teresina", "Parnaíba", "Picos", "Floriano"),
            "RJ" => array("Rio de Janeiro", "São Gonçalo", "Duque de Caxias", "Nova Iguaçu"),
            "RN" => array("Natal", "Mossoró", "Parnamirim", "Caicó"),
            "RS" => array("Porto Alegre", "Caxias do Sul", "Pelotas", "Santa Maria"),
            "RO" => array("Porto Velho", "Ji-Paraná", "Ariquemes", "Vilhena"),
            "RR" => array("Boa Vista", "Rorainópolis", "Caracaraí", "Alto Alegre"),
            "SC" => array("Florianópolis", "Joinville", "Blumenau", "Chapecó"),
            "SP" => array("São Paulo", "Campinas", "Guarulhos", "Santos"),
            "SE" => array("Aracaju", "Nossa Senhora do Socorro", "Lagarto", "Itabaiana"),
            "TO" => array("Palmas", "Araguaína", "Gurupi", "Porto Nacional")
        );
    ?>
    <form id='f' name='f' method='post' action='tabela.php' id = "filtro">
            <label for="nome" >Nome:</label>
            <input type="text" name="nome" value="<?= isset($_POST['nome'])?$_POST['nome']:"" ?>">
            <label for="idade">Idade:</label>
            <input type="number" name="idade" value="<?= isset($_POST['idade'])?$_POST['idade']:"" ?>">
            <label for="estado">Estado:</label>
            <select name="estado" id="estado">
                <?php
                    foreach($cidadesEstados as $chave => $valor){
                        echo "<option value='" . $chave . "' ";
                        if(isset($_POST["estado"]) && $_POST["estado"] == $chave){
                            echo "selected";
                        }
                        echo ">". $chave . "</option>";
                    }                    
                ?>
            </select>
            <label for="cidade">Cidade:</label>
            <select name="cidade" id="cidade">
                <?php
                if(!empty($_POST["estado"])){
                    foreach($cidadesEstados[$_POST["estado"]] as $chave => $valor){
                        echo "<option value='" . $valor . "'>" . $valor . "</option>";
                    }
                } 
                ?>
            </select>
            <button type="submit" id="Filtar" name="Filtrar">Filtrar</button>
        </form>
</body>
</html>
