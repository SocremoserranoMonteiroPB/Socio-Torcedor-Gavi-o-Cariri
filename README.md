<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Carteirinha Sócio-Torcedor</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            background-color: #f4f4f4;
            padding: 20px;
        }
        .container {
            background-color: white;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            max-width: 400px;
            margin: auto;
        }
        .botao {
            display: inline-block;
            margin-top: 10px;
            padding: 10px;
            background-color: #006400;
            color: white;
            text-decoration: none;
            border-radius: 5px;
            cursor: pointer;
        }
        .carteirinha {
            display: none;
            margin-top: 20px;
            padding: 15px;
            background-color: #006400;
            color: white;
            border-radius: 8px;
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
        <h1>Seja bem-vindo ao site Sócio-Torcedor Socremo-Serrano!</h1>
        <p>"Juntos, somos mais fortes!"</p>
    </div>
    <div class="container">
        <h2>Gerar Carteirinha Digital</h2>
        <form id="socioForm" onsubmit="return enviarFormulario()">
            <label>Nome:</label><br>
            <input type="text" id="nome" required><br><br>
            <label>Plano:</label><br>
            <select id="plano">
                <option value="Gavião">Plano Gavião - R$ 15 (15% de desconto nos ingressos)</option>
                <option value="Carcará">Plano Carcará - R$ 30 (30% de desconto nos ingressos + sorteio de brindes)</option>
                <option value="Elite Serrano">Plano Elite Serrano - R$ 45 (50% de desconto nos ingressos + sorteio de brindes)</option>
            </select><br><br>
            <button type="submit" class="botao">Realizar Pagamento</button>
        </form>
        <div id="carteirinha" class="carteirinha">
            <h3>Carteirinha Sócio-Torcedor</h3>
            <p id="nomeSocio"></p>
            <p id="planoSocio"></p>
            <p>QR Code de Validação</p>
            <img id="qrCode" src="" alt="QR Code" width="100">
        </div>
    </div>
    <script>
        function enviarFormulario() {
            let nome = document.getElementById("nome").value;
            let plano = document.getElementById("plano").value;
            
            if (nome === "") {
                alert("Por favor, preencha seu nome.");
                return false;
            }
            
            let email = "seuemail@example.com";
            let assunto = "Novo Sócio-Torcedor: " + nome;
            let corpo = "Nome: " + nome + "\nPlano: " + plano;
            
            let mailtoLink = "mailto:" + email + "?subject=" + encodeURIComponent(assunto) + "&body=" + encodeURIComponent(corpo);
            window.location.href = mailtoLink;
            
            gerarCarteirinha(nome, plano);
            
            return false;
        }

        function gerarCarteirinha(nome, plano) {
            document.getElementById("nomeSocio").innerText = "Nome: " + nome;
            document.getElementById("planoSocio").innerText = "Plano: " + plano;
            document.getElementById("qrCode").src = "https://api.qrserver.com/v1/create-qr-code/?size=100x100&data=" + encodeURIComponent(nome + " - " + plano);
            document.getElementById("carteirinha").style.display = "block";
        }
    </script>
</body>
</html>
