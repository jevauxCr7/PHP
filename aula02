<?php

$formulario = array(
    'id'=>'formCadastro',
    'tipo_submit'=>'POST', 
    'url_submit'=>'cadastro.php', 
    'itens'=> array(
        'nome'=>array('tipo'=> 'text', 'nome'=> 'nome', 'label'=> 'Nome', 'placeholder'=> 'Informe seu nome.'),
        'idade'=>array('tipo'=> 'number', 'nome'=> 'idade', 'label'=> 'Idade', 'placeholder'=> 'Informe sua idade.', 'funcao_validacao'=> 'validaIdade'),
        'sexo'=>array('tipo'=> 'radio', 'nome'=> 'sexo', 'label'=> 'Sexo', 'opcoes'=> array("M"=> "Masculino", "F"=>"Feminino", "O"=>"Outros")),
        'esporte_preferido'=>array('tipo'=> 'checkbox', 'nome'=> 'esporte_preferido', 'label'=> 'Esporte Pref.', 'opcoes'=> array("F"=> "Futebol", "V"=>"Vôlei", "N"=>"Natação", "O"=> "Outros"), 'obrigatorio'=>false),
        'cidade_nascimento'=>array('tipo'=> 'text', 'nome'=> 'cidade', 'label'=> 'Cidade de Nasc.', 'placeholder'=> 'Informe a cidade que você nasceu.'),
        'estado_nascimento'=>array('tipo'=> 'select', 'nome'=> 'estado_nascimento', 'label'=> 'Estado de Nasc.', 'opcoes'=> array("RJ"=> "Rio de Janeiro", "SP"=>"São Paulo", "ES"=>"Espírito Santo", "MG"=>"Minas Gerais", "O"=> "Outros")),
        'cpf'=>array('tipo'=> 'number', 'nome'=> 'cpf', 'label'=> 'CPF', 'placeholder'=> 'Informe seu CPF.', 'funcao_validacao'=> 'validaCpf'),
        'botao_enviar'=>array('tipo'=> 'submit', 'nome'=> 'enviar', 'label'=> 'Enviar'),
        'botao_limpar_form'=>array('tipo'=> 'reset', 'nome'=> 'reset', 'label'=> 'Limpar Formulário'),
    )
);
function criarFormulario($formulario) {
    echo "<form id='" . $formulario['id'] . "' action='" . $formulario['url_submit'] . "' method='" . $formulario['tipo_submit'] . "'>";
    foreach ($formulario['itens'] as $id => $item) {
        criarCampo($id, $item);
    }
    echo "</form>";
}

function criarCampo($id, $item) {
    echo "<div>";
    echo "<label for='$id'>" . $item['label'] . ":</label>";
    switch ($item['tipo']) {
        case 'text':
        case 'number':
            criarInputText($id, $item);
            break;
        case 'textarea':
            criarTextarea($id, $item);
            break;
        case 'radio':
        case 'checkbox':
            criarRadioCheckbox($id, $item);
            break;
        case 'select':
            criarSelect($id, $item);
            break;
        case 'submit':
        case 'reset':
            criarBotao($id, $item);
            break;
    }
    echo "</div>";
}

function criarInputText($id, $item) {
    $placeholder = '';
    if (isset($item['placeholder'])) {
        $placeholder = $item['placeholder'];
    }
    $valorPadrao = '';
    if (isset($item['valor_padrao'])) {
        $valorPadrao = $item['valor_padrao'];
    }
    echo "<input type='" . $item['tipo'] . "' id='$id' name='" . $item['nome'] . "' placeholder='$placeholder' value='$valorPadrao' required />";
}

function criarTextarea($id, $item) {
    $placeholder = '';
    if (isset($item['placeholder'])) {
        $placeholder = $item['placeholder'];
    }
    $valorPadrao = '';
    if (isset($item['valor_padrao'])) {
        $valorPadrao = $item['valor_padrao'];
    }
    echo "<textarea id='$id' name='" . $item['nome'] . "' placeholder='$placeholder'>$valorPadrao</textarea>";
}

function criarSelect($id, $item) {
    $valorPadrao = '';
    if (isset($item['valor_padrao'])) {
        $valorPadrao = $item['valor_padrao'];
    }
    echo "<select id='$id' name='" . $item['nome'] . "'>";
    foreach ($item['opcoes'] as $valor => $texto) {
        $selected = '';
        if ($valor == $valorPadrao) {
            $selected = 'selected';
        }
        echo "<option value='$valor' $selected>$texto</option>";
    }
    echo "</select>";
}

function criarBotao($id, $item) {
    echo "<button type='" . $item['tipo'] . "' id='$id' name='" . $item['nome'] . "'>" . $item['label'] . "</button>";
}

function criarRadioCheckbox($id, $item) {
    $valorPadrao = [];
    if (isset($item['valor_padrao'])) {
        $valorPadrao = (array)$item['valor_padrao'];
    }
    foreach ($item['opcoes'] as $valor => $texto) {
        $checked = '';
        if (in_array($valor, $valorPadrao)) {
            $checked = 'checked';
        }
        echo "<input type='" . $item['tipo'] . "' id='{$id}_$valor' name='" . $item['nome'] . "' value='$valor' $checked />";
        echo "<label for='{$id}_$valor'>$texto</label>";
    }
}

criarFormulario($formulario);
?>
