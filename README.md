<!DOCTYPE html>
<html lang="pt-br">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Portal Restaurante</title>

<style>

/* RESET */
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:Arial, Helvetica, sans-serif;
}

/* CONTAINER */
.container{
    max-width:1200px;
    margin:auto;
}

body{
    background: linear-gradient(135deg, #1993b2, #084c01);
    min-height:100vh;
      padding:20px;
    display:flex;
    color:#111;
}

/* MENU */
.menu{
    width:250px;
    background:#084c01;
    color:white;
    min-height:100vh;
    padding:20px;
}

.menu h2{
    margin-bottom:20px;
    text-align:center;
}

.menu button{
    width:100%;
    padding:12px;
    margin-bottom:10px;
    border:none;
    background:#149b02;
    color:white;
    cursor:pointer;
    border-radius:5px;
    transition:0.3s;
    font-weight:bold;
}

.menu button:hover{
    background:#b7d304;
    color:#000;
}

/* CONTEÚDO */
.conteudo{
    flex:1;
    padding:20px;
    overflow:auto;
}

.tela{
    display:none;
}

.ativa{
    display:block;
}

/* CARDS */
.cards{
    display:grid;
    grid-template-columns:repeat(auto-fit,minmax(220px,1fr));
    gap:20px;
    margin-top:20px;
}

.card{
    background:white;
    padding:12px;
    border-radius:10px;
    box-shadow:0 0 10px rgba(0,0,0,0.2);
    text-align:center;
    cursor:pointer;
    transition:0.3s;
}

.card:hover{
    transform:scale(1.05);
    background:#13b8ff;
    color:white;
}

/* FORMULÁRIOS */
input,
select,
textarea{
    width:100%;
    padding:10px;
    margin-top:10px;
    border:1px solid #ccc;
    border-radius:5px;
}

button{
    border:none;
}

/* BOTÕES */
.cadastrar{
    width:100%;
    padding:12px;
    margin-top:15px;
    background:#24cb02;
    color:white;
    border:none;
    border-radius:5px;
    cursor:pointer;
    font-size:16px;
    font-weight:bold;
    transition:0.3s;
}

.cadastrar:hover{
    background:#1e9e02;
}

.entrada{
    background:#0ba923;
    color:white;
    padding:10px;
    border-radius:5px;
    cursor:pointer;
}

.saida{
    background:#f44336;
    color:white;
    padding:10px;
    border-radius:5px;
    cursor:pointer;
}

.delete{
    background:red;
    color:white;
    padding:8px;
    border-radius:5px;
    cursor:pointer;
}

/* TABELAS */
table{
    width:100%;
    border-collapse:collapse;
    margin-top:20px;
    background:white;
}

table th,table td{
    border:1px solid #380f0f;
    padding:10px;
    text-align:center;
}

table th{
    background:#4493fb;
    color:white;
}

/* RELÓGIO */
#relogio{
    font-size:20px;
    margin:15px 0;
    font-weight:bold;
}

</style>
</head>

<!--Mesas-->>
<head>
    <style>

        body{
            min-height:100vh;
            padding:20px;
            color:white;

        }
        
        .container{
            max-width:1200px;
            margin:auto;
        }
        
        /* CARDS */
        .cards{
            display:grid;
            grid-template-columns:repeat(auto-fit,minmax(220px,1fr));
            gap:20px;
            margin-bottom:30px;
        }
        
        .card{
            background:white;
            color:#111;
            padding:20px;
            border-radius:15px;
            box-shadow:0 5px 15px rgba(0,0,0,0.3);
            transition:0.3s;
        }
        
        .card:hover{
            transform:translateY(-5px);
        }
        
        .card h2{
            font-size:18px;
            margin-bottom:10px;
        }
        
        .card p{
            font-size:25px;
            font-weight:bold;
        }
        /* FORM */
        
        .formulario{
            background:white;
            color:#111;
            padding:20px;
            border-radius:15px;
            margin-bottom:30px;
            box-shadow:0 5px 15px rgba(0,0,0,0.3);
        }
        
        .form-grid{
            display:grid;
            grid-template-columns:repeat(auto-fit,minmax(200px,1fr));
            gap:15px;
        }
        
        input,
        select{
            width:100%;
            padding:12px;
            border:1px solid #ccc;
            border-radius:8px;
            font-size:15px;
        }
        
        button{
            border:none;
            padding:12px;
            border-radius:8px;
            cursor:pointer;
            font-weight:bold;
            transition:0.3s;
        }
        
        .btn-add{
            background:#28a745;
            color:white;
        }
        
        .btn-add:hover{
            background:#218838;
        }
        
        .btn-delete{
            background:#dc3545;
            color:white;
        }
        
        .btn-delete:hover{
            background:#c82333;
        }
        
        .btn-edit{
            background:#007bff;
            color:white;
        }
        
        .btn-edit:hover{
            background:#0069d9;
        }
        
        .btn{
            background:#007bff;
            color:white;
        }
        
        .btn:hover{
            opacity:.85;
        }
        
        .btn-green{
            background:#149b02;
            color:white;
        }
        
        .btn-red{
            background:#dc3545;
            color:white;
        }
        
        .btn-yellow{
            background:#ffc107;
            color:#000;
        }
        
        /* TABELA */
        table{
            width:100%;
            border-collapse:collapse;
            background:white;
            color:#111;
            border-radius:15px;
            overflow:hidden;
        }
        
        table th{
            background:#007bff;
            color:white;
            padding:15px;
        }
        
        table td{
            padding:12px;
            border-bottom:1px solid #ddd;
            text-align:center;
        }
        
        .baixo{
            background:#ffb3b3;
            color:#b30000;
            font-weight:bold;
        }
        
        .medio{
            background:#fff3cd;
            color:#856404;
            font-weight:bold;
        }
        
        .alto{
            background:#c3f7d0;
            color:#155724;
            font-weight:bold;
        }
        
        @media(max-width:768px){
            table{

                font-size:12px;
            }
            
            h1{
                font-size:19px;
            }
        }
        
        /* STATUS */
        .status{
            display:inline-block;
            padding:6px 10px;
            border-radius:15px;
            font-weight:bold;
        }
        
        .livre{
            background:#c8f9cc;
            color:#087f23;
        }
        
        .ocupada{
            background:#ffd1d1;
            color:#b30000;
        }
        
        .reservada{
            background:#fff0a8;
            color:#8a6d00;
        }
        
        /* MESAS */
        .mesas-grid{
            display:grid;
            grid-template-columns:repeat(auto-fit,minmax(230px,1fr));
            gap:18px;
        }
        
        .mesa-card{
            background:white;
            border-radius:14px;
            padding:20px;
            box-shadow:0 4px 12px rgba(0,0,0,.2);
            border-top:8px solid #149b02;
        }
        
        .mesa-card.ocupada-card{
            border-top-color:#dc3545;
        }
        
        .mesa-card.reservada-card{
            border-top-color:#ffc107;
        }
        
        .mesa-numero{
            font-size:25px;
            font-weight:bold;
            margin-bottom:10px;
        }
        
        .mesa-info{
            margin:7px 0;
        }
        
        .mesa-acoes{
            display:flex;
            flex-wrap:wrap;
            gap:7px;
            margin-top:15px;
        }
        
        .mesa-acoes button{
            flex:1;
            min-width:100px;
        }
        
        .form-grid{
            display:grid;
            grid-template-columns:repeat(auto-fit,minmax(180px,1fr));
            gap:10px;
        }
        
        @media(max-width:800px){
            .sidebar{
                position:relative;
                width:100%;
                height:auto;
            }
            
            .content{
                margin-left:0;
            }
        }

    </style>
</head>

<!---RH - 13º Salário--->
<style>
    body{
        margin:0;
        font-family:Arial,sans-serif;
        background:linear-gradient(135deg,#1993b2,#084c01);
        color:#222
    } 
    
    .container{
        max-width:100px;
        margin:30px auto;
        padding:20px
    } 
    
    h1{
        color:white;
        text-align:center
    }
    
    .card{
        background:white;
        border-radius:12px;
        padding:20px;
        margin-bottom:20px;
        box-shadow:0 4px 12px rgba(0,0,0,.18)
    } 
    
    .grid{
        display:grid;
        grid-template-columns:repeat(auto-fit,minmax(180px,1fr));
        gap:12px
    } 
    
    label{
        font-weight:bold;
        display:block;
        margin-bottom:5px
    } 
    
    input{
        width:100%;
        box-sizing:border-box;
        padding:10px;
        border:1px solid #ccc;
        border-radius:7px
    } 
    
    button{
        border:0;
        border-radius:7px;
        padding:10px 15px;
        cursor:pointer;
        margin-top:12px
    } 
    
    .btn-green{
        background:#149b02;
        color:white
    }
    
    .btn-blue{
        background:#007bff;
        color:white
    }
    
    .btn-yellow{
        background:#b7d304;
        color:#222
    }
     table{
        width:100%;
        border-collapse:collapse;
        margin-top:15px
    }
     th{
        background:#007bff;
        color:white;
        padding:10px
    }
    td{
        padding:9px;
        border-bottom:1px solid #ddd;
        text-align:center
    }

    .resumo{
        display:grid;
        grid-template-columns:repeat(auto-fit,minmax(180px,1fr));
        gap:12px
    }
    .box{
        background:#fff;
        padding:15px;
        border-radius:10px;
        box-shadow:0 3px 9px rgba(0,0,0,.15)
    }
    
    .valor{
        font-size:20px;
        font-weight:bold
    }
    
    @media(max-width:600px){
        .container{
            margin:10px;
            padding:10px
        }
        table{
            font-size:12px
        }
    }
</style>
</head>


<!-- MENU -->
<div class="menu">

    <h2>🍽 Restaurante</h2>

    <button onclick="mostrarTela('dashboard')">Dashboard</button>
    <button onclick="mostrarTela('estoque')">Estoque</button>
    <button onclick="mostrarTela('funcionarios')">Funcionários</button>
    <button onclick="mostrarTela('controle')">Controle de Ponto</button>
    <button onclick="mostrarTela('rh')">RH</button>
    <button onclick="mostrarTela('mesas')">Mesas</button>
    <button onclick="mostrarTela('pedidos')">Pedidos</button>
    <button onclick="mostrarTela('reciclados')">Alimentos Reciclados</button>

</div>

<!-- CONTEÚDO -->
<div class="conteudo">

    <!-- DASHBOARD -->
    <div id="dashboard" class="tela ativa">

        <h1> 🏪Portal do Restaurante</h1>

        <div class="cards">

            <div class="card" onclick="mostrarTela('controle')">
                <h2>⏰ Controle de Ponto</h2>
                <p>Registro de entrada e saída</p>
            </div>

            <div class="card" onclick="mostrarTela('funcionarios')">
                <h2>👨‍🍳 Funcionários</h2>
                <p>Cadastro completo</p>
            </div>

            <div class="card" onclick="mostrarTela('estoque')">
                <h2>📦 Estoque</h2>
                <p>Estoque de total de produtos </p>
            </div>

            <div class="card" onclick="mostrarTela('mesas')">
                <h2>🪑 Mesas</h2>
                <p>Status das mesas</p>
            </div>

            <div class="card" onclick="mostrarTela('pedidos')">
                <h2>🧾 Pedidos</h2>
                <p>Controle de pedidos</p>
            </div>

             <div class="card" onclick="mostrarTela('reciclados')">
                <h2>♻️ Alimentos Reciclados</h2>
                <p>Controle de desperdícios</p>
            </div>

        </div>

    </div>

    <!-- ESTOQUE -->
    <div id="estoque" class="tela">

        <h1>📦 Estoque</h1>
        <p>Área de estoque em desenvolvimento.</p>

        <div class="cards">

        <div class="card">
            <h2>Total de Produtos</h2>
            <p id="totalProdutos">0</p>
        </div>

        <div class="card">
            <h2>Itens em Baixa</h2>
            <p id="baixoEstoque">0</p>
        </div>

        <div class="card">
            <h2>Valor Total</h2>
            <p id="valorTotal">R$ 0,00</p>
        </div>

    </div>

    <!-- FORMULÁRIO -->
    <div class="formulario">

        <div class="form-grid">

            <input type="text" id="produto" placeholder="Nome do Produto">
            <input type="number" id="quantidade" placeholder="Quantidade">
            <input type="number" id="preco" placeholder="Preço Unitário">

            <select id="categoria">
                <option value="">Categoria</option>
                <option>Bebidas</option>
                <option>Carnes</option>
                <option>Massas</option>
                <option>Hortifruti</option>
                <option>Limpeza</option>
                <option>Outros</option>
            </select>

            <button class="btn-add" onclick="adicionarProduto()">
                ➕ Adicionar Produto
            </button>

        </div>

    </div>

    <!-- TABELA -->
    <table>

        <thead>
            <tr>
                <th>Produto</th>
                <th>Categoria</th>
                <th>Quantidade</th>
                <th>Preço</th>
                <th>Total</th>
                <th>Status</th>
                <th>Ações</th>
            </tr>
        </thead>

        <tbody id="tabelaProdutos"></tbody>

    </table>


    </div>

    <!-- CONTROLE DE PONTO -->
    <div id="controle" class="tela">

        <h1>⏰ Controle de Ponto</h1>

        <div id="relogio"></div>

        <input type="text" id="nomePonto" placeholder="Nome do funcionário">
        <input type="text" id="funcaoPonto" placeholder="Função">

        <button class="entrada" onclick="registrar('entrada')">
            Registrar Entrada
        </button>

        <button class="saida" onclick="registrar('saida')">
            Registrar Saída
        </button>

        <table>

            <thead>
                <tr>
                    <th>Nome</th>
                    <th>Função</th>
                    <th>Data</th>
                    <th>Entrada</th>
                    <th>Saída</th>
                    <th>Total (Horas)</th>
                    <th>Ação</th>
                </tr>
            </thead>

            <tbody id="tabelaPonto"></tbody>

        </table>

    </div>

    <!-- FUNCIONÁRIOS -->
    <div id="funcionarios" class="tela">

        <h1>👨‍🍳 Cadastro de Funcionários</h1>

        <input type="text" id="nomeFuncionario" placeholder="Nome">
        <input type="text" id="cargo" placeholder="Cargo">
        <input type="text" id="telefone" placeholder="Telefone">
        <input type="number" id="salario" placeholder="Salário">

        <select id="status">
            <option value="Ativo">✔️ Ativo</option>
            <option value="Desativado">❌ Desativado</option>
        </select>

        <button class="cadastrar" onclick="cadastrar()">
            Cadastrar Funcionário
        </button>

        <table>

            <thead>
                <tr>
                    <th>Nome</th>
                    <th>Cargo</th>
                    <th>Telefone</th>
                    <th>Salário</th>
                    <th>Status</th>
                    <th>Ações</th>
                </tr>
            </thead>

            <tbody id="tabelaFuncionarios"></tbody>

        </table>

    </div>

    <!-- RH -->
    <div id="rh" class="tela">

        <h1>🏢 RH</h1>
        <p>Área de RH em desenvolvimento.</p>

        <div class="card">
            <h2>Cadastro / Cálculo</h2> 
            <div class="grid"> 
                <div>
                    <label>Funcionário</label>
                    <input id="funcionario" placeholder="Nome">
                </div> 
                
                <div>
                    <label>Salário / remuneração considerada</label>
                    <input id="salario" type="number" step="0.01">
                </div> 
                 
                <div>
                    <label>Ano</label>
                    <input id="ano" type="number" value="2026">
                </div> 
                    
                <div>
                    <label>Data de admissão</label>
                    <input id="admissao" type="date">
                </div>
                     
                <div>
                    <label>Avos considerados</label>
                    <input id="avos" type="number" min="0" max="12" value="12">
                </div>
                     
                <div>
                    <label>Descontos</label>
                    <input id="descontos" type="number" step="0.01" value="0">
                </div>
            </div>
            
            <button class="btn-green" onclick="calcular13()">n Calcular 13º</button>
            <button class="btn-blue" onclick="salvar13()">n Salvar</button>
            <button class="btn-yellow" onclick="limpar()">n Limpar</button>
            <div id="resultado" style="margin-top:15px"></div>
            
        </div> 
        
        <div class="card">
            <h2>Histórico</h2>
            <table>
                <thead>
                    <tr>
                        <th>Funcionário</th>
                        <th>Ano</th>
                        <th>Avos</th>
                        <th>Bruto</th>
                        <th>Descontos</th>
                        <th>Líquido</th>
                        <th>Status</th>
                    </tr>
                </thead>
                
                <tbody id="tabela"></tbody>
            </table>
        </div>

    </div>
</div>

    <!-- MESAS -->
    <div id="mesas" class="tela">

        <h1>🪑 Controle de Mesas</h1>
        <p>Área de mesas em desenvolvimento.</p>

        <div class="cards">
            <div class="card">
                <h3>🟢 Mesas Livres</h3>
                <p id="totalMesasLivres">0</p>
            </div>
            <div class="card">
                <h3>🔴 Mesas Ocupadas</h3>
                <p id="totalMesasOcupadas">0</p>
            </div>
            <div class="card">
                <h3>🟡 Reservadas</h3>
                <p id="totalMesasReservadas">0</p>
            </div>
            <div class="card">
                <h3>💰 Faturamento</h3>
                <p id="faturamentoMesas">R$ 0,00</p>
            </div>
        </div>

        <div class="box">
            <h2>🪑 Cadastro / Edição de Mesa</h2>
            <div class="form-grid">
                <div>
                    <label>Número da mesa</label>
                    <input
                        id="numeroMesa"
                        type="number"
                        min="1"
                    >
                </div>

                <div>
                    <label>Nome do cliente</label>
                    <input
                        id="clienteMesa"
                        placeholder="Nome do cliente"
                    >
                </div>

                <div>
                    <label>Quantidade de pessoas</label>
                    <input
                        id="pessoasMesa"
                        type="number"
                        min="1"
                    >
                </div>

                <div>
                    <label>Valor da conta</label>
                    <input
                        id="valorMesa"
                        type="number"
                        step="0.01"
                        value="0"
                    >
                </div>

                <div>
                    <label>Status</label>
                    <select id="statusMesa">
                        <option value="livre">🟢 Livre</option>
                        <option value="ocupada">🔴 Ocupada</option>
                        <option value="reservada">🟡 Reservada</option>
                    </select>
                </div>

                <button
                class="btn-green"
                onclick="salvarMesa()">Salvar Mesa
                </button>
            
                <button
                 class="btn"
                 onclick="limparMesaForm()">limpar
             </button>
            </div>

        </div>

        <div class="box">
            <h2>Mesas do Restaurante</h2>
            <div
                id="mesasGrid"
                class="mesas-grid">
            </div>
        </div>

    </div>
</div>
    <!-- PEDIDOS -->
    <div id="pedidos" class="tela">

        <h1>🧾 Pedidos</h1>
        <p>Área de pedidos em desenvolvimento.</p>

        <div class="cards">
            <div class="card">
                <h3>🟡 Pendentes</h3>
                <p id="pedidosPendentes">0</p>
            </div>

            <div class="card">
                <h3>🔵 Em preparo</h3>
                <p id="pedidosPreparo">0</p>
            </div>
            
            <div class="card">
                <h3>🟢 Prontos</h3>
                <p id="pedidosProntos">0</p>
            </div>
            
            <div class="card">
                <h3>💰 Total dos pedidos</h3>
                <p id="totalPedidos">R$ 0,00</p>
            </div>
        </div>

        <div class="box">

            <h2>🍽️ Novo Pedido</h2>
            <div class="form-grid">
                <div>
                    <label>Número da mesa</label>
                    <input
                        id="mesaPedido"
                        type="number"
                        min="1"
                        placeholder="Ex.: 5"
                    >
                </div>
                <div>
                    <label>Cliente</label>
                    <input
                        id="clientePedido"
                        placeholder="Nome do cliente"
                    >
                </div>
            
                <div>
                    <label>Produto / Prato</label>
                    <input
                        id="produtoPedido"
                        placeholder="Ex.: Hambúrguer"
                    >
                </div>
            
                <div>
                    <label>Quantidade</label>
                    <input
                        id="quantidadePedido"
                        type="number"
                        min="1"
                        value="1"
                    >
                </div>
            
                <div>
                    <label>Valor unitário</label>
                    <input
                        id="valorUnitarioPedido"
                        type="number"
                        step="0.01"
                        placeholder="0,00"
                    >
                </div>
                <div>
                    <label>Status</label>
                    <select id="statusPedido">
                        <option value="Pendente">🟡 Pendente</option>
                        <option value="Em preparo">🔵 Em preparo</option>
                        <option value="Pronto">🟢 Pronto</option>
                        <option value="Entregue">🟣 Entregue</option>
                    </select>
                </div>
            </div>

            <buttonclass="btn-green"
            onclick="adicionarPedido()">➕ Adicionar Pedido</button>
            <button
                class="btn"
                onclick="limparPedido()">Limpar
            </button>
        </div>

        <div class="box">

            <h2>📋 Pedidos registrados</h2>

            <div class="table-container">
                <table>
                    <thead>
                        <tr>
                            <th>Pedido</th>
                            <th>Mesa</th>
                            <th>Cliente</th>
                            <th>Produto</th>
                            <th>Qtd.</th>
                            <th>Unitário</th>
                            <th>Total</th>
                            <th>Horário</th>
                            <th>Status</th>
                            <th>Ações</th>
                        </tr>
                    </thead>
                    <tbody id="tabelaPedidos"></tbody>
                </table>
            </div>
        </div>
    </div>

    <!-- ALIMENTOS RECICLADOS -->
    <div id="reciclados" class="tela">

        <h1>♻️ Alimentos Reciclados</h1>
        <p>Registro de alimentos que não foram aproveitados.</p>

         <div class="formulario">
            <div class="form-grid">

                <input
                    type="text"
                    id="alimento"
                    placeholder="Alimento"
                >

                <input
                    type="number"
                    id="quantidadeReciclado"
                    placeholder="Quantidade"
                    min="0"
                    step="0.01"
                >
                <select id="motivoReciclado">

                    <option value="">
                        Motivo
                    </option>

                    <option>
                        Pedido cancelado
                    </option>

                    <option>
                        Não consumido
                    </option>

                    <option>
                        Pedido devolvido
                    </option>

                    <option>
                        Validade
                    </option>

                    <option>
                        Outro
                    </option>

                </select>

                <input
                    type="text"
                    id="mesaReciclado"
                    placeholder="Mesa"
                >

                <input
                    type="text"
                    id="funcionarioReciclado"
                    placeholder="Funcionário"
                >

                <textarea
                    id="observacaoReciclado"
                    placeholder="Observação"
                    >
                </textarea>

                <button
                    class="btn-add"
                    onclick="registrarReciclado()"> ♻️ Registrar Alimento

                </button>
             </div>
        </div>
        <table>
            <thead>
                <tr>
                    <th>Alimento</th>
                    <th>Quantidade</th>
                    <th>Motivo</th>
                    <th>Mesa</th>
                    <th>Funcionário</th>
                    <th>Data/Hora</th>
                    <th>Observação</th>
                </tr>
            </thead>
                <tbody id="tabelaReciclados"></tbody>
        </table>

        <!-- RELATÓRIOS -->
        <div id="relatorios" class="tela">
            <h1>📊 Relatórios</h1>
            <p>Resumo das informações cadastradas no sistema.</p>
                    
            <div class="formulario">
                <div class="cards">
                    <h2>♻️ Alimentos Reciclados</h2>
                    <p id="relatorioReciclados">0</p>
                </div>
            </div>
        </div>

    </div>
<script>

/* TROCAR TELAS */
function mostrarTela(id){

    let telas = document.querySelectorAll(".tela");

    telas.forEach(tela => {
        tela.classList.remove("ativa");
    });

    document.getElementById(id).classList.add("ativa");
}

/* RELÓGIO */
function atualizarRelogio(){

    const agora = new Date();
    const data = agora.toLocaleDateString();
    const hora = agora.toLocaleTimeString();

    document.getElementById("relogio").innerHTML =
        "📅 " + data + " ⏰ " + hora;
}

setInterval(atualizarRelogio, 1000);

atualizarRelogio();

/* FUNÇÕES DE DATA */
function agora(){
    return new Date();
}

function formatarHora(data){
    return data.toLocaleTimeString();
}

function formatarData(data){
    return data.toLocaleDateString();
}

/* REGISTRAR PONTO */
function registrar(tipo){

    const nome = document.getElementById("nomePonto").value;
    const funcao = document.getElementById("funcaoPonto").value;

    if(nome === ""){
        alert("Digite o nome!");
        return;
    }

    let registros = JSON.parse(localStorage.getItem("ponto")) || [];
    const dataAtual = formatarData(agora());
    const horaAtual = formatarHora(agora());

    if(tipo === "entrada"){

        registros.push({
            nome,
            funcao,
            data:dataAtual,
            entrada:horaAtual,
            saida:"",
            total:""
        });
    }

    if(tipo === "saida"){

        for(let i = registros.length - 1; i >= 0; i--){

            if(registros[i].nome === nome && registros[i].saida === ""){

                registros[i].saida = horaAtual;

                registros[i].total =
                    calcularHoras(
                        registros[i].entrada,
                        horaAtual
                    );

                break;
            }
        }
    }

    localStorage.setItem("ponto",JSON.stringify(registros)
    );

    renderizarPonto();
}

/* CALCULAR HORAS */
function calcularHoras(entrada, saida){

    const [h1,m1,s1] = entrada.split(":").map(Number);
    const [h2,m2,s2] = saida.split(":").map(Number);
    const inicio = new Date(0,0,0,h1,m1,s1);
    const fim = new Date(0,0,0,h2,m2,s2);
    const diff = (fim - inicio) / 1000 / 60 / 60;

    return diff.toFixed(2);
}

/* DELETAR REGISTRO */
function deletar(index){

    let registros =JSON.parse(localStorage.getItem("ponto")) || [];

    registros.splice(index,1);

    localStorage.setItem("ponto",JSON.stringify(registros));

    renderizarPonto();
}

/* RENDERIZAR TABELA PONTO */
function renderizarPonto(){

    const tabela =document.getElementById("tabelaPonto");

    tabela.innerHTML = "";

    let registros =JSON.parse(localStorage.getItem("ponto")) || [];

    registros.forEach((r,i) => {

        tabela.innerHTML += `
            <tr>
                <td>${r.nome}</td>
                <td>${r.funcao}</td>
                <td>${r.data}</td>
                <td>${r.entrada}</td>
                <td>${r.saida}</td>
                <td>${r.total}</td>

                <td>
                    <button
                        class="delete"
                        onclick="deletar(${i})">
                        Excluir
                    </button>
                </td>
            </tr>
        `;
    });
}

renderizarPonto();

/* CARREGAR DO LOCALSTORAGE */
let funcionarios =JSON.parse(localStorage.getItem("funcionarios")) || [];

/* SALVAR */
function salvar(){
    localStorage.setItem("funcionarios",JSON.stringify(funcionarios));
}

/* CADASTRAR FUNCIONÁRIO */
function cadastrar(){

    let nome =document.getElementById("nomeFuncionario").value.trim();
    let cargo =document.getElementById("cargo").value.trim();
    let telefone =document.getElementById("telefone").value.trim();
    let salario =document.getElementById("salario").value;
    let status =document.getElementById("status").value;

    if(
        nome === "" ||
        cargo === "" ||
        telefone === "" ||
        salario === ""
    ){
        alert("Preencha todos os campos!");
        return;
    }

    let tabela =
        document.getElementById(
            "tabelaFuncionarios"
        );

    let linha = document.createElement("tr");

    linha.innerHTML = `
        <td>${nome}</td>
        <td>${cargo}</td>
        <td>${telefone}</td>
        <td>R$ ${Number(salario).toFixed(2)}</td>
        <td>${status}</td>

        <td>
            <button
                class="delete"
                onclick="remover(this)">
                ❌ Excluir
            </button>
        </td>
    `;

    tabela.appendChild(linha);

    /* LIMPAR CAMPOS */
    document.getElementById( "nomeFuncionario").value = "";
    document.getElementById("cargo").value = "";
    document.getElementById("telefone").value = "";
    document.getElementById( "salario").value = "";
    document.getElementById("status").value = "Ativo";
}

/* REMOVER FUNCIONÁRIO */
function remover(botao){
    botao.parentElement.parentElement.remove();
}

/* INICIAR */
renderizar();

</script>

<script>

/* ADICIONAR PRODUTO */
let estoque =JSON.parse(localStorage.getItem("estoque")) || [];
function adicionarProduto(){

    let produto =document.getElementById("produto").value.trim();
    let quantidade =document.getElementById("quantidade").value;
    let preco =document.getElementById("preco").value;
    let categoria =document.getElementById("categoria").value;

    if(
        produto === "" ||
        quantidade === "" ||
        preco === "" ||
        categoria === ""
    ){
        alert("Preencha todos os campos!");
        return;
    }

    estoque.push({
        produto,
        quantidade:Number(quantidade),
        preco:Number(preco),
        categoria
    });

    salvarDados();
    limparCampos();
    renderizarTabela();
}

/* SALVAR LOCALSTORAGE */
function salvarDados(){

    localStorage.setItem(
        "estoque",
        JSON.stringify(estoque)
    );
}

/* LIMPAR CAMPOS */
function limparCampos(){

    document.getElementById("produto").value = "";
    document.getElementById("quantidade").value = "";
    document.getElementById("preco").value = "";
    document.getElementById("categoria").value = "";
}

/* STATUS ESTOQUE */
function statusEstoque(qtd){

    if(qtd <= 5){
        return {
            texto:"BAIXO",
            classe:"baixo"
        };
    }

    if(qtd <= 15){
        return {
            texto:"MÉDIO",
            classe:"medio"
        };
    }

    return {
        texto:"ALTO",
        classe:"alto"
    };
}

/* RENDERIZAR */
function renderizarTabela(){

    let tabela =
        document.getElementById("tabelaProdutos");

    tabela.innerHTML = "";

    let totalProdutos = estoque.length;

    let baixoEstoque = 0;

    let valorTotal = 0;

    estoque.forEach((item,index)=>{

        let status =
            statusEstoque(item.quantidade);

        if(item.quantidade <= 5){
            baixoEstoque++;
        }

        let totalItem =
            item.quantidade * item.preco;

        valorTotal += totalItem;

        tabela.innerHTML += `
            <tr>

                <td>${item.produto}</td>
                <td>${item.categoria}</td>
                <td>${item.quantidade}</td>

                <td>
                    R$ ${item.preco.toFixed(2)}
                </td>

                <td>
                    R$ ${totalItem.toFixed(2)}
                </td>

                <td class="${status.classe}">
                    ${status.texto}
                </td>

                <td>

                    <button
                        class="btn-edit"
                        onclick="editarProduto(${index})">
                        ✏️
                    </button>

                    <button
                        class="btn-delete"
                        onclick="deletarProduto(${index})">
                        🗑️
                    </button>

                </td>

            </tr>
        `;
    });

    document.getElementById("totalProdutos").innerText = totalProdutos;
    document.getElementById("baixoEstoque").innerText = baixoEstoque;
    document.getElementById("valorTotal").innerText ="R$ " + valorTotal.toFixed(2);
}

/* DELETAR */
function deletarProduto(index){

    if(confirm("Deseja remover este produto?")){

        estoque.splice(index,1);

        salvarDados();
        renderizarTabela();
    }
}

/* EDITAR */
function editarProduto(index){

    let item = estoque[index];

    let novoNome =prompt("Editar produto:", item.produto);
    let novaQtd =prompt("Editar quantidade:", item.quantidade);
    let novoPreco =prompt("Editar preço:", item.preco);

    if(
        novoNome !== null &&
        novaQtd !== null &&
        novoPreco !== null
    ){

        estoque[index].produto = novoNome;
        estoque[index].quantidade =Number(novaQtd);
        estoque[index].preco =Number(novoPreco);

        salvarDados();
        renderizarTabela();
    }
}

/*MESAS*/

let mesas=JSON.parse(localStorage.getItem("mesas")) || [];

function inicializarMesas(){

    if(mesas.length===0){

        for(let i=1;i<=10;i++){

            mesas.push({

                numero:i,
                cliente:"",
                pessoas:0,
                valor:0,
                status:"livre"

            });

        }

        salvarMesas();
    }
}

function salvarMesas(){
    localStorage.setItem("mesas",JSON.stringify(mesas));
}


function salvarMesa(){

    const numero=Number(document.getElementById("numeroMesa").value);
    const cliente=document.getElementById("clienteMesa").value;
    const pessoas=Number(document.getElementById("pessoasMesa").value);
    const valor=Number(document.getElementById("valorMesa").value);
    const status=document.getElementById("statusMesa").value;

    if(!numero){

        alert("Informe o número da mesa.");

        return;
    }

    const existente=
    mesas.find(
        m=>Number(m.numero)===numero
    );

    if(existente){

        existente.cliente=cliente;
        existente.pessoas=pessoas;
        existente.valor=valor;
        existente.status=status;

    }else{

        mesas.push({

            numero,
            cliente,
            pessoas,
            valor,
            status

        });

    }

    salvarMesas();
    limparMesaForm();
    renderizarMesas();
    atualizarResumo();
}


function limparMesaForm(){

    document.getElementById("numeroMesa").value="";
    document.getElementById("clienteMesa").value="";
    document.getElementById("pessoasMesa").value="";
    document.getElementById("valorMesa").value=0;
    document.getElementById("statusMesa").value="livre";
}

function abrirMesa(numero){

    const mesa=mesas.find(m=>Number(m.numero)===Number(numero));

    if(!mesa)return;

    const cliente=prompt("Nome do cliente:");

    if(cliente===null)return;

    const pessoas=Number(prompt("Quantidade de pessoas:", "1")) || 1;

    mesa.status="ocupada";
    mesa.cliente=cliente;
    mesa.pessoas=pessoas;

    if(!mesa.valor){
        mesa.valor=0;
    }

    salvarMesas();
    renderizarMesas();
    atualizarResumo();
}

function fecharMesa(numero){

    const mesa=mesas.find(m=>Number(m.numero)===Number(numero));
    if(!mesa)return;

    const pedidosMesa= pedidos.filter(p=>Number(p.mesa)===Number(numero) && p.status!=="Cancelado");
    const totalPedidos=pedidosMesa.reduce((s,p)=>s+Number(p.total||0),0);

    let valor=totalPedidos;

    if(valor===0){

        valor=Number(prompt("Valor final da conta:",mesa.valor||0)) || 0;
    }

    if(!confirm(
        `Fechar Mesa ${numero}?\n\nTotal: R$ ${valor.toFixed(2)}`
    )){
        return;
    }

    mesa.valor=valor;
    mesa.status="livre";
    mesa.cliente="";
    mesa.pessoas=0;

    salvarMesas();
    renderizarMesas();
}

function liberarMesa(numero){

    const mesa=mesas.find(m=>Number(m.numero)===Number(numero));

    if(!mesa)return;

    mesa.status="livre";
    mesa.cliente="";
    mesa.pessoas=0;
    mesa.valor=0;

    salvarMesas();
    renderizarMesas();
    atualizarResumo();
}


function editarMesa(numero){

    const mesa=mesas.find(m=>Number(m.numero)===Number(numero));

    if(!mesa)return;

    document.getElementById("numeroMesa").value=mesa.numero;
    document.getElementById("clienteMesa").value=mesa.cliente;
    document.getElementById("pessoasMesa").value=mesa.pessoas;
    document.getElementById("valorMesa").value=mesa.valor;
    document.getElementById("statusMesa").value=mesa.status;

    mostrarTela("mesas");
}


function acaoMesa(mesa){

    if(mesa.status==="livre"){

        return `
        <button
        class="btn-green"
        onclick="abrirMesa(${mesa.numero})">
        🔓 Abrir mesa
        </button>
        `;

    }

    if(mesa.status==="ocupada"){

        return `
        <button
        class="btn-red"
        onclick="fecharMesa(${mesa.numero})">
        💳 Fechar mesa
        </button>
        `;
    }

     if(mesa.status==="reservada"){

        return `
        <button
        class="btn-green"
        onclick="liberarMesa(${mesa.numero})">
        🟢 Liberar
        </button>
        `;

    }

    return "";
}


function renderizarMesas(){

    inicializarMesas();

    const grid= document.getElementById("mesasGrid");

    if(!grid)return;

    grid.innerHTML="";

    mesas.forEach(mesa=>{

        let classe="";

        if(mesa.status==="ocupada"){
            classe="ocupada-card";
        }

        if(mesa.status==="reservada"){
            classe="reservada-card";
        }

        let textoStatus="🟢 Livre";

        if(mesa.status==="ocupada"){
            textoStatus="🔴 Ocupada";
        }

        if(mesa.status==="reservada"){
            textoStatus="🟡 Reservada";
        }

        grid.innerHTML+=`

        <div class="mesa-card ${classe}">

        <div class="mesa-numero">🪑 Mesa ${mesa.numero}</div>

        <div class="mesa-info">

        <strong>Status:</strong>
        ${textoStatus}

        </div>

        <div class="mesa-info">
            <strong>Cliente:</strong>${mesa.cliente||"-"}
        </div>

        <div class="mesa-info">
            <strong>Pessoas:</strong>${mesa.pessoas||0}
        </div>

        <div class="mesa-info">

        <strong>Conta:</strong>
        R$ ${(Number(mesa.valor)||0).toFixed(2)}

        </div>

        <div class="mesa-acoes">
            ${acaoMesa(mesa)}

            <button
               class="btn"
              onclick="editarMesa(${mesa.numero})">
              ✏️ Editar
            </button>

        </div>
        `;
    });

    atualizarResumoMesas();
}

function atualizarResumoMesas(){

    const livres= mesas.filter(m=>m.status==="livre").length;
    const ocupadas= mesas.filter(m=>m.status==="ocupada").length;
    const reservadas=mesas.filter(m=>m.status==="reservada").length;
    const faturamento=mesas.filter(m=>m.status==="ocupada").reduce((s,m)=>s+Number(m.valor||0),0);

    document.getElementById("totalMesasLivres").textContent=livres;
    document.getElementById("totalMesasOcupadas").textContent=ocupadas;
    document.getElementById("totalMesasReservadas").textContent=reservadas;
    document.getElementById("faturamentoMesas").textContent="R$ "+faturamento.toFixed(2);
}

/*PEDIDOS*/

let pedidos=JSON.parse(localStorage.getItem("pedidos")) || [];
function salvarPedidos(){

    localStorage.setItem("pedidos",JSON.stringify(pedidos));
}

function adicionarPedido(){

    const mesa=Number(document.getElementById("mesaPedido").value);
    const cliente=document.getElementById("clientePedido").value.trim();
    const produto=document.getElementById("produtoPedido").value.trim();
    const quantidade=Number(document.getElementById("quantidadePedido").value);
    const valorUnitario=Number(document.getElementById("valorUnitarioPedido").value);
    const status=document.getElementById("statusPedido").value;

    
    if(!mesa){

        alert("Informe o número da mesa.");

        return;
    }

    if(!produto){

        alert("Informe o produto ou prato.");

        return;
    }

    if(quantidade<=0){

        alert("Informe uma quantidade válida.");

        return;
    }

    const mesaExiste=mesas.some(m=>Number(m.numero)===mesa);

    if(!mesaExiste){

        alert(
            "Essa mesa não está cadastrada."
        );

        return;
    }


    const pedido={

        id:Date.now(),

        mesa,
        cliente,
        produto,
        quantidade,
        valorUnitario,

        total:
        quantidade*valorUnitario,

        status,
         horario:
        new Date().toLocaleTimeString(
            "pt-BR",
            {
                hour:"2-digit",
                minute:"2-digit"
            }
        )

    };

    pedidos.push(pedido);

    salvarPedidos();
    atualizarValorMesa(mesa);
    limparPedido();
    renderizarPedidos();
    atualizarResumoPedidos();
    atualizarResumo();
}

function atualizarValorMesa(numero){

    const mesa=mesas.find(m=>Number(m.numero)===Number(numero));

    if(!mesa)return;

    const total=pedidos.filter(p=>Number(p.mesa)===Number(numero) &&p.status!=="Cancelado").reduce((s,p)=>s+Number(p.total||0),0);

    mesa.valor=total;

    salvarMesas();
    renderizarMesas();
    atualizarResumoMesas();
}


function renderizarPedidos(){

    const tabela=document.getElementById("tabelaPedidos");

    if(!tabela)return;

    tabela.innerHTML="";


    if(pedidos.length===0){

        tabela.innerHTML=`
        <tr>
            <td colspan="10">
                Nenhum pedido registrado.
            </td>
        </tr>

        `;

        atualizarResumoPedidos();

        return;
    }

    pedidos.forEach(pedido=>{

        tabela.innerHTML+=`

        <tr>
            <td>
                #${pedido.id.toString().slice(-4)}
            </td>

            <td>
                Mesa ${pedido.mesa}
            </td>

            <td>
                ${pedido.cliente||"-"}
            </td>

            <td>
                ${pedido.produto}
            </td>

            <td>
                ${pedido.quantidade}
            </td>

            <td>
                R$ ${(pedido.valorUnitario||0).toFixed(2)}
            </td>

            <td>
                <strong>
                    R$ ${(pedido.total||0).toFixed(2)}
                </strong>
            </td>

            <td>
                ${pedido.horario}
            </td>

            <td>
                ${statusPedidoHTML(pedido.status)}
            </td>

            <td>
                 ${botoesPedido(pedido)}

                <button
                    class="btn-red"
                    onclick="cancelarPedido(${pedido.id})">
                    🗑️
                </button>
            </td>
        
        </tr>
        `;
    });

     atualizarResumoPedidos();
}


function statusPedidoHTML(status){

    if(status==="Pendente"){

        return `
        <span class="status reservada">🟡 Pendente </span>
        `;
    }

    if(status==="Em preparo"){

        return `
        <span class="status reservada">🔵 Em preparo </span>
        `;
    }

    if(status==="Pronto"){

        return `
        <span class="status livre">🟢 Pronto </span>
        `;
    }

    if(status==="Entregue"){

        return `
        <span class="status livre">
        🟣 Entregue
        </span>
        `;
    }

    if(status==="Cancelado"){

        return `
        <span class="status ocupada">
        🔴 Cancelado
        </span>
        `;
    }

     return status;
}

function botoesPedido(pedido){

    if(pedido.status==="Pendente"){

        return `
        <button
        class="btn"onclick="alterarStatusPedido(${pedido.id},'Em preparo')">🔵 Preparar
        </button>
        `;
    }

    if(pedido.status==="Em preparo"){

        return `
        <button
        class="btn-green"onclick="alterarStatusPedido(${pedido.id},'Pronto')">🟢 Pronto
        </button>
        `;
    }

    if(pedido.status==="Pronto"){

        return `
        <button
        class="btn"onclick="alterarStatusPedido(${pedido.id},'Entregue')">🟣 Entregue
        </button>
        `;
    }

    return "";
}

function alterarStatusPedido(id,status){

    const pedido=pedidos.find(p=>p.id===id);

    if(!pedido)return;

    pedido.status=status;

    salvarPedidos();
    renderizarPedidos();
    atualizarValorMesa(pedido.mesa);
    atualizarResumoPedidos();
    atualizarResumo();
}


function cancelarPedido(id){

    const pedido=pedidos.find(p=>p.id===id);

    if(!pedido)return;

    if(!confirm(
        "Deseja cancelar este pedido?"
    )){
        return;
    }

    pedido.status="Cancelado";

    salvarPedidos();
    renderizarPedidos();
    atualizarValorMesa(
        pedido.mesa
    );

    atualizarResumoPedidos();
    atualizarResumo();
}


function limparPedido(){

    document.getElementById("mesaPedido").value="";
    document.getElementById("clientePedido").value="";
    document.getElementById("produtoPedido").value="";
    document.getElementById("quantidadePedido").value=1;
    document.getElementById("valorUnitarioPedido").value="";
    document.getElementById("statusPedido").value="Pendente";
}


function atualizarResumoPedidos(){

    const pendentes=pedidos.filter( p=>p.status==="Pendente").length;
    const preparo=pedidos.filter(p=>p.status==="Em preparo").length;
    const prontos=pedidos.filter(p=>p.status==="Pronto").length;
    const total=pedidos.filter(p=>p.status!=="Cancelado").reduce((s,p)=>s+Number(p.total||0),0);
    const elPendentes=document.getElementById("pedidosPendentes");
    const elPreparo=document.getElementById("pedidosPreparo");
    const elProntos=document.getElementById("pedidosProntos");
    const elTotal=document.getElementById("totalPedidos");


    if(elPendentes)
        elPendentes.textContent=pendentes;

    if(elPreparo)
        elPreparo.textContent=preparo;

    if(elProntos)
        elProntos.textContent=prontos;

    if(elTotal)
        elTotal.textContent=
        "R$ "+total.toFixed(2);
}

let reciclados =JSON.parse(localStorage.getItem("reciclados")) || [];

function registrarReciclado(){

    const alimento =document.getElementById("alimento" ).value.trim();
    const quantidade =document.getElementById("quantidadeReciclado").value;
    const motivo =document.getElementById("motivoReciclado").value;
    const mesa =document .getElementById("mesaReciclado").value.trim();
    const funcionario =document.getElementById("funcionarioReciclado" ) .value .trim();
    const observacao =document.getElementById("observacaoReciclado").value.trim();

        if(
        
        alimento === ""||quantidade === ""||motivo === ""||funcionario === ""

    ){

        alert(
            "Preencha os campos obrigatórios!"
        );

        return;

    }

    reciclados.push({

        alimento,
        quantidade:Number(quantidade),
        motivo,
        mesa,
        funcionario,
        observacao,
        dataHora:
        new Date()
        .toLocaleString(
             "pt-BR"
        )

    });

    localStorage.setItem("reciclados",JSON.stringify(reciclados));
    document.getElementById("alimento").value = "";
    document.getElementById("quantidadeReciclado").value = "";
    document.getElementById("motivoReciclado").value = "";
    document.getElementById("mesaReciclado").value = "";
    document.getElementById("funcionarioReciclado").value = "";
    document.getElementById("observacaoReciclado").value = "";

    renderizarReciclados();
    atualizarResumo();

}

function renderizarReciclados(){

    const tabela =document.getElementById("tabelaReciclados");

    if(!tabela)
        return;

    tabela.innerHTML = "";

    reciclados.forEach(
        r => {

            tabela.innerHTML += `

                <tr>

                    <td>
                        ${r.alimento}
                    </td>

                    <td>
                        ${r.quantidade}
                    </td>

                    <td>
                        ${r.motivo}
                    </td>

                    <td>
                        ${r.mesa || "-"}
                    </td>

                    <td>
                        ${r.funcionario}
                    </td>

                    <td>
                        ${r.dataHora}
                    </td>

                    <td>
                        ${r.observacao || "-"}
                    </td>

                </tr>
             `;
        }
    );
}

/*RH*/

let decimos=JSON.parse(localStorage.getItem("decimos"))||[]; 
function moeda(v)
{
    return Number(v||0)
    .toLocaleString("pt-BR",{style:"currency",currency:"BRL"})
}
function calcular13(){ 
    const salario=Number(document.getElementById("salario").value)||0;
    const avos=Math.max(0,Math.min(12,Number(document.getElementById("avos").value)||0));
    const descontos=Number(document.getElementById("descontos").value)||0;
    const bruto=salario*avos/12;
    const primeira=bruto/2;
    const liquido=Math.max(0,bruto-descontos);
    document.getElementById("resultado").innerHTML= `<div class="resumo"> 
        <div class="box">Avos<div class="valor">${avos}/12
            </div>
        </div>
        <div class="box">13º bruto<div class="valor">${moeda(bruto)}
            </div>
        </div> 
        <div class="box">1ª parcela (referência)<div class="valor">${moeda(primeira)}
            </div>
        </div>
        <div class="box">Descontos<div class="valor">${moeda(descontos)}
            </div>
        </div>
        
        <div class="box">Líquido estimado<div class="valor">${moeda(liquido)}
            </div>
        </div> 
        
        </div>`; 
        return {
            bruto,
            primeira,
            liquido,
            avos,
            descontos
        }; 
    } 
    
    function salvar13(){ 
        const c=calcular13(); 
        const funcionario=document.getElementById("funcionario").value.trim(); 
        if(!funcionario)
        {
            alert("Informe o funcionário.");
        return
    } decimos.push({
          id:Date.now(),
          funcionario,
          ano:Number(document.getElementById("ano").value),
          avos:c.avos,
          bruto:c.bruto,
          descontos:c.descontos,
          liquido:c.liquido,
          status:"Pendente"
        }
    ); 
    
    localStorage
    .setItem("decimos",JSON.stringify(decimos)); 
    renderizar(); 
    alert("13º salvo no protótipo.");
} 

function renderizar(){ 
    document.getElementById("tabela").innerHTML=decimos.map(d=>` 
    <tr>
        <td>${d.funcionario}</td>
        <td>${d.ano}</td>
        <td>${d.avos}/12</td>
        <td>${moeda(d.bruto)}</td>
        <td>${moeda(d.descontos)}</td>
        <td>${moeda(d.liquido)}</td>
        <td>${d.status}</td>
    </tr>`
    ).join(""); 
} 

function limpar(){ 
    document.getElementById("funcionario").value=""; 
    document.getElementById("salario").value=""; 
    document.getElementById("admissao").value=""; 
    document.getElementById("avos").value=12; 
    document.getElementById("descontos").value=0; 
    document.getElementById("resultado").innerHTML=""; 
} 

/* INICIAR */
renderizarTabela()
inicializarMesas();
renderizarMesas();
renderizarPedidos();
renderizarReciclados();
renderizar();

</script>

</body>
</html>
