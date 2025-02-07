<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sócio-Torcedor Socremo-Serrano</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            background-image: url('papel-de-parede.jpg');
            background-size: cover;
            background-position: center;
            padding: 20px;
            color: white;
        }
        .container {
            background-color: rgba(0, 0, 0, 0.8);
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            max-width: 600px;
            margin: auto;
        }
        .planos {
            display: flex;
            justify-content: space-around;
            flex-wrap: wrap;
            gap: 10px;
        }
        .plano {
            background-color: #006400;
            color: white;
            padding: 15px;
            border-radius: 8px;
            width: 180px;
            text-align: center;
        }
        .botao {
            display: inline-block;
            margin-top: 10px;
            padding: 10px;
            background-color: #ffcc00;
            color: black;
            text-decoration: none;
            border-radius: 5px;
            cursor: pointer;
        }
        .logo {
            width: 150px;
            margin-bottom: 10px;
        }
        .header {
            text-align: center;
            margin-bottom: 20px;
        }
    </style>
</head>
<body>
    <div class="header">
        <img src="logo.png" alt="Logo Socremo-Serrano" class="logo">
        <h1>Seja um Sócio-Torcedor e fortaleça o nosso time!</h1>
    </div>
    <div class="container">
        <h2>Escolha seu Plano</h2>
        <div class="planos">
            <div class="plano">
                <h3>Plano Gavião</h3>
                <p>R$ 15/mês</p>
                <p>15% de desconto no ingresso</p>
                <button class="botao" onclick="selecionarPlano('Gavião', 15)">Quero Assinar</button>
            </div>
            <div class="plano">
                <h3>Plano Carcará</h3>
                <p>R$ 30/mês</p>
                <p>30% de desconto no ingresso</p>
                <p>Sorteio de brindes</p>
                <button class="botao" onclick="selecionarPlano('Carcará', 30)">Quero Assinar</button>
            </div>
            <div class="plano">
                <h3>Plano Elite Serrano</h3>
                <p>R$ 45/mês</p>
                <p>50% de desconto no ingresso</p>
                <p>Sorteio de brindes</p>
                <button class="botao" onclick="selecionarPlano('Elite Serrano', 45)">Quero Assinar</button>
            </div>
        </div>
        <div id="formulario" style="display:none; margin-top: 20px;">
            <h2>Preencha seus dados</h2>
            <form id="socioForm" onsubmit="return enviarFormulario()">
                <label>Nome:</label><br>
                <input type="text" id="nome" required><br><br>
                <input type="hidden" id="planoSelecionado">
                <label>Forma de Pagamento:</label><br>
                <select id="pagamento" required>
                    <option value="PIX">PIX</option>
                    <option value="Cartão de Crédito">Cartão de Crédito</option>
                    <option value="Boleto">Boleto</option>
                </select><br><br>
                <button type="submit" class="botao">Confirmar Associação</button>
            </form>
        </div>
    </div>
    <div class="container" style="margin-top: 20px;">
        <h2>História do Clube</h2>
        <p>O Socremo-Serrano é um time tradicional de Monteiro-PB, com grande paixão da torcida. Em 2025, o time disputará a 2ª divisão do Campeonato Paraibano Masculino, além do Campeonato Paraibano Feminino e as categorias de base Sub-15, Sub-17 e Sub-20.</p>
    </div>
    <script>
        function selecionarPlano(plano, valor) {
            document.getElementById("planoSelecionado").value = plano + " - R$ " + valor + "/mês";
            document.getElementById("formulario").style.display = "block";
        }

        function enviarFormulario() {
            let nome = document.getElementById("nome").value;
            let plano = document.getElementById("planoSelecionado").value;
            let pagamento = document.getElementById("pagamento").value;
            
            if (nome === "") {
                alert("Por favor, preencha seu nome.");
                return false;
            }
            
            let email = "seuemail@example.com";
            let assunto = "Novo Sócio-Torcedor: " + nome;
            let corpo = "Nome: " + nome + "\nPlano: " + plano + "\nForma de Pagamento: " + pagamento + "\nConfirmação de associação.";
            
            let mailtoLink = "mailto:" + email + "?subject=" + encodeURIComponent(assunto) + "&body=" + encodeURIComponent(corpo);
            window.location.href = mailtoLink;
            
            return false;
        }
    </script>
</body>
</html>

