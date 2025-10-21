<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CosmoMind - IA de Exploração Espacial</title>
    <style>
        :root {
            --primary: #0a0e29;
            --secondary: #1a237e;
            --accent: #00b0ff;
            --text: #e0e0e0;
            --highlight: #ff4081;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: var(--primary);
            color: var(--text);
            line-height: 1.6;
            overflow-x: hidden;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        /* Header */
        header {
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            padding: 20px 0;
            position: sticky;
            top: 0;
            z-index: 100;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.3);
        }
        
        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            display: flex;
            align-items: center;
            gap: 15px;
        }
        
        .logo-icon {
            font-size: 2.5rem;
            color: var(--accent);
        }
        
        .logo-text {
            font-size: 1.8rem;
            font-weight: 700;
            background: linear-gradient(to right, var(--accent), var(--highlight));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        
        nav ul {
            display: flex;
            list-style: none;
            gap: 30px;
        }
        
        nav a {
            color: var(--text);
            text-decoration: none;
            font-weight: 500;
            transition: color 0.3s;
            position: relative;
        }
        
        nav a:hover {
            color: var(--accent);
        }
        
        nav a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background-color: var(--accent);
            transition: width 0.3s;
        }
        
        nav a:hover::after {
            width: 100%;
        }
        
        /* Hero Section */
        .hero {
            height: 80vh;
            display: flex;
            align-items: center;
            position: relative;
            overflow: hidden;
        }
        
        .hero-bg {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 800" preserveAspectRatio="none"><rect width="1200" height="800" fill="%230a0e29"/><circle cx="200" cy="150" r="2" fill="%2300b0ff" opacity="0.7"/><circle cx="800" cy="300" r="1" fill="%2300b0ff" opacity="0.5"/><circle cx="1100" cy="100" r="1.5" fill="%2300b0ff" opacity="0.6"/><circle cx="400" cy="500" r="1" fill="%23ff4081" opacity="0.5"/><circle cx="1000" cy="600" r="2" fill="%23ff4081" opacity="0.7"/><circle cx="300" cy="700" r="1.5" fill="%23ff4081" opacity="0.6"/></svg>');
            z-index: -1;
        }
        
        .hero-content {
            max-width: 600px;
            z-index: 1;
        }
        
        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 20px;
            line-height: 1.2;
        }
        
        .hero p {
            font-size: 1.2rem;
            margin-bottom: 30px;
            opacity: 0.9;
        }
        
        .cta-button {
            display: inline-block;
            background: linear-gradient(to right, var(--accent), var(--highlight));
            color: white;
            padding: 12px 30px;
            border-radius: 30px;
            text-decoration: none;
            font-weight: 600;
            transition: transform 0.3s, box-shadow 0.3s;
            box-shadow: 0 4px 15px rgba(0, 176, 255, 0.4);
        }
        
        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 20px rgba(0, 176, 255, 0.6);
        }
        
        /* Features Section */
        .features {
            padding: 100px 0;
            background-color: rgba(10, 14, 41, 0.9);
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 60px;
            font-size: 2.5rem;
        }
        
        .section-title span {
            background: linear-gradient(to right, var(--accent), var(--highlight));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        
        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }
        
        .feature-card {
            background: rgba(26, 35, 126, 0.3);
            border-radius: 15px;
            padding: 30px;
            transition: transform 0.3s, box-shadow 0.3s;
            border: 1px solid rgba(0, 176, 255, 0.2);
        }
        
        .feature-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 10px 25px rgba(0, 176, 255, 0.2);
        }
        
        .feature-icon {
            font-size: 2.5rem;
            margin-bottom: 20px;
            color: var(--accent);
        }
        
        .feature-card h3 {
            font-size: 1.5rem;
            margin-bottom: 15px;
        }
        
        /* Demo Section */
        .demo {
            padding: 100px 0;
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
        }
        
        .demo-container {
            display: flex;
            align-items: center;
            gap: 50px;
        }
        
        .demo-content {
            flex: 1;
        }
        
        .demo-visual {
            flex: 1;
            background: rgba(0, 0, 0, 0.2);
            border-radius: 15px;
            padding: 30px;
            min-height: 400px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            border: 1px solid rgba(0, 176, 255, 0.3);
        }
        
        .ai-response {
            background: rgba(0, 0, 0, 0.3);
            border-radius: 10px;
            padding: 20px;
            margin-top: 20px;
            width: 100%;
            min-height: 200px;
            font-family: monospace;
            overflow-y: auto;
            border: 1px solid rgba(255, 64, 129, 0.3);
        }
        
        .input-group {
            display: flex;
            margin-top: 20px;
            width: 100%;
        }
        
        .input-group input {
            flex: 1;
            padding: 12px 15px;
            border: none;
            border-radius: 30px 0 0 30px;
            background: rgba(0, 0, 0, 0.5);
            color: var(--text);
            outline: none;
        }
        
        .input-group button {
            padding: 12px 25px;
            border: none;
            border-radius: 0 30px 30px 0;
            background: linear-gradient(to right, var(--accent), var(--highlight));
            color: white;
            cursor: pointer;
            transition: opacity 0.3s;
        }
        
        .input-group button:hover {
            opacity: 0.9;
        }
        
        /* Ethics Section */
        .ethics {
            padding: 100px 0;
            background-color: rgba(10, 14, 41, 0.9);
        }
        
        .ethics-content {
            max-width: 800px;
            margin: 0 auto;
            text-align: center;
        }
        
        .ethics-statement {
            background: rgba(26, 35, 126, 0.3);
            border-radius: 15px;
            padding: 40px;
            margin-top: 40px;
            border-left: 5px solid var(--highlight);
        }
        
        /* Footer */
        footer {
            background: linear-gradient(135deg, var(--secondary) 0%, var(--primary) 100%);
            padding: 60px 0 30px;
        }
        
        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 40px;
            margin-bottom: 40px;
        }
        
        .footer-column h3 {
            font-size: 1.3rem;
            margin-bottom: 20px;
            color: var(--accent);
        }
        
        .footer-column ul {
            list-style: none;
        }
        
        .footer-column ul li {
            margin-bottom: 10px;
        }
        
        .footer-column a {
            color: var(--text);
            text-decoration: none;
            transition: color 0.3s;
        }
        
        .footer-column a:hover {
            color: var(--accent);
        }
        
        .copyright {
            text-align: center;
            padding-top: 30px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            font-size: 0.9rem;
            opacity: 0.7;
        }
        
        /* Responsive */
        @media (max-width: 768px) {
            .header-content {
                flex-direction: column;
                gap: 20px;
            }
            
            nav ul {
                gap: 15px;
            }
            
            .hero h1 {
                font-size: 2.5rem;
            }
            
            .demo-container {
                flex-direction: column;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container">
            <div class="header-content">
                <div class="logo">
                    <div class="logo-icon">🚀</div>
                    <div class="logo-text">CosmoMind</div>
                </div>
                <nav>
                    <ul>
                        <li><a href="#home">Início</a></li>
                        <li><a href="#features">Recursos</a></li>
                        <li><a href="#demo">Demonstração</a></li>
                        <li><a href="#ethics">Ética</a></li>
                        <li><a href="#contact">Contato</a></li>
                    </ul>
                </nav>
            </div>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="hero-bg"></div>
        <div class="container">
            <div class="hero-content">
                <h1>IA Super Inteligente para <span>Exploração Espacial</span></h1>
                <p>CosmoMind é uma inteligência artificial avançada projetada para auxiliar na descoberta e análise de dados espaciais, identificando oportunidades de pesquisa e exploração de forma ética e responsável.</p>
                <a href="#demo" class="cta-button">Experimente Agora</a>
            </div>
        </div>
    </section>

    <!-- Features Section -->
    <section class="features" id="features">
        <div class="container">
            <h2 class="section-title">Nossos <span>Recursos</span></h2>
            <div class="features-grid">
                <div class="feature-card">
                    <div class="feature-icon">🔭</div>
                    <h3>Análise de Dados Espaciais</h3>
                    <p>Processamento avançado de dados de telescópios e satélites para identificar padrões e anomalias cósmicas.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">🧠</div>
                    <h3>Raciocínio Científico</h3>
                    <p>Capacidade de formular hipóteses e propor experimentos baseados em princípios científicos estabelecidos.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">🌌</div>
                    <h3>Simulações de Exploração</h3>
                    <p>Criação de modelos preditivos para missões espaciais, considerando variáveis físicas e astronômicas.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">🛰️</div>
                    <h3>Otimização de Trajetórias</h3>
                    <p>Cálculo de rotas eficientes para sondas e naves espaciais, maximizando o retorno científico.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Demo Section -->
    <section class="demo" id="demo">
        <div class="container">
            <h2 class="section-title">Demonstração <span>Interativa</span></h2>
            <div class="demo-container">
                <div class="demo-content">
                    <h3>Converse com a CosmoMind</h3>
                    <p>Faça perguntas sobre exploração espacial, astronomia ou ciência. Nossa IA responderá com informações precisas e relevantes.</p>
                    <p>Exemplos de perguntas:</p>
                    <ul>
                        <li>Quais são os exoplanetas mais promissores para busca de vida?</li>
                        <li>Como poderíamos explorar Europa, lua de Júpiter?</li>
                        <li>Quais tecnologias são necessárias para viagens interestelares?</li>
                    </ul>
                </div>
                <div class="demo-visual">
                    <div class="ai-response" id="ai-response">
                        Olá! Sou a CosmoMind, uma IA especializada em exploração espacial. Como posso ajudá-lo hoje?
                    </div>
                    <div class="input-group">
                        <input type="text" id="user-input" placeholder="Digite sua pergunta sobre exploração espacial...">
                        <button id="send-btn">Enviar</button>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Ethics Section -->
    <section class="ethics" id="ethics">
        <div class="container">
            <h2 class="section-title">Compromisso <span>Ético</span></h2>
            <div class="ethics-content">
                <p>A CosmoMind foi desenvolvida com princípios éticos rigorosos, priorizando a segurança, transparência e responsabilidade em todas as suas operações.</p>
                <div class="ethics-statement">
                    <h3>Nossa Declaração de Princípios</h3>
                    <p>Nos comprometemos a usar a inteligência artificial exclusivamente para fins pacíficos, de pesquisa e exploração científica. Nossa tecnologia não será utilizada para desenvolver armas, causar danos ou violar direitos humanos e soberanias nacionais. Todo conhecimento gerado pela CosmoMind será compartilhado com a comunidade científica global para o benefício de toda a humanidade.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer id="contact">
        <div class="container">
            <div class="footer-content">
                <div class="footer-column">
                    <h3>CosmoMind</h3>
                    <p>IA avançada para descobertas espaciais e exploração científica responsável.</p>
                </div>
                <div class="footer-column">
                    <h3>Links Rápidos</h3>
                    <ul>
                        <li><a href="#home">Início</a></li>
                        <li><a href="#features">Recursos</a></li>
                        <li><a href="#demo">Demonstração</a></li>
                        <li><a href="#ethics">Ética</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>Contato</h3>
                    <ul>
                        <li>Email: info@cosmomind.space</li>
                        <li>Telefone: +55 (11) 99999-9999</li>
                        <li>Endereço: Av. Paulista, 1000 - São Paulo, SP</li>
                    </ul>
                </div>
            </div>
            <div class="copyright">
                <p>&copy; 2023 CosmoMind. Todos os direitos reservados. Desenvolvido para o avanço científico da humanidade.</p>
            </div>
        </div>
    </footer>

    <script>
        // Simulação de resposta da IA
        document.getElementById('send-btn').addEventListener('click', function() {
            const userInput = document.getElementById('user-input').value;
            const aiResponse = document.getElementById('ai-response');
            
            if (userInput.trim() === '') return;
            
            // Adiciona a pergunta do usuário ao chat
            const userMessage = document.createElement('div');
            userMessage.innerHTML = `<strong>Você:</strong> ${userInput}`;
            userMessage.style.marginBottom = '10px';
            userMessage.style.color = '#00b0ff';
            aiResponse.appendChild(userMessage);
            
            // Simula processamento
            aiResponse.innerHTML += '<div>CosmoMind está pensando...</div>';
            aiResponse.scrollTop = aiResponse.scrollHeight;
            
            // Resposta após um breve delay
            setTimeout(() => {
                // Remove a mensagem de "pensando"
                aiResponse.removeChild(aiResponse.lastChild);
                
                // Gera resposta baseada na entrada do usuário
                const response = generateAIResponse(userInput);
                const aiMessage = document.createElement('div');
                aiMessage.innerHTML = `<strong>CosmoMind:</strong> ${response}`;
                aiMessage.style.marginBottom = '10px';
                aiResponse.appendChild(aiMessage);
                
                // Limpa o campo de entrada
                document.getElementById('user-input').value = '';
                
                // Rola para a última mensagem
                aiResponse.scrollTop = aiResponse.scrollHeight;
            }, 1500);
        });
        
        // Permitir enviar com Enter
        document.getElementById('user-input').addEventListener('keypress', function(e) {
            if (e.key === 'Enter') {
                document.getElementById('send-btn').click();
            }
        });
        
        // Gerador de respostas simples
        function generateAIResponse(input) {
            const lowerInput = input.toLowerCase();
            
            if (lowerInput.includes('exoplaneta') || lowerInput.includes('vida')) {
                return "Os exoplanetas mais promissores para busca de vida incluem aqueles na zona habitável de suas estrelas, como os do sistema TRAPPIST-1, Kepler-186f e Proxima Centauri b. A presença de água líquida e atmosfera são fatores cruciais.";
            } else if (lowerInput.includes('europa') || lowerInput.includes('júpiter')) {
                return "Europa, lua de Júpiter, possui um oceano subsuperficial que pode abrigar condições para vida. Para explorá-la, precisaríamos de robôs submarinos capazes de perfar o gelo superficial e equipamentos resistentes à radiação intensa do campo magnético de Júpiter.";
            } else if (lowerInput.includes('viagem interestelar') || lowerInput.includes('interestelar')) {
                return "Viagens interestelares exigiriam avanços em propulsão (como velas solares, propulsão nuclear ou antimatéria), sistemas de suporte vital de longa duração e proteção contra radiação cósmica. Atualmente, a sonda Voyager é o objeto humano mais distante, mas levaria milhares de anos para alcançar a estrela mais próxima.";
            } else if (lowerInput.includes('mars') || lowerInput.includes('marte')) {
                return "Marte é um alvo prioritário para exploração humana. Desafios incluem radiação, poeira fina, temperaturas extremas e a necessidade de produzir recursos in situ (como água e oxigênio). A NASA planeja missões tripuladas para a década de 2030.";
            } else {
                return "Interessante pergunta sobre exploração espacial! Baseando-me em dados científicos atuais, posso afirmar que o cosmos oferece oportunidades infinitas para descobertas. A colaboração internacional e o desenvolvimento tecnológico responsável são essenciais para nosso avanço no espaço.";
            }
        }
    </script>
</body>
</html>
