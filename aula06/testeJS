const pegaValorCategoria = () => document.getElementById("categoria").value;
const pegaCaixaTipo = document.getElementById("caixaTipo");
document.addEventListener("DOMContentLoaded",()=>{
    let selectCategoria = document.getElementById("categoria");
    pegaCaixaTipo.style = "display: none";
    selectCategoria.addEventListener("change", carregaTipos);
});
let criaOptionsTipos = (resposta) =>{
    let selectTipo = document.getElementById("tipo");
    limpaSelect(selectTipo);
    console.log(resposta);
    for(let tipo of resposta){
        let optionTip = document.createElement("option");
        optionTip.setAttribute("value", tipo);
        optionTip.textContent = tipo;
        selectTipo.appendChild(optionTip);
    }
}
function limpaSelect(campo){
    let opt;
    while(opt = campo.firstChild){
        campo.removeChild(opt);
    }
}
function carregaTipos(){
    pegaCaixaTipo.style = "display: block";
    let formulario = new FormData();
    formulario.append("categoria",pegaValorCategoria());
    fetch("http://localhost/christinedesenvolvimentoweb/aula06/tipos.php",{
        mode: 'no-cors',
        method:"POST", headers:{"content-type":"application-json",  "Access-Control-Allow-Origin": 'origin-list'},body:formulario})
        .then(async resposta=>{
            let tipos=await resposta.json();
            criaOptionsTipos(tipos);
        })
        .catch(error=>console.log(error));
}
