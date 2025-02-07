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
        .banner {
            background-color: #ffcc00;
            color: black;
            padding: 10px;
            font-size: 20px;
            font-weight: bold;
            position: fixed;
            width: 100%;
            top: 0;
            left: 0;
            animation: moveBanner 10s linear infinite;
        }
        @keyframes moveBanner {
            from { transform: translateX(100%); }
            to { transform: translateX(-100%); }
        }
        .container {
            background-color: rgba(0, 0, 0, 0.8);
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            max-width: 800px;
            margin: auto;
            margin-top: 50px;
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
            width: 200px;
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
            width: 200px;
            margin-bottom: 10px;
        }
        .header {
            text-align: center;
            margin-bottom: 20px;
        }
    </style>
</head>
<body>
    <div class="banner">VENHA SER NOSSO SÓCIO-TORCEDOR!</div>
    <audio autoplay loop>
        <source src="musica.mp3" type="audio/mpeg">
    </audio>
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
                <button class="botao">Quero Assinar</button>
            </div>
            <div class="plano">
                <h3>Plano Carcará</h3>
                <p>R$ 30/mês</p>
                <p>30% de desconto no ingresso</p>
                <p>Sorteio de brindes</p>
                <button class="botao">Quero Assinar</button>
            </div>
            <div class="plano">
                <h3>Plano Elite Serrano</h3>
                <p>R$ 45/mês</p>
                <p>50% de desconto no ingresso</p>
                <p>Sorteio de brindes</p>
                <button class="botao">Quero Assinar</button>
            </div>
        </div>
    </div>
    <div class="container" style="margin-top: 20px;">
        <h2>História do Clube</h2>
        <p>O Socremo-Serrano é um time tradicional de Monteiro-PB, com grande paixão da torcida. Em 2025, o time disputará a 2ª divisão do Campeonato Paraibano Masculino, além do Campeonato Paraibano Feminino e as categorias de base Sub-15, Sub-17 e Sub-20.</p>
    </div>
</body>
</html>
