# Jogocopaperguntas-
Jogo de perguntas e respostas da 

<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
    <title>Quiz das Copas do Mundo - Edição Especialista</title>
    
    <meta name="description" content="Quiz ultra-difícil sobre Copas do Mundo! Teste seus conhecimentos com perguntas de especialista.">
    <meta name="keywords" content="quiz, copa do mundo, futebol, perguntas difíceis, especialista">
    <meta name="author" content="Quiz Copa">
    <meta name="version" content="2.1.2">
    
    <!-- Google AdSense -->
    <script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js?client=ca-pub-5555223308090320534"
     crossorigin="anonymous"></script>
    
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', 'Segoe UI', system-ui, sans-serif;
        }

        body {
            min-height: 100vh;
            background: linear-gradient(135deg, #009c3b 0%, #002776 100%);
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 20px;
        }

        .container {
            max-width: 950px;
            width: 100%;
            background: white;
            border-radius: 50px;
            box-shadow: 0 20px 40px rgba(0,0,0,0.3);
            overflow: hidden;
            border: 3px solid #ffdf00;
        }

        .ad-top {
            background: linear-gradient(135deg, #f8f9fa, #e9ecef);
            text-align: center;
            padding: 12px;
            border-bottom: 1px solid #dee2e6;
        }
        .ad-top small { color: #6c757d; font-size: 10px; display: block; margin-bottom: 5px; text-transform: uppercase; letter-spacing: 1px; }
        .ad-top .adsbygoogle { display: inline-block; width: 728px; height: 90px; }

        .ad-bottom {
            background: linear-gradient(135deg, #f8f9fa, #e9ecef);
            text-align: center;
            padding: 12px;
            border-top: 1px solid #dee2e6;
        }
        .ad-bottom small { color: #6c757d; font-size: 10px; display: block; margin-bottom: 5px; text-transform: uppercase; letter-spacing: 1px; }
        .ad-bottom .adsbygoogle { display: inline-block; width: 728px; height: 90px; }

        .header {
            background: linear-gradient(135deg, #009c3b 0%, #002776 100%);
            padding: 25px 20px;
            text-align: center;
            position: relative;
        }

        .header::before { content: "🏆"; position: absolute; left: 20px; top: 50%; transform: translateY(-50%); font-size: 35px; animation: balanca 2s infinite; }
        .header::after { content: "⚽"; position: absolute; right: 20px; top: 50%; transform: translateY(-50%); font-size: 35px; animation: balanca 2s infinite 1s; }

        @keyframes balanca { 0%, 100% { transform: translateY(-50%) rotate(0deg); } 50% { transform: translateY(-50%) rotate(15deg); } }

        .premio { font-size: 2rem; font-weight: 800; color: #ffdf00; text-shadow: 2px 2px 4px rgba(0,0,0,0.3); }
        .nivel-info { color: white; margin-top: 5px; font-size: 0.9rem; }
        .dificuldade { display: inline-block; background: rgba(0,0,0,0.3); padding: 3px 12px; border-radius: 20px; margin-top: 8px; font-size: 0.8rem; }
        .dificuldade.facil { background: #4caf50; }
        .dificuldade.medio { background: #ff9800; }
        .dificuldade.dificil { background: #f44336; }
        .dificuldade.especialista { background: #9c27b0; }

        .progresso { height: 8px; background: #e0e0e0; }
        .progresso-bar { width: 0%; height: 100%; background: linear-gradient(90deg, #ffdf00, #009c3b); transition: width 0.3s; }

        .quiz-content { padding: 30px; }
        .pergunta { font-size: 1.2rem; font-weight: 700; color: #002776; background: #f8f9fa; padding: 20px; border-radius: 20px; margin-bottom: 30px; text-align: center; border-left: 5px solid #ffdf00; }

        .opcoes { display: grid; grid-template-columns: repeat(2, 1fr); gap: 15px; margin-bottom: 30px; }
        .opcao { background: white; border: 2px solid #dee2e6; border-radius: 15px; padding: 15px; display: flex; align-items: center; gap: 15px; cursor: pointer; transition: all 0.3s; }
        .opcao:hover { transform: translateY(-3px); border-color: #ffdf00; box-shadow: 0 5px 15px rgba(0,0,0,0.1); }
        .opcao.expulsa { opacity: 0.3; pointer-events: none; text-decoration: line-through; background: #ccc; }
        .letra { width: 45px; height: 45px; background: linear-gradient(135deg, #ffdf00, #ffc107); border-radius: 12px; display: flex; align-items: center; justify-content: center; font-weight: 800; font-size: 1.1rem; color: #002776; }
        .texto-opcao { flex: 1; font-size: 0.95rem; color: #333; }

        .opcao.correct { background: #4caf50; animation: pisca 0.5s 3; }
        .opcao.correct .letra, .opcao.correct .texto-opcao { color: white; }
        @keyframes pisca { 0%,100%{background:#4caf50} 50%{background:#81c784} }

        .opcao.wrong { background: #f44336; animation: treme 0.3s; }
        .opcao.wrong .letra, .opcao.wrong .texto-opcao { color: white; }
        @keyframes treme { 0%,100%{transform:translateX(0)} 25%{transform:translateX(-5px)} 75%{transform:translateX(5px)} }

        .recursos { display: flex; justify-content: center; gap: 15px; margin-bottom: 25px; flex-wrap: wrap; }
        .btn-recurso { background: #002776; border: none; border-radius: 50px; padding: 10px 20px; color: #ffdf00; font-weight: bold; cursor: pointer; transition: all 0.3s; font-size: 0.9rem; }
        .btn-recurso:hover:not(:disabled) { transform: translateY(-2px); background: #003399; }
        .btn-recurso:disabled { opacity: 0.5; cursor: not-allowed; }

        .feedback { background: #f0f0f0; padding: 15px; border-radius: 15px; margin-bottom: 25px; text-align: center; border-left: 5px solid #ffdf00; }

        .btn { display: block; width: 100%; margin-bottom: 10px; background: linear-gradient(135deg, #ffdf00, #ffc107); border: none; padding: 14px; border-radius: 50px; font-size: 1rem; font-weight: bold; cursor: pointer; }
        .btn:disabled { opacity: 0.5; }
        .btn-desistir { background: #666; color: white; }
        .btn-reiniciar { background: #6c757d; color: white; }

        .footer {
            background: linear-gradient(135deg, #1a1a2e, #16213e);
            padding: 20px;
            text-align: center;
            border-top: 2px solid #ffdf00;
        }
        .footer p { font-size: 11px; color: #aaa; margin: 5px 0; }
        .footer a { color: #ffdf00; text-decoration: none; cursor: pointer; }
        .footer a:hover { color: #ffc107; text-decoration: underline; }
        .footer .versao { color: #ffdf00; font-weight: bold; background: rgba(255,223,0,0.1); display: inline-block; padding: 2px 10px; border-radius: 20px; font-size: 10px; }

        /* MODAIS */
        .modal-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.95);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 2000;
            animation: fadeIn 0.3s;
        }
        .modal-content {
            background: white;
            border-radius: 40px;
            max-width: 600px;
            width: 90%;
            max-height: 80vh;
            overflow-y: auto;
            padding: 30px;
            position: relative;
            animation: slideUp 0.3s;
        }
        @keyframes slideUp { from { transform: translateY(50px); opacity: 0; } to { transform: translateY(0); opacity: 1; } }
        .modal-content h2 { color: #002776; border-left: 4px solid #ffdf00; padding-left: 15px; margin-bottom: 20px; }
        .modal-content h3 { color: #009c3b; margin: 20px 0 10px; }
        .modal-content p { color: #333; line-height: 1.6; margin-bottom: 10px; }
        .close-modal { position: absolute; top: 15px; right: 20px; font-size: 28px; cursor: pointer; color: #999; }
        .close-modal:hover { color: #f44336; }
        .modal-btn { background: linear-gradient(135deg, #ffdf00, #ffc107); border: none; padding: 10px 20px; border-radius: 30px; font-weight: bold; cursor: pointer; margin-top: 20px; }

        /* MODAIS DO JOGO */
        .modal-var, .modal-juiz, .modal-trofeu {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.95);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 1000;
            animation: fadeIn 0.3s;
        }
        @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }

        .var-box {
            background: linear-gradient(135deg, #009c3b, #002776);
            border-radius: 60px;
            padding: 40px;
            max-width: 500px;
            width: 90%;
            text-align: center;
            border: 4px solid #ffdf00;
            animation: varPop 0.5s cubic-bezier(0.68, -0.55, 0.265, 1.55);
        }
        @keyframes varPop { 0% { transform: scale(0.2) rotate(-180deg); opacity: 0; } 50% { transform: scale(1.1) rotate(5deg); } 100% { transform: scale(1) rotate(0); opacity: 1; } }
        .var-box h2 { color: #ffdf00; margin-bottom: 15px; font-size: 1.8rem; }
        .var-bola { font-size: 3rem; margin: 10px 0; animation: giraBola 1s linear infinite; }
        @keyframes giraBola { from { transform: rotate(0deg); } to { transform: rotate(360deg); } }
        .var-tempo { font-size: 3rem; color: #ffdf00; margin: 20px; background: rgba(0,0,0,0.5); display: inline-block; padding: 10px 25px; border-radius: 30px; animation: pulseTempo 1s infinite; }
        @keyframes pulseTempo { 0%, 100% { transform: scale(1); } 50% { transform: scale(1.1); } }
        .var-scan { width: 100%; height: 3px; background: linear-gradient(90deg, transparent, #ffdf00, transparent); margin: 20px 0; animation: scan 1s linear infinite; }
        @keyframes scan { 0% { transform: translateX(-100%); } 100% { transform: translateX(100%); } }
        .var-dica { font-size: 1.2rem; color: #ffdf00; margin: 20px; padding: 15px; background: rgba(0,0,0,0.4); border-radius: 30px; animation: revelaDica 0.5s ease-out; }
        @keyframes revelaDica { from { opacity: 0; transform: scale(0.8); letter-spacing: 5px; } to { opacity: 1; transform: scale(1); letter-spacing: normal; } }
        .fechar-var { background: #ffdf00; border: none; padding: 12px 35px; border-radius: 50px; font-weight: bold; cursor: pointer; margin-top: 15px; }

        .cartao-box {
            background: linear-gradient(135deg, #1a1a2e, #16213e);
            border-radius: 30px;
            padding: 40px;
            text-align: center;
            border: 4px solid #ffdf00;
            animation: cartaoEntrada 0.5s cubic-bezier(0.68, -0.55, 0.265, 1.55);
        }
        @keyframes cartaoEntrada { 0% { transform: scale(0.2) rotate(-10deg) translateY(-100px); opacity: 0; } 60% { transform: scale(1.1) rotate(2deg); } 100% { transform: scale(1) rotate(0) translateY(0); opacity: 1; } }
        .cartao-titulo { font-size: 1.5rem; font-weight: bold; color: white; text-transform: uppercase; letter-spacing: 3px; margin-bottom: 20px; }
        .cartoes { display: flex; justify-content: center; gap: 30px; margin: 20px 0; }
        .cartao { width: 120px; padding: 20px; border-radius: 15px; text-align: center; animation: cartaoAparece 0.4s ease-out forwards; opacity: 0; transform: scale(0); }
        .cartao:nth-child(1) { animation-delay: 0.2s; }
        .cartao:nth-child(2) { animation-delay: 0.4s; }
        @keyframes cartaoAparece { 0% { opacity: 0; transform: scale(0) rotate(-180deg); } 100% { opacity: 1; transform: scale(1) rotate(0); } }
        .cartao-amarelo { background: #ffc107; border: 3px solid #ff8f00; }
        .cartao-vermelho { background: #f44336; border: 3px solid #c62828; }
        .cartao-numero { font-size: 4rem; font-weight: 800; color: #1a1a2e; }
        .cartao-legenda { font-size: 0.8rem; color: #1a1a2e; font-weight: bold; margin-top: 10px; }
        .cartao-mensagem { color: white; font-size: 1rem; margin: 20px 0; }
        .fechar-juiz { background: #ffdf00; border: none; padding: 10px 30px; border-radius: 50px; font-weight: bold; cursor: pointer; margin-top: 15px; }

        .trofeu-box {
            background: linear-gradient(135deg, #009c3b, #002776);
            border-radius: 60px;
            padding: 50px;
            max-width: 500px;
            width: 90%;
            text-align: center;
            border: 4px solid #ffdf00;
            animation: trofeuPop 0.6s ease-out;
        }
        @keyframes trofeuPop { 0% { transform: scale(0.2) rotate(-180deg); opacity: 0; } 70% { transform: scale(1.1) rotate(5deg); } 100% { transform: scale(1) rotate(0); opacity: 1; } }
        .trofeu-icon { font-size: 5rem; margin: 20px; animation: trofeuBrilha 1s infinite; }
        @keyframes trofeuBrilha { 0%, 100% { text-shadow: 0 0 0px #ffdf00; transform: scale(1); } 50% { text-shadow: 0 0 30px #ffdf00; transform: scale(1.1); } }
        .trofeu-box h2 { color: #ffdf00; font-size: 2rem; }
        .trofeu-box p { color: white; font-size: 1.2rem; margin: 15px; }

        @media (max-width: 800px) {
            .ad-top .adsbygoogle { width: 320px; height: 100px; }
            .ad-bottom .adsbygoogle { width: 320px; height: 100px; }
        }
        @media (max-width: 600px) {
            .opcoes { grid-template-columns: 1fr; }
            .pergunta { font-size: 1rem; }
            .premio { font-size: 1.3rem; }
            .recursos { gap: 10px; }
            .btn-recurso { padding: 8px 12px; font-size: 0.75rem; }
            .cartao { width: 80px; padding: 12px; }
            .cartao-numero { font-size: 2rem; }
        }
    </style>
</head>
<body>

<div class="container">
    <div class="ad-top">
        <small>PUBLICIDADE</small>
        <ins class="adsbygoogle"
             style="display:inline-block;width:728px;height:90px"
             data-ad-client="ca-pub-8229926888509165"
             data-ad-slot="SEU_SLOT_TOPO"></ins>
        <script>(adsbygoogle = window.adsbygoogle || []).push({});</script>
    </div>

    <div class="container-inner" id="container"></div>

    <div class="ad-bottom">
        <small>PUBLICIDADE</small>
        <ins class="adsbygoogle"
             style="display:inline-block;width:728px;height:90px"
             data-ad-client="ca-pub-8229926888509165"
             data-ad-slot="SEU_SLOT_RODAPE"></ins>
        <script>(adsbygoogle = window.adsbygoogle || []).push({});</script>
    </div>

    <div class="footer">
        <p>🏆 QUIZ DAS COPAS DO MUNDO - VERSÃO <span class="versao">2.1.2</span> 🏆</p>
        <p>© 2025 Quiz das Copas - Todos os direitos reservados</p>
        <p><a onclick="abrirModal('privacidade')">📋 Política de Privacidade</a> | <a onclick="abrirModal('termos')">📜 Termos de Uso</a></p>
        <p style="font-size: 9px; opacity: 0.6;">⭐ Edição Especialista - VAR com animação! ⭐</p>
    </div>
</div>

<div id="modalContainer" style="display: none;"></div>

<script>
    // ============================================================
    // CONTEÚDO DA POLÍTICA DE PRIVACIDADE
    // ============================================================
    const conteudos = {
        privacidade: {
            titulo: "📋 Política de Privacidade",
            html: `<p><strong>Última atualização:</strong> 16 de Abril de 2025</p>
                <h3>1. Informações Gerais</h3><p>Quiz das Copas do Mundo - Edição Especialista</p>
                <h3>2. Google AdSense</h3><p>Este site utiliza o Google AdSense. Você pode desativar anúncios personalizados em <a href="https://www.google.com/settings/ads" target="_blank">Configurações de anúncios do Google</a>.</p>
                <h3>3. Contato</h3><p>📧 fabin.rj88@gmail.com<br>📍 Nossa Senhora de Copacabana, Copacabana - RJ</p>`
        },
        termos: {
            titulo: "📜 Termos de Uso",
            html: `<p><strong>Última atualização:</strong> 16 de Abril de 2025</p>
                <h3>1. Uso do Site</h3><p>Quiz gratuito para entretenimento. Perguntas de alto nível de dificuldade.</p>
                <h3>2. Contato</h3><p>📧 fabin.rj88@gmail.com</p>`
        }
    };

    function abrirModal(tipo) {
        const modalContainer = document.getElementById("modalContainer");
        const conteudo = conteudos[tipo];
        modalContainer.innerHTML = `
            <div class="modal-overlay" onclick="fecharModal(event)">
                <div class="modal-content">
                    <span class="close-modal" onclick="fecharModal()">&times;</span>
                    <h2>${conteudo.titulo}</h2>
                    ${conteudo.html}
                    <button class="modal-btn" onclick="fecharModal()">FECHAR</button>
                </div>
            </div>
        `;
        modalContainer.style.display = "block";
    }

    function fecharModal(event) {
        if (event && event.target !== event.currentTarget && event.target.className !== "modal-btn" && event.target.className !== "close-modal") return;
        document.getElementById("modalContainer").style.display = "none";
        document.getElementById("modalContainer").innerHTML = "";
    }

    // ============================================================
    // PERGUNTAS - NÍVEL FÁCIL (15 perguntas)
    // ============================================================
    const PERGUNTAS_FACIL = [
        { text: "Qual país venceu a primeira Copa do Mundo em 1930?", options: ["Brasil", "Uruguai", "Argentina", "Itália"], correct: 1, usada: false },
        { text: "Qual seleção tem mais títulos mundiais?", options: ["Alemanha", "Itália", "Argentina", "Brasil"], correct: 3, usada: false },
        { text: "Quem é considerado o Rei do Futebol?", options: ["Maradona", "Pelé", "Messi", "Cristiano Ronaldo"], correct: 1, usada: false },
        { text: "Em que ano o Brasil ganhou o primeiro título?", options: ["1958", "1962", "1970", "1994"], correct: 0, usada: false },
        { text: "Qual o mascote da Copa de 2014?", options: ["Fuleco", "Zakumi", "La'eeb", "Ciao"], correct: 0, usada: false },
        { text: "Qual país sediou a Copa de 2018?", options: ["Catar", "Rússia", "França", "Inglaterra"], correct: 1, usada: false },
        { text: "Qual seleção é conhecida como 'Canarinho'?", options: ["Argentina", "Alemanha", "Brasil", "Itália"], correct: 2, usada: false },
        { text: "Quantas Copas a Alemanha venceu até 2022?", options: ["2", "3", "4", "5"], correct: 2, usada: false },
        { text: "Qual a cor da camisa da seleção brasileira?", options: ["Azul", "Amarela", "Verde", "Branca"], correct: 1, usada: false },
        { text: "Qual seleção venceu a Copa de 2010?", options: ["Holanda", "Espanha", "Alemanha", "Uruguai"], correct: 1, usada: false },
        { text: "Qual o apelido da seleção argentina?", options: ["Albiceleste", "Canarinho", "Laranja", "Tricolor"], correct: 0, usada: false },
        { text: "Qual estádio sediou a final da Copa de 1950?", options: ["Maracanã", "Morumbi", "Mineirão", "Beira-Rio"], correct: 0, usada: false },
        { text: "Qual jogador é conhecido como 'El Mágico'?", options: ["Maradona", "Messi", "Ronaldo", "Zico"], correct: 0, usada: false },
        { text: "Quantos gols Pelé fez na Copa de 1958?", options: ["6", "4", "5", "3"], correct: 0, usada: false },
        { text: "Qual seleção tem 4 estrelas na camisa?", options: ["Alemanha", "Itália", "França", "Uruguai"], correct: 0, usada: false }
    ];

    // ============================================================
    // PERGUNTAS - NÍVEL MÉDIO (15 perguntas)
    // ============================================================
    const PERGUNTAS_MEDIO = [
        { text: "Qual foi o placar da final de 2014 (Brasil x Alemanha)?", options: ["1x7", "0x7", "2x7", "1x5"], correct: 0, usada: false },
        { text: "Quem é o maior artilheiro da história das Copas?", options: ["Ronaldo", "Miroslav Klose", "Pelé", "Messi"], correct: 1, usada: false },
        { text: "Qual país foi vice-campeão em 2022?", options: ["França", "Croácia", "Marrocos", "Argentina"], correct: 0, usada: false },
        { text: "Quem fez o gol do título do Brasil em 1994?", options: ["Romário", "Bebeto", "Dunga", "Cafu"], correct: 2, usada: false },
        { text: "Qual jogador tem mais partidas em Copas?", options: ["Messi", "Maradona", "Lothar Matthäus", "Cristiano Ronaldo"], correct: 2, usada: false },
        { text: "Qual o nome do estádio que sediou a final de 2002?", options: ["Maracanã", "Yokohama", "Lusail", "Stade de France"], correct: 1, usada: false },
        { text: "Quem foi o técnico campeão com o Brasil em 2002?", options: ["Zagallo", "Felipão", "Parreira", "Tite"], correct: 1, usada: false },
        { text: "Quantas Copas a Argentina venceu até 2022?", options: ["2", "3", "4", "1"], correct: 0, usada: false },
        { text: "Qual seleção feminina tem mais títulos?", options: ["EUA", "Alemanha", "Brasil", "Japão"], correct: 0, usada: false },
        { text: "Qual seleção é conhecida como 'Laranja Mecânica'?", options: ["Holanda", "Bélgica", "Espanha", "Portugal"], correct: 0, usada: false },
        { text: "Qual jogador tem o recorde de mais gols em uma única Copa?", options: ["Just Fontaine", "Pelé", "Ronaldo", "Klose"], correct: 0, usada: false },
        { text: "Em que ano a Croácia foi vice-campeã?", options: ["2018", "2022", "1998", "2006"], correct: 0, usada: false },
        { text: "Qual jogador ganhou a Bola de Ouro da Copa de 2014?", options: ["Messi", "Neuer", "Ronaldo", "James"], correct: 0, usada: false },
        { text: "Qual seleção eliminou o Brasil nas quartas de 2018?", options: ["Bélgica", "França", "Croácia", "Uruguai"], correct: 0, usada: false },
        { text: "Quantos gols Mbappé fez na final de 2022?", options: ["3", "2", "4", "1"], correct: 0, usada: false }
    ];

    // ============================================================
    // PERGUNTAS - NÍVEL DIFÍCIL (20 perguntas)
    // ============================================================
    const PERGUNTAS_DIFICIL = [
        { text: "Qual jogador fez o gol mais rápido da história das Copas?", options: ["Hakan Şükür", "Ronaldo", "Klose", "Owen"], correct: 0, usada: false },
        { text: "Qual técnico conquistou Copas por países diferentes?", options: ["Zagallo", "Beckenbauer", "Parreira", "Lippi"], correct: 0, usada: false },
        { text: "Qual foi o maior público em uma final de Copa?", options: ["199.854", "120.000", "110.000", "95.000"], correct: 0, usada: false },
        { text: "Qual jogador é o único a marcar em duas finais diferentes?", options: ["Pelé", "Vavá", "Zidane", "Mbappé"], correct: 1, usada: false },
        { text: "Qual o nome do estádio da final de 2022?", options: ["Lusail", "Khalifa", "Education City", "Ahmad Bin Ali"], correct: 0, usada: false },
        { text: "Em que ano o VAR foi usado pela primeira vez na Copa?", options: ["2018", "2022", "2014", "2010"], correct: 0, usada: false },
        { text: "Qual país perdeu duas finais seguidas (1974 e 1978)?", options: ["Holanda", "Alemanha", "Argentina", "Brasil"], correct: 0, usada: false },
        { text: "Quem foi o artilheiro da Copa de 1994?", options: ["Stoichkov", "Romário", "Baggio", "Salenko"], correct: 3, usada: false },
        { text: "Qual jogador mais velho a marcar em uma Copa?", options: ["Roger Milla", "Cafu", "Buffon", "Matthäus"], correct: 0, usada: false },
        { text: "Qual país mais sediou Copas do Mundo?", options: ["México", "Brasil", "Itália", "Alemanha"], correct: 0, usada: false },
        { text: "Qual árbitro apitou a final da Copa de 2002?", options: ["Pierluigi Collina", "Markus Merk", "Anders Frisk", "Urs Meier"], correct: 0, usada: false },
        { text: "Qual juiz italiano é considerado o melhor da história?", options: ["Pierluigi Collina", "Roberto Rosetti", "Nicola Rizzoli", "Gianluca Rocchi"], correct: 0, usada: false },
        { text: "Qual árbitro apitou a final da Copa de 1998?", options: ["Said Belqola", "Pierluigi Collina", "Kim Milton Nielsen", "Hugh Dallas"], correct: 0, usada: false },
        { text: "Qual árbitro apitou a final da Copa de 2014?", options: ["Nicola Rizzoli", "Björn Kuipers", "Mark Geiger", "Nestor Pitana"], correct: 0, usada: false },
        { text: "Qual jogador tem o recorde de mais assistências em uma única Copa?", options: ["Maradona", "Messi", "Pelé", "Zidane"], correct: 0, usada: false },
        { text: "Qual seleção tem o maior número de jogos em Copas?", options: ["Brasil", "Alemanha", "Itália", "Argentina"], correct: 0, usada: false },
        { text: "Qual foi o primeiro gol de falta na história das Copas?", options: ["Pelé", "Maradona", "Rivelino", "Zico"], correct: 2, usada: false },
        { text: "Qual jogador tem o recorde de mais Copas disputadas?", options: ["Antonio Carbajal", "Messi", "Cafu", "Maradona"], correct: 0, usada: false },
        { text: "Qual foi o maior público da história das Copas (não final)?", options: ["199.854", "150.000", "180.000", "170.000"], correct: 0, usada: false },
        { text: "Qual jogador fez o gol mais bonito da história das Copas?", options: ["Maradona", "Pelé", "Zidane", "Bergkamp"], correct: 0, usada: false }
    ];

    // ============================================================
    // PERGUNTAS - NÍVEL ESPECIALISTA (15 perguntas)
    // ============================================================
    const PERGUNTAS_ESPECIALISTA = [
        { text: "Qual árbitro argentino apitou a final da Copa de 2018?", options: ["Nestor Pitana", "Piero Maza", "Fernando Rapallini", "Patricio Loustau"], correct: 0, usada: false },
        { text: "Qual foi o primeiro árbitro a usar o spray de barreira na Copa?", options: ["Ravshan Irmatov", "Howard Webb", "Yuichi Nishimura", "Björn Kuipers"], correct: 0, usada: false },
        { text: "Qual jogador levou o cartão vermelho mais rápido da história das Copas?", options: ["José Batista", "Zlatan Ibrahimovic", "David Beckham", "Zinedine Zidane"], correct: 0, usada: false },
        { text: "Quantos cartões vermelhos foram dados na final da Copa de 2006?", options: ["1", "2", "0", "3"], correct: 0, usada: false },
        { text: "Qual árbitro apitou três finais de Copa do Mundo?", options: ["Nenhum", "Pierluigi Collina", "Howard Webb", "Nicola Rizzoli"], correct: 0, usada: false },
        { text: "Qual jogador tem o recorde de mais gols de cabeça em Copas?", options: ["Klose", "Ronaldo", "Pelé", "Müller"], correct: 0, usada: false },
        { text: "Qual foi o primeiro jogador a ser expulso na história das Copas?", options: ["José Batista", "David Beckham", "Zinedine Zidane", "Cafu"], correct: 0, usada: false },
        { text: "Qual seleção fez mais gols em uma única edição de Copa?", options: ["Hungria 1954", "Brasil 1970", "Alemanha 2014", "França 1998"], correct: 0, usada: false },
        { text: "Qual jogador tem o recorde de mais partidas sem perder em Copas?", options: ["Pelé", "Messi", "Zidane", "Maradona"], correct: 0, usada: false },
        { text: "Qual foi o único jogador a vencer a Copa como capitão e técnico?", options: ["Zagallo", "Beckenbauer", "Deschamps", "Pelé"], correct: 1, usada: false },
        { text: "Qual país tem o melhor aproveitamento em finais de Copa?", options: ["Uruguai", "Brasil", "Alemanha", "Itália"], correct: 0, usada: false },
        { text: "Qual jogador fez o gol mais rápido em uma final de Copa?", options: ["Mario Mandzukic", "Mbappé", "Pelé", "Zidane"], correct: 0, usada: false },
        { text: "Qual foi o primeiro país a vencer uma Copa fora do seu continente?", options: ["Brasil 1958", "Alemanha 2014", "Espanha 2010", "França 2018"], correct: 0, usada: false },
        { text: "Qual jogador tem o recorde de mais defesas em uma final de Copa?", options: ["Courtois", "Neuer", "Buffon", "Casillas"], correct: 0, usada: false },
        { text: "Qual foi a maior goleada da história das Copas?", options: ["9x0", "10x1", "8x0", "7x1"], correct: 0, usada: false }
    ];

    const PREMIOS = [1000, 2000, 3000, 5000, 10000, 20000, 50000, 100000, 300000, 1000000];
    const ZONA_SEGURA = [3, 6, 9];

    let nivel = 1;
    let perguntasJogo = [];
    let indice = 0;
    let bloqueado = false;
    let recursos = { varUsado: false, pularUsado: false, juizUsado: false };

    const container = document.getElementById("container");

    function resetarPerguntasUsadas() {
        PERGUNTAS_FACIL.forEach(p => p.usada = false);
        PERGUNTAS_MEDIO.forEach(p => p.usada = false);
        PERGUNTAS_DIFICIL.forEach(p => p.usada = false);
        PERGUNTAS_ESPECIALISTA.forEach(p => p.usada = false);
    }

    function getPerguntaUnica(array) {
        let disponiveis = array.filter(p => !p.usada);
        if (disponiveis.length === 0) {
            array.forEach(p => p.usada = false);
            disponiveis = array;
        }
        const idx = Math.floor(Math.random() * disponiveis.length);
        const pergunta = disponiveis[idx];
        pergunta.usada = true;
        return { ...pergunta };
    }

    function getPerguntaPorNivel() {
        if (nivel <= 3) return getPerguntaUnica(PERGUNTAS_FACIL);
        else if (nivel <= 6) return getPerguntaUnica(PERGUNTAS_MEDIO);
        else if (nivel <= 9) return getPerguntaUnica(PERGUNTAS_DIFICIL);
        else return getPerguntaUnica(PERGUNTAS_ESPECIALISTA);
    }

    function gerarPerguntas() {
        resetarPerguntasUsadas();
        let perguntas = [];
        for (let i = 1; i <= 10; i++) {
            nivel = i;
            perguntas.push(getPerguntaPorNivel());
        }
        nivel = 1;
        return perguntas;
    }

    // ============================================================
    // FUNÇÃO PARA CALCULAR PRÊMIO GARANTIDO (ZONAS SEGURAS)
    // ============================================================
    function obterPremioGarantido() {
        let ultimo = 0;
        for (let i = 0; i < nivel - 1; i++) {
            if (ZONA_SEGURA.includes(i + 1)) {
                ultimo = PREMIOS[i];
            }
        }
        return `R$ ${ultimo.toLocaleString()}`;
    }

    // ============================================================
    // AJUDA DO JUIZ
    // ============================================================
    function ajudaJuiz() {
        if (recursos.juizUsado) {
            document.getElementById("feedback").innerHTML = "⚠️ Você já usou a ajuda do juiz!";
            return;
        }
        if (bloqueado) {
            document.getElementById("feedback").innerHTML = "⚠️ Você já respondeu esta pergunta!";
            return;
        }
        if (nivel === PREMIOS.length) {
            document.getElementById("feedback").innerHTML = "⚠️ Você NÃO pode usar a ajuda do juiz na pergunta de R$ 1 MILHÃO!";
            return;
        }
        
        const pergunta = perguntasJogo[indice];
        const opcoes = document.querySelectorAll(".opcao");
        const letras = ["A", "B", "C", "D"];
        
        let opcoesErradas = [];
        let indicesErrados = [];
        opcoes.forEach((opt) => {
            const optIdx = parseInt(opt.getAttribute("data-idx"));
            if (optIdx !== pergunta.correct && !opt.classList.contains("expulsa")) {
                opcoesErradas.push(opt);
                indicesErrados.push(optIdx);
            }
        });
        
        if (opcoesErradas.length >= 2) {
            const expulsar1 = opcoesErradas[0];
            const expulsar2 = opcoesErradas[1];
            const idx1 = indicesErrados[0];
            const idx2 = indicesErrados[1];
            const letra1 = letras[idx1];
            const letra2 = letras[idx2];
            
            const modal = document.createElement("div");
            modal.className = "modal-juiz";
            modal.innerHTML = `
                <div class="cartao-box">
                    <div class="cartao-titulo">⚽ DECISÃO DO ÁRBITRO ⚽</div>
                    <div class="cartoes">
                        <div class="cartao cartao-amarelo"><div class="cartao-numero">${letra1}</div><div class="cartao-legenda">CARTÃO AMARELO</div></div>
                        <div class="cartao cartao-vermelho"><div class="cartao-numero">${letra2}</div><div class="cartao-legenda">CARTÃO VERMELHO</div></div>
                    </div>
                    <div class="cartao-mensagem">🚨 OPÇÕES EXPULSAS! 🚨</div>
                    <button class="fechar-juiz" id="fecharJuiz">CONTINUAR</button>
                </div>
            `;
            document.body.appendChild(modal);
            document.getElementById("fecharJuiz").onclick = () => {
                expulsar1.classList.add("expulsa");
                expulsar2.classList.add("expulsa");
                modal.remove();
                document.getElementById("feedback").innerHTML = `⚽ Opções ${letra1} e ${letra2} EXPULSAS!`;
            };
            recursos.juizUsado = true;
            document.getElementById("btnJuiz").disabled = true;
        } else {
            document.getElementById("feedback").innerHTML = "⚽ Não há opções para expulsar!";
        }
    }

    // ============================================================
    // AJUDA DO VAR
    // ============================================================
    function ajudaVAR() {
        if (recursos.varUsado) {
            document.getElementById("feedback").innerHTML = "⚠️ Você já usou o VAR!";
            return;
        }
        if (bloqueado) {
            document.getElementById("feedback").innerHTML = "⚠️ Você já respondeu esta pergunta!";
            return;
        }
        if (nivel === PREMIOS.length) {
            document.getElementById("feedback").innerHTML = "⚠️ NÃO pode usar o VAR na pergunta de R$ 1 MILHÃO!";
            return;
        }
        
        const pergunta = perguntasJogo[indice];
        const letras = ["A", "B", "C", "D"];
        
        const modal = document.createElement("div");
        modal.className = "modal-var";
        modal.innerHTML = `
            <div class="var-box">
                <h2>📺 REVISÃO DO VAR</h2>
                <div class="var-bola">⚽</div>
                <div class="var-scan"></div>
                <p>Analisando o lance...</p>
                <div class="var-tempo" id="varContador">3</div>
                <div id="varResultado" style="display:none">
                    <div class="var-dica">✅ RESPOSTA CORRETA: ${letras[pergunta.correct]}</div>
                    <p style="color:white; margin-top:10px">📌 ${pergunta.options[pergunta.correct]}</p>
                </div>
                <button class="fechar-var" id="varFechar" style="display:none">FECHAR</button>
            </div>
        `;
        
        document.body.appendChild(modal);
        
        let tempo = 3;
        const contador = modal.querySelector("#varContador");
        const resultado = modal.querySelector("#varResultado");
        const fechar = modal.querySelector("#varFechar");
        
        const interval = setInterval(() => {
            tempo--;
            if (tempo >= 1) {
                if (contador) contador.innerText = tempo;
            } else {
                clearInterval(interval);
                if (contador) contador.style.display = "none";
                if (resultado) resultado.style.display = "block";
                if (fechar) fechar.style.display = "inline-block";
            }
        }, 1000);
        
        fechar.onclick = () => {
            modal.remove();
        };
        
        recursos.varUsado = true;
        const btnVar = document.getElementById("btnVar");
        if (btnVar) btnVar.disabled = true;
        document.getElementById("feedback").innerHTML = "📺 VAR usado! O árbitro revisou o lance.";
    }

    // ============================================================
    // PULAR PERGUNTA
    // ============================================================
    function pularPergunta() {
        if (nivel === PREMIOS.length) {
            document.getElementById("feedback").innerHTML = "⚠️ NÃO pode pular a pergunta de R$ 1 MILHÃO!";
            return;
        }
        if (recursos.pularUsado) {
            document.getElementById("feedback").innerHTML = "⚠️ Você já usou o recurso de pular!";
            return;
        }
        if (bloqueado) {
            document.getElementById("feedback").innerHTML = "⚠️ Você já respondeu esta pergunta!";
            return;
        }
        
        const perguntaAtual = perguntasJogo[indice];
        perguntaAtual.usada = false;
        
        const nivelTemp = nivel;
        let novaPergunta = null;
        if (nivelTemp <= 3) novaPergunta = getPerguntaUnica(PERGUNTAS_FACIL);
        else if (nivelTemp <= 6) novaPergunta = getPerguntaUnica(PERGUNTAS_MEDIO);
        else if (nivelTemp <= 9) novaPergunta = getPerguntaUnica(PERGUNTAS_DIFICIL);
        else novaPergunta = getPerguntaUnica(PERGUNTAS_ESPECIALISTA);
        
        perguntasJogo[indice] = novaPergunta;
        carregarPergunta();
        recursos.pularUsado = true;
        document.getElementById("btnPular").disabled = true;
        document.getElementById("feedback").innerHTML = "⏭️ Pergunta pulada! Nova pergunta carregada.";
    }

    // ============================================================
    // MOSTRAR TROFÉU
    // ============================================================
    function mostrarTrofeu() {
        const modal = document.createElement("div");
        modal.className = "modal-trofeu";
        modal.innerHTML = `
            <div class="trofeu-box">
                <div class="trofeu-icon">🏆🏆🏆</div>
                <h2>CAMPEÃO MUNDIAL!</h2>
                <p>🏆 VOCÊ GANHOU R$ 1.000.000,00! 🏆</p>
                <p>⭐ Você domina as Copas do Mundo! ⭐</p>
                <button class="fechar-var" id="fecharTrofeu">JOGAR NOVAMENTE</button>
            </div>
        `;
        document.body.appendChild(modal);
        document.getElementById("fecharTrofeu").onclick = () => {
            modal.remove();
            iniciarJogo();
        };
    }

    function carregarPergunta() {
        bloqueado = false;
        document.getElementById("btnProximo").disabled = true;
        const q = perguntasJogo[indice];
        document.getElementById("perguntaTexto").innerHTML = `${nivel}. ${q.text}`;
        const containerOpcoes = document.getElementById("opcoesContainer");
        containerOpcoes.innerHTML = "";
        const letras = ["A", "B", "C", "D"];
        q.options.forEach((opt, i) => {
            const div = document.createElement("div");
            div.className = "opcao";
            div.setAttribute("data-idx", i);
            div.innerHTML = `<div class="letra">${letras[i]}</div><div class="texto-opcao">${opt}</div>`;
            div.onclick = () => responder(i, div);
            containerOpcoes.appendChild(div);
        });
        document.getElementById("feedback").innerHTML = "🎤 Qual é a resposta?";
    }

    function responder(selecionado, elemento) {
        if (bloqueado) return;
        const pergunta = perguntasJogo[indice];
        const acertou = (selecionado === pergunta.correct);
        bloqueado = true;
        const todas = document.querySelectorAll(".opcao");
        
        if (acertou) {
            elemento.classList.add("correct");
            document.getElementById("feedback").innerHTML = "✅ CORRETO! 👏";
            if (nivel === PREMIOS.length) {
                setTimeout(() => mostrarTrofeu(), 500);
                return;
            }
            document.getElementById("btnProximo").disabled = false;
        } else {
            elemento.classList.add("wrong");
            todas.forEach(opt => {
                if (parseInt(opt.getAttribute("data-idx")) === pergunta.correct) {
                    opt.classList.add("correct");
                }
            });
            
            // CALCULA O PRÊMIO GARANTIDO
            const premioGanho = obterPremioGarantido();
            
            document.getElementById("feedback").innerHTML = `❌ ERROU! Resposta: ${pergunta.options[pergunta.correct]}`;
            
            setTimeout(() => {
                alert(`🏁 FIM DE JOGO!\nVocê ganhou ${premioGanho}!\n\nClique em OK para recomeçar.`);
                iniciarJogo();
            }, 2000);
        }
        todas.forEach(opt => opt.style.pointerEvents = "none");
    }

    function avancarNivel() {
        if (!bloqueado) return;
        nivel++;
        indice++;
        if (nivel <= PREMIOS.length && indice < perguntasJogo.length) renderizarQuiz();
    }

    function desistir() {
        const premioGanho = obterPremioGarantido();
        if (confirm(`Desistir? Você ganha ${premioGanho}. Confirmar?`)) {
            alert(`🎉 Você desistiu e levou ${premioGanho}! 🎉`);
            iniciarJogo();
        }
    }

    function getDificuldadeTexto() {
        if (nivel <= 3) return "FÁCIL";
        if (nivel <= 6) return "MÉDIO";
        if (nivel <= 9) return "DIFÍCIL";
        return "ESPECIALISTA";
    }

    function getDificuldadeClasse() {
        if (nivel <= 3) return "facil";
        if (nivel <= 6) return "medio";
        if (nivel <= 9) return "dificil";
        return "especialista";
    }

    function renderizarQuiz() {
        const progresso = (nivel / PREMIOS.length) * 100;
        const isUltima = (nivel === PREMIOS.length);
        container.innerHTML = `
            <div class="header">
                <div class="premio">💰 R$ ${PREMIOS[nivel-1].toLocaleString()}</div>
                <div class="nivel-info">Nível ${nivel} de ${PREMIOS.length}</div>
                <div class="dificuldade ${getDificuldadeClasse()}">🎯 ${getDificuldadeTexto()}</div>
            </div>
            <div class="progresso"><div class="progresso-bar" style="width:${progresso}%"></div></div>
            <div class="quiz-content">
                <div class="pergunta" id="perguntaTexto"></div>
                <div class="opcoes" id="opcoesContainer"></div>
                <div class="recursos">
                    <button class="btn-recurso" id="btnJuiz" ${recursos.juizUsado || isUltima ? 'disabled' : ''}>⚽ JUIZ</button>
                    <button class="btn-recurso" id="btnVar" ${recursos.varUsado || isUltima ? 'disabled' : ''}>📺 VAR</button>
                    <button class="btn-recurso" id="btnPular" ${recursos.pularUsado || isUltima ? 'disabled' : ''}>⏭️ PULAR</button>
                </div>
                <div class="feedback" id="feedback"></div>
                <button class="btn" id="btnProximo" disabled>PRÓXIMA ➡</button>
                <button class="btn btn-desistir" id="btnDesistir">🏠 DESISTIR</button>
                <button class="btn btn-reiniciar" id="btnReiniciar">🔄 REINICIAR</button>
            </div>
        `;
        carregarPergunta();
        document.getElementById("btnProximo").onclick = avancarNivel;
        document.getElementById("btnDesistir").onclick = desistir;
        document.getElementById("btnReiniciar").onclick = iniciarJogo;
        document.getElementById("btnJuiz").onclick = ajudaJuiz;
        document.getElementById("btnVar").onclick = ajudaVAR;
        document.getElementById("btnPular").onclick = pularPergunta;
    }

    function iniciarJogo() {
        nivel = 1;
        perguntasJogo = gerarPerguntas();
        indice = 0;
        bloqueado = false;
        recursos = { varUsado: false, pularUsado: false, juizUsado: false };
        renderizarQuiz();
    }

    iniciarJogo();
</script>
</body>
</html>