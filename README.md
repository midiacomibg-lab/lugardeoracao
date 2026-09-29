<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Mural de Pedidos de Oração</title>
  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body, html {
      height: 100%;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background-color: #0b2c81;
      color: #ffffff;
      overflow: hidden;
    }

    /* Botão de Tela Cheia */
    .fullscreen-btn {
      position: fixed;
      top: 15px;
      right: 15px;
      z-index: 100;
      background: rgba(31, 41, 55, 0.8);
      color: #f59e0b;
      border: 1px solid #374151;
      padding: 8px 12px;
      border-radius: 6px;
      cursor: pointer;
      font-size: 0.9rem;
      transition: background 0.3s;
    }

    .fullscreen-btn:hover {
      background: #374151;
    }

    .container {
      display: flex;
      height: 100vh;
      width: 100vw;
    }

    /* Lado Esquerdo - 30% da largura */
.sidebar {
  width: 30%;
  background: 
    linear-gradient(135deg, rgba(61, 31, 3, 0.85) 0%, rgba(73, 38, 5, 0.85) 100%),
    url('https://i.pinimg.com/736x/a9/d8/4c/a9d84ceba024e40600d3f272c9c24f6f.jpg');
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  padding: 50px 30px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  border-right: 2px solid #374151;
  z-index: 10;
  box-shadow: 5px 0 25px rgba(0,0,0,0.5);
}

    .sidebar h1 {
      font-size: 6rem;
      color: #f59e0b;
      margin-bottom: 24px;
      line-height: 1.2;
      font-weight: 900;
      font-family: 'Figtree', sans-serif;
    }

    .sidebar p {
      font-size: 2rem;
      line-height: 1.6;
      color: #d1d5db;
      margin-bottom: 20px;
      font-family: 'Figtree', sans-serif;
    }

    .sidebar .highlight-box {
      background: rgba(245, 158, 11, 0.1);
      border-left: 4px solid #f59e0b;
      padding: 16px 20px;
      border-radius: 0 8px 8px 0;
      margin-top: 10px;
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 12px;
    }

    .sidebar .highlight-box p {
      margin-bottom: 0;
      font-size: 2rem;
      color: #fef3c7;
      width: 100%;
      font-family: 'Figtree', sans-serif;
    }

    .sidebar .highlight-box img {
      max-width: 100%;
      height: auto;
      border-radius: 6px;
      display: block;
    }

    /* Lado Direito - 70% da largura */
.credits-window {
  width: 70%;
  position: relative;
  overflow: hidden;
  /* Substituição do radial-gradient pela imagem */
  background-image: url('https://unblast.com/wp-content/uploads/2018/12/Wood-Pattern-2.jpg');
  background-size: cover;      /* Preenche toda a área */
  background-position: center; /* Centraliza a textura de madeira */
  background-repeat: no-repeat;
}

.credits-window::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100px;
  background: linear-gradient(to bottom, rgba(243, 165, 49, 0.8) 0%, transparent 100%);
  z-index: 5;
  pointer-events: none;
}

.credits-window::after {
  content: "";
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 100px;
  background: linear-gradient(to top, rgba(243, 165, 49, 0.8) 0%, transparent 100%);
  z-index: 5;
  pointer-events: none;
}

    .credits-content {
      position: absolute;
      width: 100%;
      text-align: center;
      top: 0;
      will-change: transform;
      padding: 0 30px;
    }

    /* Grid de 2 Colunas */
    .cards-grid {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 30px;
      padding-bottom: 20px;
    }

    .name-card {
      margin: 10px 40px;
      padding: 24px 20px;
      background: rgba(255, 255, 255, 0.979);
      border: 1px solid rgba(253, 245, 228, 0.979);
      border-radius: 3px;
      box-shadow: 0 4px 20px rgba(0, 0, 0, 0.2);
      display: flex;
      align-items: center;
      justify-content: center;
    }

    .name-title {
      font-size: 3.6rem;
      font-weight: 600;
      color: #2c1c03;
      letter-spacing: 0.5px;
      font-family: 'Figtree', sans-serif;
    }

    .status-msg {
      font-size: 1.8rem;
      color: #09162e;
      margin-top: 50vh;
      transform: translateY(-50%);
    }

    @media (max-width: 900px) {
      .container { flex-direction: column; }
      .sidebar { width: 100%; height: 35%; padding: 25px; }
      .credits-window { width: 100%; height: 65%; }
      .cards-grid { grid-template-columns: 1fr; }
      .sidebar h1 { font-size: 1.8rem; }
      .sidebar p { font-size: 1rem; }
      .name-title { font-size: 1.5rem; }
    }
  </style>
</head>
<body>

  <button class="fullscreen-btn" onclick="toggleFullScreen()">⛶</button>

  <div class="container">
    <div class="sidebar">
      <h1>Lugar<br><span style="font-size: 2rem; font-weight: 600;">de</span> Oração</h1>
      <p>Acompanhe os últimos pedidos de oração enviados por nossa comunidade.</p>
      
      <div class="highlight-box">
        <p>✨ Faça o seu pedido pelo nosso App ou site: <span style="font-weight: 900;">www.ibg.org.br</span></p>
        <img src="https://www.image2url.com/r2/default/images/1788611607397-673c067c-7e81-4e4f-9ecf-8ff483aaa89a.png" alt="Acesse pelo App ou Site" width="70%">
      </div>
    </div>

    <div class="credits-window" id="creditsWindow">
      <div class="credits-content" id="creditsContent">
        <div class="status-msg">Carregando lista de nomes...</div>
      </div>
    </div>
  </div>

  <script>
    const API_URL = 'https://script.google.com/macros/s/AKfycbw32JcNWu4QoPXsiuwnCan11nF1wSvPJ08-ExeCmE1KojSoIlx_jaOTka7Ii75S_NphIg/exec';

    // Cache local: mostra imediatamente o último resultado válido
    // enquanto tenta atualizar os dados em segundo plano.
    const CACHE_KEY = 'ibg_lugar_oracao_cache_v1';
    const CACHE_MAX_AGE = 7 * 24 * 60 * 60 * 1000; // 7 dias
    const FETCH_TIMEOUT = 8000; // não deixa a tela ficar esperando indefinidamente

    let animationId = null;
    let posY = 80;
    const speed = 1.2; 
    let isInitialized = false;
    let cachedItems = null;

    function loadCache() {
      try {
        const raw = localStorage.getItem(CACHE_KEY);
        if (!raw) return null;

        const data = JSON.parse(raw);
        if (!data || !Array.isArray(data.items)) return null;

        // Mesmo que o cache seja antigo, ele ainda pode ser útil como
        // último estado visual; o limite evita guardar dados indefinidamente.
        if (Date.now() - (data.savedAt || 0) > CACHE_MAX_AGE) return null;

        return data;
      } catch (error) {
        console.warn('Não foi possível ler o cache local:', error);
        return null;
      }
    }

    function saveCache(items) {
      try {
        localStorage.setItem(CACHE_KEY, JSON.stringify({
          savedAt: Date.now(),
          items: items
        }));
      } catch (error) {
        console.warn('Não foi possível salvar o cache local:', error);
      }
    }

    function showCache() {
      const data = loadCache();
      if (!data) return false;

      cachedItems = data.items;
      renderNames(cachedItems, true);
      return true;
    }

    // Função para alternar modo tela cheia
    function toggleFullScreen() {
      if (!document.fullscreenElement) {
        document.documentElement.requestFullscreen().catch(err => {
          console.error(`Erro ao ativar tela cheia: ${err.message}`);
        });
      } else {
        if (document.exitFullscreen) {
          document.exitFullscreen();
        }
      }
    }

    async function fetchNames(options = {}) {
      const controller = new AbortController();
      const timeout = setTimeout(() => controller.abort(), options.timeout || FETCH_TIMEOUT);

      try {
        // Cache-busting: evita que uma resposta HTTP antiga seja reutilizada.
        const separator = API_URL.includes('?') ? '&' : '?';
        const url = `${API_URL}${separator}_ts=${Date.now()}`;

        const response = await fetch(url, {
          method: 'GET',
          redirect: 'follow',
          cache: 'no-store',
          signal: controller.signal
        });

        if (!response.ok) {
          throw new Error(`HTTP ${response.status}`);
        }

        const items = await response.json();

        if (!Array.isArray(items)) {
          throw new Error('Resposta do Apps Script não é uma lista válida');
        }

        cachedItems = items;
        saveCache(items);
        renderNames(items, false);

        console.log('Lugar de Oração: dados atualizados pelo Apps Script.');
      } catch (error) {
        if (cachedItems && cachedItems.length) {
          console.warn('Atualização falhou; mantendo último cache válido:', error);
        } else {
          console.error('Erro ao buscar dados:', error);
          renderNames([], false);
        }
      } finally {
        clearTimeout(timeout);
      }
    }

    function renderNames(items, fromCache = false) {
      const contentDiv = document.getElementById('creditsContent');
      
      if (!items || items.length === 0) {
        contentDiv.innerHTML = '<div class="status-msg">Nenhum nome cadastrado até o momento.</div>';
        return;
      }

      const cardsHTML = items.map(item => `
        <div class="name-card">
          <div class="name-title">${item.name}</div>
        </div>
      `).join('');

      contentDiv.innerHTML = `
        <div id="firstBlock" class="cards-grid">${cardsHTML}</div>
        <div id="secondBlock" class="cards-grid">${cardsHTML}</div>
      `;

      if (!isInitialized) {
        isInitialized = true;
        animateCredits();
      }
    }

    function animateCredits() {
      const content = document.getElementById('creditsContent');
      const firstBlock = document.getElementById('firstBlock');

      if (firstBlock) {
        const singleSetHeight = firstBlock.clientHeight;

        posY -= speed;

        if (Math.abs(posY) >= singleSetHeight) {
          posY = 0;
        }

        content.style.transform = `translateY(${posY}px)`;
      }

      animationId = requestAnimationFrame(animateCredits);
    }

    window.onload = async () => {
      // 1. Mostra imediatamente o último resultado salvo no aparelho.
      const hasCache = showCache();

      // 2. Atualiza em segundo plano. A página não fica esperando o Apps Script.
      fetchNames({ timeout: FETCH_TIMEOUT });

      // 3. Continua verificando novidades a cada 30 segundos.
      setInterval(() => fetchNames({ timeout: FETCH_TIMEOUT }), 30000);
    };
  </script>
</body>
</html>

