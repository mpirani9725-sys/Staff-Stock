
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Portal Restaurante</title>
<style>
/* ESTILO GERAL */
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:Arial,Helvetica,sans-serif
}
body{
    min-height:100vh;
    padding:20px;
    display:flex;
    color:#222;
    background:linear-gradient(135deg,#1993b2,#084c01)
}
.container{width:100%;
    max-width:1500px;
    margin:auto;
    display:flex;
    gap:20px;
    min-height:calc(100vh - 40px)
}

/* MENU */
.menu{
    flex:0 0 250px;
    padding:20px;
    color:#fff;
    background:#084c01;
    border-radius:12px
}
.menu h2{
    text-align:center;
    margin-bottom:20px
}
.menu button{
    width:100%;
    padding:12px;
    margin-bottom:10px;
    border:0;
    border-radius:5px;
    background:#149b02;
    color:#fff;
    font-weight:bold;
    cursor:pointer;
    transition:.3s
}
.menu button:hover{
    background:#b7d304;
    color:#000
}
/* CONTEÚDO */
.conteudo{
    flex:1;
    min-width:0;
    padding:20px;
    overflow:auto
}
.tela{
    display:none
}
.tela.ativa{
    display:block
}
h1{
    color:#fff;
    text-align:center;
    margin-bottom:12px
}
h2,h3{
    margin-bottom:12px
}
.descricao{
    color:#fff;
    margin-bottom:18px
}
/* CARDS E FORMULÁRIOS */
.cards,.resumo{
    display:grid;
    grid-template-columns:repeat(auto-fit,minmax(200px,1fr));
    gap:20px;
    margin:20px 0 30px
}
.card,.box,.formulario{
    background:#fff;
    color:#111;
    padding:20px;
    border-radius:12px;
    margin-bottom:20px;
    box-shadow:0 4px 12px rgba(0,0,0,.2)
}
.card{
    text-align:center;
    transition:.3s
}
.card.clicavel{
    cursor:pointer
}
.card.clicavel:hover{
    transform:translateY(-5px);
    background:#13b8ff;
    color:#fff
}

.card h2,.card h3{font-size:18px}.card p,.valor{font-size:23px;font-weight:bold}
.form-grid,.grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(180px,1fr));gap:12px;align-items:end}
label{display:block;font-weight:bold;margin-bottom:5px}
input,select,textarea{width:100%;min-width:0;margin-top:8px;padding:11px;border:1px solid #ccc;border-radius:7px;font-size:15px}
textarea{min-height:42px;resize:vertical}
button{border:0;border-radius:7px;padding:10px 15px;cursor:pointer;font-weight:bold;transition:.3s}
button:hover{filter:brightness(.92)}
.cadastrar,.btn-add,.btn-green,.entrada{background:#149b02;color:#fff}
.cadastrar{width:100%;padding:12px;margin-top:15px;font-size:16px}
.btn-blue,.btn,.btn-edit{background:#007bff;color:#fff}
.btn-red,.btn-delete,.saida,.delete{background:#dc3545;color:#fff}
.btn-yellow{background:#ffc107;color:#222}
.entrada,.saida,.delete{padding:10px;border-radius:5px}
.acoes{display:flex;flex-wrap:wrap;gap:7px}
/* TABELAS */
.table-container{width:100%;overflow-x:auto}
table{width:100%;margin-top:18px;border-collapse:collapse;background:#fff;color:#111}
th,td{padding:11px;border:1px solid #ddd;text-align:center;vertical-align:middle}
th{background:#007bff;color:#fff}
.baixo{background:#ffb3b3;color:#b30000;font-weight:bold}
.medio{background:#fff3cd;color:#856404;font-weight:bold}
.alto{background:#c3f7d0;color:#155724;font-weight:bold}
/* RELÓGIO E STATUS */
#relogio{font-size:20px;font-weight:bold;color:#fff;margin:15px 0}
.status{display:inline-block;padding:6px 10px;border-radius:15px;font-weight:bold}
.livre{background:#c8f9cc;color:#087f23}.ocupada{background:#ffd1d1;color:#b30000}.reservada{background:#fff0a8;color:#8a6d00}
/* MESAS */
.mesas-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(230px,1fr));gap:18px}
.mesa-card{background:#fff;border-radius:14px;padding:20px;border-top:8px solid #149b02;box-shadow:0 4px 12px rgba(0,0,0,.2)}
.mesa-card.ocupada-card{border-top-color:#dc3545}.mesa-card.reservada-card{border-top-color:#ffc107}
.mesa-numero{font-size:25px;font-weight:bold;margin-bottom:10px}.mesa-info{margin:7px 0}
.mesa-acoes{display:flex;flex-wrap:wrap;gap:7px;margin-top:15px}.mesa-acoes button{flex:1;min-width:100px}
.vazio{padding:18px;text-align:center;color:#555}
@media(max-width:800px){body{padding:10px}.container{flex-direction:column}.menu{flex-basis:auto}.menu button{width:calc(50% - 7px);margin-right:5px}.conteudo{padding:10px}}
@media(max-width:600px){h1{font-size:21px}.cards,.resumo{grid-template-columns:1fr}table{font-size:12px}th,td{padding:7px}.menu button{width:100%;margin-right:0}}
</style>
</head>
<body>
<div class="container">
<!-- MENU PRINCIPAL -->
<aside class="menu">
<h2>🍽 Restaurante</h2>
<button onclick="mostrarTela('dashboard')">Dashboard</button>
<button onclick="mostrarTela('estoque')">Estoque</button>
<button onclick="mostrarTela('funcionarios')">Funcionários</button>
<button onclick="mostrarTela('controle')">Controle de Ponto</button>
<button onclick="mostrarTela('rh')">RH</button>
<button onclick="mostrarTela('mesas')">Mesas</button>
<button onclick="mostrarTela('pedidos')">Pedidos</button>
<button onclick="mostrarTela('reciclados')">Alimentos Reciclados</button>
<button onclick="mostrarTela('relatorios')">Relatórios</button>
</aside>

<main class="conteudo">
<!-- DASHBOARD -->
<section id="dashboard" class="tela ativa">
<h1>🏪 Portal do Restaurante</h1>
<div class="cards">
<div class="card clicavel" onclick="mostrarTela('controle')"><h2>⏰ Controle de Ponto</h2><p>Registro de entrada e saída</p></div>
<div class="card clicavel" onclick="mostrarTela('funcionarios')"><h2>👨‍🍳 Funcionários</h2><p>Cadastro completo</p></div>
<div class="card clicavel" onclick="mostrarTela('estoque')"><h2>📦 Estoque</h2><p>Controle de produtos</p></div>
<div class="card clicavel" onclick="mostrarTela('mesas')"><h2>🪑 Mesas</h2><p>Status das mesas</p></div>
<div class="card clicavel" onclick="mostrarTela('pedidos')"><h2>🧾 Pedidos</h2><p>Controle de pedidos</p></div>
<div class="card clicavel" onclick="mostrarTela('reciclados')"><h2>♻️ Alimentos Reciclados</h2><p>Controle de desperdícios</p></div>
<div class="card clicavel" onclick="mostrarTela('relatorios')"><h2>📊 Relatórios</h2><p>Resumo do restaurante</p></div>
</div>
</section>

<!-- ESTOQUE -->
<section id="estoque" class="tela">
<h1>📦 Estoque</h1><p class="descricao">Cadastro e acompanhamento dos produtos.</p>
<div class="cards">
<div class="card"><h2>Total de Produtos</h2><p id="totalProdutos">0</p></div>
<div class="card"><h2>Itens em Baixa</h2><p id="baixoEstoque">0</p></div>
<div class="card"><h2>Valor Total</h2><p id="valorTotal">R$ 0,00</p></div>
</div>
<div class="formulario"><h2>Cadastro de Produto</h2><div class="form-grid">
<input id="produto" placeholder="Nome do Produto">
<input id="quantidade" type="number" min="0" placeholder="Quantidade">
<input id="preco" type="number" min="0" step="0.01" placeholder="Preço Unitário">
<select id="categoria"><option value="">Categoria</option><option>Bebidas</option><option>Carnes</option><option>Massas</option><option>Hortifruti</option><option>Limpeza</option><option>Outros</option></select>
<button class="btn-add" onclick="adicionarProduto()">➕ Adicionar Produto</button>
</div></div>
<div class="table-container"><table><thead><tr><th>Produto</th><th>Categoria</th><th>Quantidade</th><th>Preço</th><th>Total</th><th>Status</th><th>Ações</th></tr></thead><tbody id="tabelaProdutos"></tbody></table></div>
</section>

<!-- CONTROLE DE PONTO -->
<section id="controle" class="tela">
<h1>⏰ Controle de Ponto</h1><div id="relogio"></div>
<div class="formulario"><div class="form-grid">
<input id="nomePonto" placeholder="Nome do funcionário"><input id="funcaoPonto" placeholder="Função">
<button class="entrada" onclick="registrar('entrada')">Registrar Entrada</button><button class="saida" onclick="registrar('saida')">Registrar Saída</button>
</div></div>
<div class="table-container"><table><thead><tr><th>Nome</th><th>Função</th><th>Data</th><th>Entrada</th><th>Saída</th><th>Total (Horas)</th><th>Ação</th></tr></thead><tbody id="tabelaPonto"></tbody></table></div>
</section>

<!-- FUNCIONÁRIOS -->
<section id="funcionarios" class="tela">
<h1>👨‍🍳 Cadastro de Funcionários</h1>
<div class="formulario"><div class="form-grid">
<input id="nomeFuncionario" placeholder="Nome"><input id="cargo" placeholder="Cargo"><input id="telefone" placeholder="Telefone">
<input id="salarioFuncionario" type="number" min="0" step="0.01" placeholder="Salário">
<select id="statusFuncionario"><option value="Ativo">✔️ Ativo</option><option value="Desativado">❌ Desativado</option></select>
</div><button class="cadastrar" onclick="cadastrarFuncionario()">Cadastrar Funcionário</button></div>
<div class="table-container"><table><thead><tr><th>Nome</th><th>Cargo</th><th>Telefone</th><th>Salário</th><th>Status</th><th>Ações</th></tr></thead><tbody id="tabelaFuncionarios"></tbody></table></div>
</section>

<!-- RH / 13º SALÁRIO -->
<section id="rh" class="tela">
<h1>🏢 Recursos Humanos</h1>
<div class="card"><h2>Cadastro / Cálculo do 13º Salário</h2><div class="grid">
<div><label for="funcionario13">Funcionário</label><input id="funcionario13" placeholder="Nome"></div>
<div><label for="salario13">Salário / remuneração considerada</label><input id="salario13" type="number" min="0" step="0.01"></div>
<div><label for="ano13">Ano</label><input id="ano13" type="number" value="2026"></div>
<div><label for="admissao13">Data de admissão</label><input id="admissao13" type="date"></div>
<div><label for="avos13">Avos considerados</label><input id="avos13" type="number" min="0" max="12" value="12"></div>
<div><label for="descontos13">Descontos</label><input id="descontos13" type="number" min="0" step="0.01" value="0"></div>
</div><div class="acoes" style="margin-top:15px"><button class="btn-green" onclick="calcular13()">Calcular 13º</button><button class="btn-blue" onclick="salvar13()">Salvar</button><button class="btn-yellow" onclick="limpar13()">Limpar</button></div><div id="resultado13" style="margin-top:15px"></div></div>
<div class="card"><h2>Histórico</h2><div class="table-container"><table><thead><tr><th>Funcionário</th><th>Ano</th><th>Avos</th><th>Bruto</th><th>Descontos</th><th>Líquido</th><th>Status</th></tr></thead><tbody id="tabela13"></tbody></table></div></div>
</section>

<!-- MESAS -->
<section id="mesas" class="tela">
<h1>🪑 Controle de Mesas</h1>
<div class="cards">
<div class="card"><h3>🟢 Mesas Livres</h3><p id="totalMesasLivres">0</p></div>
<div class="card"><h3>🔴 Mesas Ocupadas</h3><p id="totalMesasOcupadas">0</p></div>
<div class="card"><h3>🟡 Reservadas</h3><p id="totalMesasReservadas">0</p></div>
<div class="card"><h3>💰 Faturamento em aberto</h3><p id="faturamentoMesas">R$ 0,00</p></div>
</div>
<div class="box"><h2>🪑 Cadastro / Edição de Mesa</h2><div class="form-grid">
<div><label for="numeroMesa">Número da mesa</label><input id="numeroMesa" type="number" min="1"></div>
<div><label for="clienteMesa">Nome do cliente</label><input id="clienteMesa" placeholder="Nome do cliente"></div>
<div><label for="pessoasMesa">Quantidade de pessoas</label><input id="pessoasMesa" type="number" min="1"></div>
<div><label for="valorMesa">Valor da conta</label><input id="valorMesa" type="number" min="0" step="0.01" value="0"></div>
<div><label for="statusMesa">Status</label><select id="statusMesa"><option value="livre">🟢 Livre</option><option value="ocupada">🔴 Ocupada</option><option value="reservada">🟡 Reservada</option></select></div>
<button class="btn-green" onclick="salvarMesa()">Salvar Mesa</button><button class="btn" onclick="limparMesaForm()">Limpar</button>
</div></div>
<div class="box"><h2>Mesas do Restaurante</h2><div id="mesasGrid" class="mesas-grid"></div></div>
</section>

<!-- PEDIDOS -->
<section id="pedidos" class="tela">
<h1>🧾 Pedidos</h1>
<div class="cards">
<div class="card"><h3>🟡 Pendentes</h3><p id="pedidosPendentes">0</p></div>
<div class="card"><h3>🔵 Em preparo</h3><p id="pedidosPreparo">0</p></div>
<div class="card"><h3>🟢 Prontos</h3><p id="pedidosProntos">0</p></div>
<div class="card"><h3>💰 Total dos pedidos</h3><p id="totalPedidos">R$ 0,00</p></div>
</div>
<div class="box"><h2>🍽️ Novo Pedido</h2><div class="form-grid">
<div><label for="mesaPedido">Número da mesa</label><input id="mesaPedido" type="number" min="1" placeholder="Ex.: 5"></div>
<div><label for="clientePedido">Cliente</label><input id="clientePedido" placeholder="Nome do cliente"></div>
<div><label for="produtoPedido">Produto / Prato</label><input id="produtoPedido" placeholder="Ex.: Hambúrguer"></div>
<div><label for="quantidadePedido">Quantidade</label><input id="quantidadePedido" type="number" min="1" value="1"></div>
<div><label for="valorUnitarioPedido">Valor unitário</label><input id="valorUnitarioPedido" type="number" min="0" step="0.01" placeholder="0,00"></div>
<div><label for="statusPedido">Status</label><select id="statusPedido"><option value="Pendente">🟡 Pendente</option><option value="Em preparo">🔵 Em preparo</option><option value="Pronto">🟢 Pronto</option><option value="Entregue">🟣 Entregue</option></select></div>
</div><div class="acoes" style="margin-top:15px"><button class="btn-green" onclick="adicionarPedido()">➕ Adicionar Pedido</button><button class="btn" onclick="limparPedido()">Limpar</button></div></div>
<div class="box"><h2>📋 Pedidos registrados</h2><div class="table-container"><table><thead><tr><th>Pedido</th><th>Mesa</th><th>Cliente</th><th>Produto</th><th>Qtd.</th><th>Unitário</th><th>Total</th><th>Horário</th><th>Status</th><th>Ações</th></tr></thead><tbody id="tabelaPedidos"></tbody></table></div></div>
</section>

<!-- ALIMENTOS RECICLADOS -->
<section id="reciclados" class="tela">
<h1>♻️ Alimentos Reciclados</h1><p class="descricao">Registro de alimentos que não foram aproveitados.</p>
<div class="formulario"><div class="form-grid">
<input id="alimento" placeholder="Alimento"><input id="quantidadeReciclado" type="number" min="0.01" step="0.01" placeholder="Quantidade">
<select id="motivoReciclado"><option value="">Motivo</option><option>Pedido cancelado</option><option>Não consumido</option><option>Pedido devolvido</option><option>Validade</option><option>Outro</option></select>
<input id="mesaReciclado" placeholder="Mesa"><input id="funcionarioReciclado" placeholder="Funcionário"><textarea id="observacaoReciclado" placeholder="Observação"></textarea>
<button class="btn-add" onclick="registrarReciclado()">♻️ Registrar Alimento</button>
</div></div>
<div class="table-container"><table><thead><tr><th>Alimento</th><th>Quantidade</th><th>Motivo</th><th>Mesa</th><th>Funcionário</th><th>Data/Hora</th><th>Observação</th></tr></thead><tbody id="tabelaReciclados"></tbody></table></div>
</section>

<!-- RELATÓRIOS -->
<section id="relatorios" class="tela">
<h1>📊 Relatórios</h1><p class="descricao">Resumo das informações cadastradas no sistema.</p>
<div class="cards">
<div class="card"><h2>♻️ Registros de alimentos</h2><p id="relatorioReciclados">0</p></div>
<div class="card"><h2>📦 Produtos cadastrados</h2><p id="relatorioProdutos">0</p></div>
<div class="card"><h2>🧾 Pedidos registrados</h2><p id="relatorioPedidos">0</p></div>
<div class="card"><h2>👨‍🍳 Funcionários cadastrados</h2><p id="relatorioFuncionarios">0</p></div>
</div>
</section>
</main>
</div>

<script>
"use strict";

/* FUNÇÕES GERAIS */
function mostrarTela(id){
    document.querySelectorAll(".tela").forEach(tela=>tela.classList.remove("ativa"));
    const selecionada=document.getElementById(id);
    if(selecionada) selecionada.classList.add("ativa");
}
function moeda(valor){
    return Number(valor||0).toLocaleString("pt-BR",{style:"currency",currency:"BRL"});
}
function carregarLista(chave){
    try{return JSON.parse(localStorage.getItem(chave))||[];}
    catch(erro){console.warn("Falha ao carregar "+chave,erro);return [];}
}
function atualizarRelogio(){
    const el=document.getElementById("relogio");
    if(el){const agora=new Date();el.textContent="📅 "+agora.toLocaleDateString("pt-BR")+" ⏰ "+agora.toLocaleTimeString("pt-BR");}
}
setInterval(atualizarRelogio,1000);atualizarRelogio();

/* CONTROLE DE PONTO */
let registrosPonto=carregarLista("ponto");
function calcularHoras(entrada,saida){
    const [h1,m1,s1=0]=entrada.split(":").map(Number);
    const [h2,m2,s2=0]=saida.split(":").map(Number);
    let inicio=h1*3600+m1*60+s1,fim=h2*3600+m2*60+s2;
    if(fim<inicio)fim+=86400;
    return ((fim-inicio)/3600).toFixed(2);
}
function registrar(tipo){
    const nome=document.getElementById("nomePonto").value.trim();
    const funcao=document.getElementById("funcaoPonto").value.trim();
    if(!nome){alert("Digite o nome do funcionário.");return;}
    const agora=new Date(),data=agora.toLocaleDateString("pt-BR"),hora=agora.toLocaleTimeString("pt-BR");
    if(tipo==="entrada"){
        registrosPonto.push({nome,funcao,data,entrada:hora,saida:"",total:""});
    }else{
        const aberto=[...registrosPonto].reverse().find(r=>r.nome.toLowerCase()===nome.toLowerCase()&&!r.saida);
        if(!aberto){alert("Não foi encontrada uma entrada em aberto para esse funcionário.");return;}
        aberto.saida=hora;aberto.total=calcularHoras(aberto.entrada,hora);
    }
    localStorage.setItem("ponto",JSON.stringify(registrosPonto));renderizarPonto();
}
function deletarPonto(index){
    if(!confirm("Deseja excluir este registro?"))return;
    registrosPonto.splice(index,1);localStorage.setItem("ponto",JSON.stringify(registrosPonto));renderizarPonto();
}
function renderizarPonto(){
    const tabela=document.getElementById("tabelaPonto");if(!tabela)return;tabela.innerHTML="";
    if(!registrosPonto.length){tabela.innerHTML='<tr><td colspan="7" class="vazio">Nenhum registro de ponto.</td></tr>';return;}
    registrosPonto.forEach((r,i)=>{
        const tr=document.createElement("tr");
        [r.nome,r.funcao,r.data,r.entrada,r.saida||"-",r.total||"-"].forEach(v=>{const td=document.createElement("td");td.textContent=v;tr.appendChild(td);});
        const td=document.createElement("td"),btn=document.createElement("button");btn.className="btn-delete";btn.textContent="Excluir";btn.onclick=()=>deletarPonto(i);td.appendChild(btn);tr.appendChild(td);tabela.appendChild(tr);
    });
}

/* FUNCIONÁRIOS */
let funcionarios=carregarLista("funcionarios");
function cadastrarFuncionario(){
    const nome=document.getElementById("nomeFuncionario").value.trim();
    const cargo=document.getElementById("cargo").value.trim();
    const telefone=document.getElementById("telefone").value.trim();
    const salarioTexto=document.getElementById("salarioFuncionario").value;
    const salario=Number(salarioTexto),status=document.getElementById("statusFuncionario").value;
    if(!nome||!cargo||!telefone||salarioTexto===""||salario<0){alert("Preencha todos os campos corretamente.");return;}
    funcionarios.push({id:Date.now(),nome,cargo,telefone,salario,status});
    localStorage.setItem("funcionarios",JSON.stringify(funcionarios));renderizarFuncionarios();
    ["nomeFuncionario","cargo","telefone","salarioFuncionario"].forEach(id=>document.getElementById(id).value="");
    document.getElementById("statusFuncionario").value="Ativo";
}
function removerFuncionario(id){
    if(!confirm("Deseja remover este funcionário?"))return;
    funcionarios=funcionarios.filter(f=>f.id!==id);localStorage.setItem("funcionarios",JSON.stringify(funcionarios));renderizarFuncionarios();
}
function renderizarFuncionarios(){
    const tabela=document.getElementById("tabelaFuncionarios");if(!tabela)return;tabela.innerHTML="";
    if(!funcionarios.length)tabela.innerHTML='<tr><td colspan="6" class="vazio">Nenhum funcionário cadastrado.</td></tr>';
    funcionarios.forEach(f=>{
        const tr=document.createElement("tr");
        [f.nome,f.cargo,f.telefone,moeda(f.salario),f.status].forEach(v=>{const td=document.createElement("td");td.textContent=v;tr.appendChild(td);});
        const td=document.createElement("td"),btn=document.createElement("button");btn.className="btn-delete";btn.textContent="Excluir";btn.onclick=()=>removerFuncionario(f.id);td.appendChild(btn);tr.appendChild(td);tabela.appendChild(tr);
    });
    atualizarRelatorios();
}

/* ESTOQUE */
let estoque=carregarLista("estoque");
function statusEstoque(qtd){
    if(qtd<=5)return {texto:"BAIXO",classe:"baixo"};
    if(qtd<=15)return {texto:"MÉDIO",classe:"medio"};
    return {texto:"ALTO",classe:"alto"};
}
function adicionarProduto(){
    const produto=document.getElementById("produto").value.trim();
    const qtdTexto=document.getElementById("quantidade").value,precoTexto=document.getElementById("preco").value;
    const quantidade=Number(qtdTexto),preco=Number(precoTexto),categoria=document.getElementById("categoria").value;
    if(!produto||qtdTexto===""||precoTexto===""||!categoria||quantidade<0||preco<0){alert("Preencha todos os campos corretamente.");return;}
    estoque.push({id:Date.now(),produto,quantidade,preco,categoria});
    localStorage.setItem("estoque",JSON.stringify(estoque));
    ["produto","quantidade","preco","categoria"].forEach(id=>document.getElementById(id).value="");
    renderizarTabela();
}
function editarProduto(id){
    const item=estoque.find(p=>p.id===id);if(!item)return;
    const nome=prompt("Editar produto:",item.produto);if(nome===null)return;
    const qtd=prompt("Editar quantidade:",item.quantidade);if(qtd===null)return;
    const preco=prompt("Editar preço:",item.preco);if(preco===null)return;
    if(!nome.trim()||qtd.trim()===""||preco.trim()===""||!Number.isFinite(Number(qtd))||!Number.isFinite(Number(preco))||Number(qtd)<0||Number(preco)<0){alert("Dados inválidos.");return;}
    Object.assign(item,{produto:nome.trim(),quantidade:Number(qtd),preco:Number(preco)});
    localStorage.setItem("estoque",JSON.stringify(estoque));renderizarTabela();
}
function deletarProduto(id){
    if(!confirm("Deseja remover este produto?"))return;
    estoque=estoque.filter(p=>p.id!==id);localStorage.setItem("estoque",JSON.stringify(estoque));renderizarTabela();
}
function renderizarTabela(){
    const tabela=document.getElementById("tabelaProdutos");if(!tabela)return;tabela.innerHTML="";
    let valorTotal=0,baixo=0;
    if(!estoque.length)tabela.innerHTML='<tr><td colspan="7" class="vazio">Nenhum produto cadastrado.</td></tr>';
    estoque.forEach(p=>{
        const st=statusEstoque(Number(p.quantidade)),total=Number(p.quantidade)*Number(p.preco);valorTotal+=total;if(Number(p.quantidade)<=5)baixo++;
        const tr=document.createElement("tr");
        [p.produto,p.categoria,p.quantidade,moeda(p.preco),moeda(total)].forEach(v=>{const td=document.createElement("td");td.textContent=v;tr.appendChild(td);});
        const tdStatus=document.createElement("td");tdStatus.textContent=st.texto;tdStatus.className=st.classe;tr.appendChild(tdStatus);
        const td=document.createElement("td"),editar=document.createElement("button"),excluir=document.createElement("button");
        editar.className="btn-edit";editar.textContent="✏️";editar.onclick=()=>editarProduto(p.id);
        excluir.className="btn-delete";excluir.textContent="🗑️";excluir.onclick=()=>deletarProduto(p.id);
        td.append(editar,excluir);tr.appendChild(td);tabela.appendChild(tr);
    });
    document.getElementById("totalProdutos").textContent=estoque.length;
    document.getElementById("baixoEstoque").textContent=baixo;
    document.getElementById("valorTotal").textContent=moeda(valorTotal);atualizarRelatorios();
}

/* MESAS */
let mesas=carregarLista("mesas");
function inicializarMesas(){
    if(!mesas.length){for(let n=1;n<=10;n++)mesas.push({numero:n,cliente:"",pessoas:0,valor:0,status:"livre"});salvarMesas();}
}
function salvarMesas(){localStorage.setItem("mesas",JSON.stringify(mesas));}
function limparMesaForm(){
    ["numeroMesa","clienteMesa","pessoasMesa"].forEach(id=>document.getElementById(id).value="");
    document.getElementById("valorMesa").value="0";document.getElementById("statusMesa").value="livre";
}
function salvarMesa(){
    const nTexto=document.getElementById("numeroMesa").value,n=Number(nTexto);
    const cliente=document.getElementById("clienteMesa").value.trim(),pessoas=Number(document.getElementById("pessoasMesa").value)||0;
    const valor=Number(document.getElementById("valorMesa").value)||0,status=document.getElementById("statusMesa").value;
    if(!nTexto||n<1||valor<0){alert("Informe um número e um valor válidos.");return;}
    const mesa=mesas.find(m=>Number(m.numero)===n);
    if(mesa)Object.assign(mesa,{cliente,pessoas,valor,status});else mesas.push({numero:n,cliente,pessoas,valor,status});
    salvarMesas();limparMesaForm();renderizarMesas();
}
function abrirMesa(numero){
    const mesa=mesas.find(m=>Number(m.numero)===Number(numero));if(!mesa)return;
    const cliente=prompt("Nome do cliente:",mesa.cliente||"");if(cliente===null)return;
    const pessoasTexto=prompt("Quantidade de pessoas:",String(mesa.pessoas||1));if(pessoasTexto===null)return;
    const pessoas=Number(pessoasTexto);if(!Number.isInteger(pessoas)||pessoas<1){alert("Quantidade inválida.");return;}
    Object.assign(mesa,{status:"ocupada",cliente:cliente.trim(),pessoas});salvarMesas();renderizarMesas();
}
function fecharMesa(numero){
    const mesa=mesas.find(m=>Number(m.numero)===Number(numero));if(!mesa)return;
    const total=pedidos.filter(p=>Number(p.mesa)===Number(numero)&&p.status!=="Cancelado").reduce((s,p)=>s+Number(p.total||0),0);
    let valor=total;
    if(valor===0){const informado=prompt("Valor final da conta:",String(mesa.valor||0));if(informado===null)return;valor=Number(informado);}
    if(!Number.isFinite(valor)||valor<0){alert("Valor inválido.");return;}
    if(!confirm(`Fechar Mesa ${numero}?\n\nTotal: ${moeda(valor)}`))return;
    Object.assign(mesa,{valor:0,status:"livre",cliente:"",pessoas:0});
    salvarMesas();renderizarMesas();
}
function liberarMesa(numero){
    const mesa=mesas.find(m=>Number(m.numero)===Number(numero));if(!mesa)return;
    Object.assign(mesa,{status:"livre",cliente:"",pessoas:0,valor:0});salvarMesas();renderizarMesas();
}
function editarMesa(numero){
    const m=mesas.find(item=>Number(item.numero)===Number(numero));if(!m)return;
    document.getElementById("numeroMesa").value=m.numero;document.getElementById("clienteMesa").value=m.cliente;
    document.getElementById("pessoasMesa").value=m.pessoas;document.getElementById("valorMesa").value=m.valor;
    document.getElementById("statusMesa").value=m.status;mostrarTela("mesas");
}
function renderizarMesas(){
    const grid=document.getElementById("mesasGrid");if(!grid)return;grid.innerHTML="";
    mesas.forEach(m=>{
        const card=document.createElement("div");card.className="mesa-card";
        if(m.status==="ocupada")card.classList.add("ocupada-card");
        if(m.status==="reservada")card.classList.add("reservada-card");
        const status={livre:"🟢 Livre",ocupada:"🔴 Ocupada",reservada:"🟡 Reservada"}[m.status]||"Indefinido";
        card.innerHTML=`<div class="mesa-numero">🪑 Mesa ${Number(m.numero)}</div>
        <p class="mesa-info"><strong>Status:</strong> ${status}</p>
        <p class="mesa-info"><strong>Cliente:</strong> ${escapeHTML(m.cliente||"-")}</p>
        <p class="mesa-info"><strong>Pessoas:</strong> ${Number(m.pessoas)||0}</p>
        <p class="mesa-info"><strong>Conta:</strong> ${moeda(m.valor)}</p>
        <div class="mesa-acoes">
        ${m.status==="livre"?`<button class="btn-green" onclick="abrirMesa(${Number(m.numero)})">🔓 Abrir mesa</button>`:""}
        ${m.status==="ocupada"?`<button class="btn-red" onclick="fecharMesa(${Number(m.numero)})">💳 Fechar conta</button>`:""}
        ${m.status==="reservada"?`<button class="btn-green" onclick="liberarMesa(${Number(m.numero)})">Liberar</button>`:""}
        <button class="btn-blue" onclick="editarMesa(${Number(m.numero)})">✏️ Editar</button></div>`;
        grid.appendChild(card);
    });
    atualizarResumoMesas();
}
function atualizarResumoMesas(){
    document.getElementById("totalMesasLivres").textContent=mesas.filter(m=>m.status==="livre").length;
    document.getElementById("totalMesasOcupadas").textContent=mesas.filter(m=>m.status==="ocupada").length;
    document.getElementById("totalMesasReservadas").textContent=mesas.filter(m=>m.status==="reservada").length;
    const total=mesas.filter(m=>m.status==="ocupada").reduce((s,m)=>s+Number(m.valor||0),0);
    document.getElementById("faturamentoMesas").textContent=moeda(total);
}

/* PEDIDOS */
let pedidos=carregarLista("pedidos");
function salvarPedidos(){localStorage.setItem("pedidos",JSON.stringify(pedidos));}
function adicionarPedido(){
    const mesa=Number(document.getElementById("mesaPedido").value),cliente=document.getElementById("clientePedido").value.trim();
    const produto=document.getElementById("produtoPedido").value.trim(),quantidade=Number(document.getElementById("quantidadePedido").value);
    const valorTexto=document.getElementById("valorUnitarioPedido").value,valorUnitario=Number(valorTexto);
    const status=document.getElementById("statusPedido").value;
    if(!mesa||!produto||quantidade<=0||valorTexto===""||valorUnitario<0){alert("Preencha os dados do pedido corretamente.");return;}
    if(!mesas.some(m=>Number(m.numero)===mesa)){alert("Essa mesa não está cadastrada.");return;}
    pedidos.push({id:Date.now(),mesa,cliente,produto,quantidade,valorUnitario,total:quantidade*valorUnitario,status,horario:new Date().toLocaleTimeString("pt-BR",{hour:"2-digit",minute:"2-digit"})});
    salvarPedidos();atualizarValorMesa(mesa);limparPedido();renderizarPedidos();
}
function limparPedido(){
    document.getElementById("mesaPedido").value="";document.getElementById("clientePedido").value="";
    document.getElementById("produtoPedido").value="";document.getElementById("quantidadePedido").value="1";
    document.getElementById("valorUnitarioPedido").value="";document.getElementById("statusPedido").value="Pendente";
}
function atualizarValorMesa(numero){
    const mesa=mesas.find(m=>Number(m.numero)===Number(numero));if(!mesa)return;
    mesa.valor=pedidos.filter(p=>Number(p.mesa)===Number(numero)&&p.status!=="Cancelado").reduce((s,p)=>s+Number(p.total||0),0);
    salvarMesas();renderizarMesas();
}
function alterarStatusPedido(id,status){
    const p=pedidos.find(item=>item.id===id);if(!p)return;p.status=status;salvarPedidos();renderizarPedidos();atualizarValorMesa(p.mesa);
}
function cancelarPedido(id){
    const p=pedidos.find(item=>item.id===id);if(!p||["Entregue","Cancelado"].includes(p.status))return;
    if(!confirm("Deseja cancelar este pedido?"))return;p.status="Cancelado";salvarPedidos();renderizarPedidos();atualizarValorMesa(p.mesa);
}
function excluirPedido(id){
    const p=pedidos.find(item=>item.id===id);if(!p)return;
    if(!confirm("Deseja excluir este pedido do histórico?"))return;
    pedidos=pedidos.filter(item=>item.id!==id);salvarPedidos();renderizarPedidos();atualizarValorMesa(p.mesa);
}
function botoesPedido(p){
    let html="";
    if(p.status==="Pendente")html+=`<button class="btn-blue" onclick="alterarStatusPedido(${p.id},'Em preparo')">Preparar</button>`;
    else if(p.status==="Em preparo")html+=`<button class="btn-green" onclick="alterarStatusPedido(${p.id},'Pronto')">Pronto</button>`;
    else if(p.status==="Pronto")html+=`<button class="btn-green" onclick="alterarStatusPedido(${p.id},'Entregue')">Entregue</button>`;
    if(!["Entregue","Cancelado"].includes(p.status))html+=`<button class="btn-yellow" onclick="cancelarPedido(${p.id})">Cancelar</button>`;
    html+=`<button class="btn-delete" onclick="excluirPedido(${p.id})">🗑️</button>`;return html;
}
function renderizarPedidos(){
    const tabela=document.getElementById("tabelaPedidos");if(!tabela)return;tabela.innerHTML="";
    if(!pedidos.length)tabela.innerHTML='<tr><td colspan="10" class="vazio">Nenhum pedido registrado.</td></tr>';
    pedidos.forEach(p=>{
        const tr=document.createElement("tr");
        [`#${String(p.id).slice(-4)}`,p.mesa,p.cliente||"-",p.produto,p.quantidade,moeda(p.valorUnitario),moeda(p.total),p.horario,p.status].forEach(v=>{const td=document.createElement("td");td.textContent=v;tr.appendChild(td);});
        const td=document.createElement("td");td.innerHTML=botoesPedido(p);tr.appendChild(td);tabela.appendChild(tr);
    });
    atualizarResumoPedidos();
}
function atualizarResumoPedidos(){
    document.getElementById("pedidosPendentes").textContent=pedidos.filter(p=>p.status==="Pendente").length;
    document.getElementById("pedidosPreparo").textContent=pedidos.filter(p=>p.status==="Em preparo").length;
    document.getElementById("pedidosProntos").textContent=pedidos.filter(p=>p.status==="Pronto").length;
    const total=pedidos.filter(p=>p.status!=="Cancelado").reduce((s,p)=>s+Number(p.total||0),0);
    document.getElementById("totalPedidos").textContent=moeda(total);atualizarRelatorios();
}

/* ALIMENTOS RECICLADOS */
let reciclados=carregarLista("reciclados");
function registrarReciclado(){
    const alimento=document.getElementById("alimento").value.trim(),qtdTexto=document.getElementById("quantidadeReciclado").value;
    const motivo=document.getElementById("motivoReciclado").value,mesa=document.getElementById("mesaReciclado").value.trim();
    const funcionario=document.getElementById("funcionarioReciclado").value.trim(),observacao=document.getElementById("observacaoReciclado").value.trim();
    if(!alimento||qtdTexto===""||Number(qtdTexto)<=0||!motivo||!funcionario){alert("Preencha os campos obrigatórios.");return;}
    reciclados.push({alimento,quantidade:Number(qtdTexto),motivo,mesa,funcionario,observacao,dataHora:new Date().toLocaleString("pt-BR")});
    localStorage.setItem("reciclados",JSON.stringify(reciclados));
    ["alimento","quantidadeReciclado","motivoReciclado","mesaReciclado","funcionarioReciclado","observacaoReciclado"].forEach(id=>document.getElementById(id).value="");
    renderizarReciclados();
}
function renderizarReciclados(){
    const tabela=document.getElementById("tabelaReciclados");if(!tabela)return;tabela.innerHTML="";
    if(!reciclados.length)tabela.innerHTML='<tr><td colspan="7" class="vazio">Nenhum alimento registrado.</td></tr>';
    reciclados.forEach(r=>{
        const tr=document.createElement("tr");
        [r.alimento,r.quantidade,r.motivo,r.mesa||"-",r.funcionario,r.dataHora,r.observacao||"-"].forEach(v=>{const td=document.createElement("td");td.textContent=v;tr.appendChild(td);});
        tabela.appendChild(tr);
    });atualizarRelatorios();
}

/* RH / 13º SALÁRIO */
let decimos=carregarLista("decimos");
function calcular13(){
    const salario=Number(document.getElementById("salario13").value)||0;
    const avos=Math.max(0,Math.min(12,Number(document.getElementById("avos13").value)||0));
    const descontos=Number(document.getElementById("descontos13").value)||0;
    if(salario<0||descontos<0){alert("Informe valores válidos.");return null;}
    const bruto=salario*avos/12,primeira=bruto/2,liquido=Math.max(0,bruto-descontos);
    document.getElementById("resultado13").innerHTML=`
    <div class="resumo">
    <div class="box"><strong>Avos</strong><p>${avos}/12</p></div>
    <div class="box"><strong>13º bruto</strong><p>${moeda(bruto)}</p></div>
    <div class="box"><strong>1ª parcela (referência)</strong><p>${moeda(primeira)}</p></div>
    <div class="box"><strong>Descontos informados</strong><p>${moeda(descontos)}</p></div>
    <div class="box"><strong>Líquido estimado</strong><p>${moeda(liquido)}</p></div></div>`;
    return {bruto,primeira,liquido,avos,descontos};
}
function salvar13(){
    const c=calcular13();if(!c)return;
    const funcionario=document.getElementById("funcionario13").value.trim(),ano=Number(document.getElementById("ano13").value);
    if(!funcionario||!ano){alert("Informe o funcionário e o ano.");return;}
    decimos.push({id:Date.now(),funcionario,ano,avos:c.avos,bruto:c.bruto,descontos:c.descontos,liquido:c.liquido,status:"Pendente"});
    localStorage.setItem("decimos",JSON.stringify(decimos));renderizar13();alert("13º salvo no protótipo.");
}
function limpar13(){
    ["funcionario13","salario13","admissao13"].forEach(id=>document.getElementById(id).value="");
    document.getElementById("ano13").value=new Date().getFullYear();document.getElementById("avos13").value="12";
    document.getElementById("descontos13").value="0";document.getElementById("resultado13").innerHTML="";
}
function renderizar13(){
    const tabela=document.getElementById("tabela13");if(!tabela)return;tabela.innerHTML="";
    if(!decimos.length){tabela.innerHTML='<tr><td colspan="7" class="vazio">Nenhum cálculo salvo.</td></tr>';return;}
    decimos.forEach(d=>{
        const tr=document.createElement("tr");
        [d.funcionario,d.ano,`${d.avos}/12`,moeda(d.bruto),moeda(d.descontos),moeda(d.liquido),d.status].forEach(v=>{const td=document.createElement("td");td.textContent=v;tr.appendChild(td);});
        tabela.appendChild(tr);
    });
}

/* RELATÓRIOS E PROTEÇÃO DE TEXTO */
function atualizarRelatorios(){
    const dados={relatorioReciclados:reciclados.length,relatorioProdutos:estoque.length,relatorioPedidos:pedidos.length,relatorioFuncionarios:funcionarios.length};
    Object.entries(dados).forEach(([id,valor])=>{const el=document.getElementById(id);if(el)el.textContent=valor;});
}
function escapeHTML(valor){
    return String(valor).replace(/[&<>"']/g,c=>({"&":"&amp;","<":"&lt;",">":"&gt;",'"':"&quot;","'":"&#39;"}[c]));
}

/* INICIALIZAÇÃO */
inicializarMesas();
renderizarPonto();
renderizarFuncionarios();
renderizarTabela();
renderizarMesas();
renderizarPedidos();
renderizarReciclados();
renderizar13();
atualizarRelatorios();
</script>
</body>
</html>