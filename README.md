<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Projeto de Estudo com Navegação</title>
    <style>
        /* * MÉTODO EDUCATIVO:
         * Usar variáveis CSS (propriedades personalizadas) é uma ótima prática. 
         * Elas permitem que você defina um valor de cor em um só lugar e o reutilize
         * em todo o código. Se quiser mudar a paleta de cores no futuro, 
         * basta alterar os valores aqui.
        */
        :root {
            --cor-fundo-principal: #0a192f;  /* Azul marinho bem escuro para o fundo */
            --cor-navegacao: #112240;       /* Azul marinho um pouco mais claro para a sidebar */
            --cor-texto-principal: #ccd6f6; /* Um branco azulado suave para textos */
            --cor-texto-cabecalho: #e6f1ff; /* Um branco mais brilhante para títulos */
            --cor-destaque: #3b82f6;        /* Um azul mais vivo para hover e foco */
            --cor-sombra: rgba(2, 12, 27, 0.7); /* Sombra para dar profundidade */
        }

        /* Resets e Estilos Globais */
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; /* Fonte mais moderna */
            margin: 0;
            background-color: var(--cor-fundo-principal); /* Aplicando a cor de fundo */
            color: var(--cor-texto-principal); /* Aplicando a cor de texto padrão */
        }

        /* Layout Principal com Flexbox (Estrutura mantida) */
        .container-principal {
            display: flex;
        }

        /* Barra de Navegação Lateral */
        #navegacao-lateral {
            width: 300px;
            background-color: var(--cor-navegacao); /* Fundo da barra de navegação */
            padding: 25px;
            height: 100vh;
            overflow-y: auto;
            border-right: 1px solid #1e2d4d; /* Borda sutil */
        }

        #navegacao-lateral h2 {
            margin-top: 0;
            color: var(--cor-texto-cabecalho); /* Cor para o título "Navegação" */
            font-size: 1.5em;
            margin-bottom: 20px;
        }

        #navegacao-lateral ul {
            list-style-type: none;
            padding: 0;
        }

        /* * DOCUMENTAÇÃO - BOTÕES DE NAVEGAÇÃO:
         * Transformamos os links <a> em botões.
         * - 'background-color': Define a cor de fundo do botão.
         * - 'color': Define a cor do texto do botão.
         * - 'border': Adiciona uma borda sutil para definir o contorno.
         * - 'transition': Cria uma animação suave para a mudança de cor ao passar o mouse.
        */
        #navegacao-lateral a {
            display: block;
            padding: 12px 15px;
            margin-bottom: 8px;
            text-decoration: none;
            color: var(--cor-texto-principal);
            background-color: transparent; /* Fundo transparente por padrão */
            border: 1px solid transparent; /* Borda transparente para manter o tamanho */
            border-radius: 5px;
            transition: background-color 0.3s, border-color 0.3s, color 0.3s;
        }

        #navegacao-lateral a:hover {
            background-color: var(--cor-destaque); /* Muda o fundo ao passar o mouse */
            color: var(--cor-texto-cabecalho);     /* Muda a cor do texto para dar mais destaque */
            border-color: var(--cor-destaque);
        }

        /* Área de Conteúdo Principal */
        #conteudo-principal {
            flex: 1;
            padding: 25px;
            overflow-y: auto;
            height: 100vh;
        }
        
        #conteudo-principal h1 {
            color: var(--cor-texto-cabecalho);
        }

        #conteudo-principal ul {
            list-style-type: none;
            padding: 0;
        }

        /*
         * DOCUMENTAÇÃO - CARTÕES DE CONTEÚDO:
         * Cada item da lista agora parece um "cartão".
         * - 'background-color': Usa a mesma cor da barra de navegação para criar coesão.
         * - 'box-shadow': Adiciona uma sombra para fazer o cartão "flutuar" sobre o fundo.
        */
        #conteudo-principal li {
            margin-bottom: 25px;
            padding: 20px;
            background-color: var(--cor-navegacao); /* Fundo do cartão */
            border-radius: 8px;
            box-shadow: 0 4px 10px var(--cor-sombra);
            border: 1px solid #1e2d4d;
        }
        
        #conteudo-principal strong {
            font-size: 1.2em;
            color: var(--cor-texto-cabecalho);
        }

        /* Caixa de texto editável */
        .caixa-editavel {
            border: 1px solid #2a4161; /* Borda sutil */
            padding: 10px;
            min-height: 120px;
            margin-top: 15px;
            border-radius: 5px;
            background-color: var(--cor-fundo-principal); /* Fundo um pouco mais escuro */
            outline: none; /* Remove o contorno padrão */
            transition: border-color 0.3s;
        }

        .caixa-editavel:focus {
            border-color: var(--cor-destaque); /* Muda a cor da borda ao focar */
        }
    </style>
</head>
<body>

    <div class="container-principal">
        
        <nav id="navegacao-lateral">
            <h2>Navegação</h2>
            <ul>
                <li><a href="#tema-1">Introdução à Medicina Laboratorial</a></li>
                <li><a href="#tema-2">Anemias</a></li>
                <li><a href="#tema-3">Leucócitos</a></li>
                <li><a href="#tema-4">Hiperglicemias</a></li>
                <li><a href="#tema-5">Dislipidemias</a></li>
                <li><a href="#tema-6">Função Renal - Revisão</a></li>
                <li><a href="#tema-7">Disfunções Hepáticas</a></li>
                <li><a href="#tema-8">Hepatites</a></li>
                <li><a href="#tema-9">IST/HIV</a></li>
                <li><a href="#tema-10">Marcadores Inflamatórios</a></li>
                <li><a href="#tema-11">COVID, Dengue, Zika e Chikungunya</a></li>
                <li><a href="#tema-12">Microbiologia Laboratorial</a></li>
            </ul>
        </nav>

        <main id="conteudo-principal">
            <h1>Temas de Estudo</h1>
            <ul>
                <li id="tema-1">
                    <strong>Introdução à Medicina Laboratorial</strong>
                    <div class="caixa-editavel" contenteditable="true"></div>
                </li>
                <li id="tema-2">
                    <strong>Anemias</strong>
                    <div class="caixa-editavel" contenteditable="true"></div>
                </li>
                <li id="tema-3">
                    <strong>Leucócitos</strong>
                    <div class="caixa-editavel" contenteditable="true"></div>
                </li>
                <li id="tema-4">
                    <strong>Hiperglicemias</strong>
                    <div class="caixa-editavel" contenteditable="true"></div>
                </li>
                <li id="tema-5">
                    <strong>Dislipidemias</strong>
                    <div class="caixa-editavel" contenteditable="true"></div>
                </li>
                <li id="tema-6">
                    <strong>Função Renal - Revisão</strong>
                    <div class="caixa-editavel" contenteditable="true"></div>
                </li>
                <li id="tema-7">
                    <strong>Disfunções Hepáticas</strong>
                    <div class="caixa-editavel" contenteditable="true"></div>
                </li>
                <li id="tema-8">
                    <strong>Hepatites</strong>
                    <div class="caixa-editavel" contenteditable="true"></div>
                </li>
                <li id="tema-9">
                    <strong>IST/HIV</strong>
                    <div class="caixa-editavel" contenteditable="true"></div>
                </li>
                <li id="tema-10">
                    <strong>Marcadores Inflamatórios e Doenças Autoimunes</strong>
                    <div class="caixa-editavel" contenteditable="true"></div>
                </li>
                <li id="tema-11">
                    <strong>COVID, Dengue, Zika e Chikungunya</strong>
                    <div class="caixa-editavel" contenteditable="true"></div>
                </li>
                <li id="tema-12">
                    <strong>Avaliação Laboratorial Inicial em Microbiologia</strong>
                    <div class="caixa-editavel" contenteditable="true"></div>
                </li>
            </ul>
        </main>

    </div>

</body>
</html>
