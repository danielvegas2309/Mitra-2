# Mitra-2
Novo dos leads
<!DOCTYPE html>
<html lang="pt-BR" data-theme="light">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Quiz C4 Nexus - Sessão Estratégica</title>
  <meta name="description" content="Diagnóstico estratégico C4 Nexus para identificar maturidade, frustrações e potencial de crescimento com ativos digitais." />
  <script src="https://cdn.tailwindcss.com"></script>
  <style>
    :root {
      --bg: #f7f6f2;
      --surface: rgba(255, 255, 255, 0.88);
      --surface-2: #fbfbf9;
      --surface-3: #f1eee8;
      --text: #28251d;
      --muted: #6f6b63;
      --border: rgba(40, 37, 29, 0.12);
      --accent: #01696f;
      --accent-soft: rgba(1, 105, 111, 0.10);
      --primary: #111111;
      --primary-hover: #242424;
      --success: #12715b;
      --danger: #9f2344;
      --shadow: 0 18px 50px rgba(17, 17, 17, 0.08);
    }

    [data-theme="dark"] {
      --bg: #171614;
      --surface: rgba(28, 27, 25, 0.92);
      --surface-2: #201f1d;
      --surface-3: #272521;
      --text: #efebe2;
      --muted: #a39f96;
      --border: rgba(239, 235, 226, 0.12);
      --accent: #61a9b1;
      --accent-soft: rgba(97, 169, 177, 0.12);
      --primary: #f2efe8;
      --primary-hover: #ffffff;
      --success: #56c39f;
      --danger: #e06d8d;
      --shadow: 0 18px 50px rgba(0, 0, 0, 0.28);
    }

    * { box-sizing: border-box; }
    html { scroll-behavior: smooth; }
    body {
      margin: 0;
      min-height: 100vh;
      font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
      background:
        radial-gradient(circle at top left, rgba(1, 105, 111, 0.10), transparent 28%),
        radial-gradient(circle at top right, rgba(1, 105, 111, 0.05), transparent 22%),
        var(--bg);
      color: var(--text);
      transition: background-color .25s ease, color .25s ease;
    }
    .step { display: none; }
    .step.active { display: block; animation: fadeUp .3s ease; }
    @keyframes fadeUp { from { opacity: 0; transform: translateY(10px); } to { opacity: 1; transform: translateY(0); } }
    .shell { background: var(--surface); border: 1px solid var(--border); box-shadow: var(--shadow); backdrop-filter: blur(14px); }
    .input, .select {
      width: 100%; border: 1px solid var(--border); background: var(--surface-2); color: var(--text);
      border-radius: 18px; padding: 16px 18px; outline: none; transition: border-color .2s ease, box-shadow .2s ease, background-color .2s ease;
    }
    .input::placeholder { color: var(--muted); }
    .input:focus, .select:focus { border-color: var(--accent); box-shadow: 0 0 0 4px var(--accent-soft); }
    .input.invalid, .select.invalid, .choice.invalid { border-color: var(--danger) !important; box-shadow: 0 0 0 4px rgba(159, 35, 68, 0.10); }
    .btn { width: 100%; border: none; border-radius: 20px; padding: 17px 22px; font-weight: 700; transition: transform .15s ease, opacity .2s ease, background-color .2s ease; min-height: 54px; }
    .btn-primary { background: var(--primary); color: var(--bg); }
    .btn-primary:hover { background: var(--primary-hover); transform: translateY(-1px); }
    .btn-secondary { background: transparent; color: var(--text); border: 1px solid var(--border); }
    .btn-secondary:hover { background: var(--surface-3); }
    .progress-track { width: 100%; height: 8px; border-radius: 999px; background: rgba(1, 105, 111, 0.12); overflow: hidden; }
    .progress-fill { width: 20%; height: 100%; border-radius: inherit; background: linear-gradient(90deg, var(--accent), #22a29c); transition: width .25s ease; }
    .choice { display: flex; align-items: center; gap: 12px; width: 100%; padding: 14px 16px; border: 1px solid var(--border); border-radius: 18px; background: var(--surface-2); cursor: pointer; transition: transform .15s ease, border-color .2s ease, background-color .2s ease; }
    .choice:hover { transform: translateY(-1px); border-color: rgba(1, 105, 111, 0.35); }
    .choice input { width: 18px; height: 18px; accent-color: var(--accent); }
    .error-box { display: none; margin-bottom: 20px; border-radius: 18px; border: 1px solid rgba(159, 35, 68, 0.22); background: rgba(159, 35, 68, 0.08); color: var(--danger); padding: 14px 16px; font-size: 14px; }
    .error-box.show { display: block; }
    .theme-toggle { position: absolute; top: 18px; right: 18px; width: 46px; height: 46px; border-radius: 999px; display: grid; place-items: center; border: 1px solid var(--border); background: var(--surface-2); color: var(--text); }
    .muted { color: var(--muted); }
    .logo-mark { width: 58px; height: 58px; margin: 0 auto 20px; display: grid; place-items: center; border-radius: 18px; background: linear-gradient(135deg, rgba(1, 105, 111, 0.14), rgba(1, 105, 111, 0.04)); border: 1px solid rgba(1, 105, 111, 0.14); }
    .result-card { border-radius: 28px; border: 1px solid rgba(18, 113, 91, 0.16); background: linear-gradient(180deg, rgba(18, 113, 91, 0.10), rgba(18, 113, 91, 0.03)); }
    .sr-only { position: absolute; width: 1px; height: 1px; padding: 0; margin: -1px; overflow: hidden; clip: rect(0, 0, 0, 0); white-space: nowrap; border: 0; }
    @media (max-width: 640px) { .theme-toggle { top: 12px; right: 12px; } }
  </style>
</head>
<body>
  <main class="min-h-screen px-4 py-8 sm:px-6 sm:py-12">
    <div class="max-w-2xl mx-auto relative">
      <button type="button" id="themeToggle" class="theme-toggle" aria-label="Alternar tema">
        <svg id="themeIcon" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true"><path d="M21 12.79A9 9 0 1 1 11.21 3 7 7 0 0 0 21 12.79z"></path></svg>
      </button>

      <section class="text-center mb-8 sm:mb-10 pt-8">
        <div class="logo-mark" aria-hidden="true"><svg width="28" height="28" viewBox="0 0 64 64" fill="none"><path d="M14 18C14 15.7909 15.7909 14 18 14H37L50 27V46C50 48.2091 48.2091 50 46 50H18C15.7909 50 14 48.2091 14 46V18Z" stroke="currentColor" stroke-width="4"/><path d="M37 14V27H50" stroke="currentColor" stroke-width="4"/><path d="M24 36H40" stroke="currentColor" stroke-width="4" stroke-linecap="round"/></svg></div>
        <h1 class="text-4xl sm:text-5xl font-bold tracking-tight">C4 Nexus</h1>
        <p class="text-xl mt-3 muted">Diagnóstico Estratégico</p>
        <p class="text-sm mt-2 muted">Descubra o potencial do seu conhecimento como Ativo Digital</p>
      </section>

      <form id="quizForm" class="shell rounded-[32px] p-6 sm:p-8" novalidate>
        <div class="mb-6">
          <div class="flex items-center justify-between text-sm mb-2"><span class="muted">Etapa <span id="currentStepLabel">1</span> de 5</span><span class="muted" id="stepTitleLabel">Vamos começar</span></div>
          <div class="progress-track"><div class="progress-fill" id="progressFill"></div></div>
        </div>

        <div id="errorBox" class="error-box" role="alert" aria-live="assertive"></div>

        <section id="step1" class="step active" data-title="Vamos começar">
          <h2 class="text-2xl font-semibold mb-2">Vamos começar</h2>
          <p class="muted mb-6">Preencha seus dados para liberar seu diagnóstico estratégico.</p>
          <div class="space-y-4">
            <label class="block"><span class="sr-only">Nome completo</span><input type="text" id="nome" class="input" placeholder="Nome completo" required /></label>
            <label class="block"><span class="sr-only">Melhor e-mail</span><input type="email" id="email" class="input" placeholder="Melhor e-mail" required /></label>
            <label class="block"><span class="sr-only">WhatsApp com DDD</span><input type="tel" id="whatsapp" class="input" placeholder="WhatsApp com DDD" required /></label>
            <label class="block"><span class="sr-only">Nome da sua empresa ou marca</span><input type="text" id="empresa" class="input" placeholder="Nome da sua empresa/marca" required /></label>
          </div>
          <button type="button" class="btn btn-primary mt-8" data-next="2">Continuar</button>
        </section>

        <section id="step2" class="step" data-title="Situação Atual">
          <h2 class="text-2xl font-semibold mb-2">Situação Atual</h2>
          <p class="muted mb-6">Mapeie o estágio atual da sua operação para direcionar a sessão.</p>
          <div class="space-y-5">
            <div><label for="faturamento" class="block text-sm font-medium mb-2">Faturamento médio mensal atual</label><select id="faturamento" class="select" required><option value="" selected disabled>Selecione...</option><option value="10-30">R$ 10 mil – R$ 30 mil</option><option value="31-80">R$ 31 mil – R$ 80 mil</option><option value="81-150">R$ 81 mil – R$ 150 mil</option><option value="151-300">R$ 151 mil – R$ 300 mil</option><option value="300+">Acima de R$ 300 mil</option></select></div>
            <div><label for="seguidores" class="block text-sm font-medium mb-2">Seguidores totais (redes sociais)</label><select id="seguidores" class="select" required><option value="" selected disabled>Selecione...</option><option value="menos8">Menos de 8 mil</option><option value="8-20">8 mil – 20 mil</option><option value="21-50">21 mil – 50 mil</option><option value="50+">Mais de 50 mil</option></select></div>
          </div>
          <div class="grid gap-3 sm:grid-cols-2 mt-8"><button type="button" class="btn btn-secondary" data-prev="1">Voltar</button><button type="button" class="btn btn-primary" data-next="3">Continuar</button></div>
        </section>

        <section id="step3" class="step" data-title="Maiores Frustrações">
          <h2 class="text-2xl font-semibold mb-2">Suas Maiores Frustrações</h2>
          <p class="muted mb-6">Selecione os pontos que mais limitam sua escala hoje.</p>
          <div class="space-y-3" id="frustracoesGroup">
            <label class="choice"><input type="checkbox" name="frustracoes" value="tempo"> <span>Trocar tempo por dinheiro</span></label>
            <label class="choice"><input type="checkbox" name="frustracoes" value="conteudo"> <span>Conteúdo que não converte em vendas</span></label>
            <label class="choice"><input type="checkbox" name="frustracoes" value="audiencia"> <span>Audiência grande mas sem conversão</span></label>
            <label class="choice"><input type="checkbox" name="frustracoes" value="autoridade"> <span>Falta de autoridade pessoal</span></label>
            <label class="choice"><input type="checkbox" name="frustracoes" value="legado"> <span>Dificuldade em construir legado</span></label>
          </div>
          <div class="grid gap-3 sm:grid-cols-2 mt-8"><button type="button" class="btn btn-secondary" data-prev="2">Voltar</button><button type="button" class="btn btn-primary" data-next="4">Continuar</button></div>
        </section>

        <section id="step4" class="step" data-title="Visão de Futuro">
          <h2 class="text-2xl font-semibold mb-2">Visão de Futuro</h2>
          <p class="muted mb-6">Defina a principal ambição para os próximos 12 a 18 meses.</p>
          <div class="space-y-5">
            <div><label for="objetivo" class="block text-sm font-medium mb-2">Principal objetivo com o C4 Nexus</label><select id="objetivo" class="select" required><option value="" selected disabled>Selecione...</option><option value="marca">Construir marca pessoal forte</option><option value="recorrente">Gerar receita recorrente com ativos digitais</option><option value="autoridade">Aumentar autoridade e influência</option><option value="legado">Criar legado intelectual</option></select></div>
            <div><label for="meta" class="block text-sm font-medium mb-2">Meta anual com produtos digitais (12-18 meses)</label><select id="meta" class="select" required><option value="" selected disabled>Selecione...</option><option value="300-600">R$ 300 mil – R$ 600 mil</option><option value="600-1000">R$ 600 mil – R$ 1 milhão</option><option value="1000+">Acima de R$ 1 milhão</option></select></div>
          </div>
          <div class="grid gap-3 sm:grid-cols-2 mt-8"><button type="button" class="btn btn-secondary" data-prev="3">Voltar</button><button type="button" class="btn btn-primary" data-next="5">Ver resultado</button></div>
        </section>

        <section id="step5" class="step" data-title="Resultado">
          <div class="text-center">
            <div class="inline-flex items-center gap-2 px-4 py-2 rounded-full text-sm mb-5" style="background: rgba(18, 113, 91, 0.12); color: var(--success); border: 1px solid rgba(18, 113, 91, 0.18);">Perfil validado para Sessão Estratégica</div>
            <h2 class="text-3xl sm:text-4xl font-bold mb-4">Parabéns, <span id="nomeResult">Empresário</span>!</h2>
            <p class="text-xl">Você tem <strong>perfil ideal</strong> para o C4 Nexus.</p>

            <div class="result-card my-8 p-6 sm:p-8">
              <p class="text-lg">Com o sistema completo você pode passar do faturamento atual para:</p>
              <p class="text-4xl sm:text-5xl font-bold mt-4" style="color: var(--success);">R$ 300 mil a R$ 1 milhão/ano</p>
              <p class="text-sm mt-3 muted">com ativos digitais recorrentes</p>
            </div>

            <p class="muted mb-8 max-w-xl mx-auto">Enquanto você constrói uma empresa forte, construa também um nome impossível de ignorar.</p>

            <a href="https://calendar.app.google/uYQPSPibLcYWVrdbA" target="_blank" rel="noopener noreferrer" class="block w-full rounded-[20px] py-5 font-semibold text-lg" style="background: var(--primary); color: var(--bg); text-decoration: none;">Agendar Sessão Estratégica Agora</a>

            <button type="button" class="btn btn-secondary mt-4" data-prev="4">Voltar e revisar respostas</button>
          </div>
        </section>
      </form>
    </div>
  </main>

  <script>
    const totalSteps = 5;
    let currentStep = 1;
    const errorBox = document.getElementById('errorBox');
    const currentStepLabel = document.getElementById('currentStepLabel');
    const stepTitleLabel = document.getElementById('stepTitleLabel');
    const progressFill = document.getElementById('progressFill');
    const themeToggle = document.getElementById('themeToggle');
    const themeIcon = document.getElementById('themeIcon');
    const fieldIds = ['nome', 'email', 'whatsapp', 'empresa', 'faturamento', 'seguidores', 'objetivo', 'meta'];
    const fields = fieldIds.map(id => document.getElementById(id)).filter(Boolean);
    const frustrationInputs = Array.from(document.querySelectorAll('input[name="frustracoes"]'));

    function updateProgress(step) {
      currentStep = step;
      currentStepLabel.textContent = String(step);
      progressFill.style.width = `${(step / totalSteps) * 100}%`;
      const section = document.getElementById(`step${step}`);
      stepTitleLabel.textContent = section ? section.dataset.title : '';
    }
    function showError(message) { errorBox.textContent = message; errorBox.classList.add('show'); }
    function clearError() { errorBox.textContent = ''; errorBox.classList.remove('show'); }
    function resetInvalidState() { fields.forEach(field => field.classList.remove('invalid')); document.querySelectorAll('.choice').forEach(choice => choice.classList.remove('invalid')); }
    function markInvalid(element) { if (!element) return; element.classList.add('invalid'); }
    function isValidEmail(email) { return /^[^s@]+@[^s@]+.[^s@]+$/.test(email); }

    function validateStep(step) {
      clearError(); resetInvalidState();
      if (step === 1) {
        const nome = document.getElementById('nome'); const email = document.getElementById('email'); const whatsapp = document.getElementById('whatsapp'); const empresa = document.getElementById('empresa');
        if (!nome.value.trim()) { markInvalid(nome); showError('Preencha seu nome completo para continuar.'); nome.focus(); return false; }
        if (!email.value.trim()) { markInvalid(email); showError('Preencha seu melhor e-mail para continuar.'); email.focus(); return false; }
        if (!isValidEmail(email.value.trim())) { markInvalid(email); showError('Digite um e-mail válido.'); email.focus(); email.reportValidity(); return false; }
        if (!whatsapp.value.trim()) { markInvalid(whatsapp); showError('Preencha seu WhatsApp com DDD.'); whatsapp.focus(); return false; }
        if (!empresa.value.trim()) { markInvalid(empresa); showError('Preencha o nome da sua empresa ou marca.'); empresa.focus(); return false; }
      }
      if (step === 2) {
        const faturamento = document.getElementById('faturamento'); const seguidores = document.getElementById('seguidores');
        if (!faturamento.value) { markInvalid(faturamento); showError('Selecione o faturamento médio mensal atual.'); faturamento.focus(); faturamento.reportValidity(); return false; }
        if (!seguidores.value) { markInvalid(seguidores); showError('Selecione o total de seguidores nas redes sociais.'); seguidores.focus(); seguidores.reportValidity(); return false; }
      }
      if (step === 3) {
        const checked = frustrationInputs.filter(input => input.checked);
        if (checked.length === 0) { document.querySelectorAll('.choice').forEach(choice => choice.classList.add('invalid')); showError('Selecione pelo menos uma frustração para continuar.'); frustrationInputs[0].focus(); return false; }
      }
      if (step === 4) {
        const objetivo = document.getElementById('objetivo'); const meta = document.getElementById('meta');
        if (!objetivo.value) { markInvalid(objetivo); showError('Selecione o principal objetivo com o C4 Nexus.'); objetivo.focus(); objetivo.reportValidity(); return false; }
        if (!meta.value) { markInvalid(meta); showError('Selecione a meta anual com produtos digitais.'); meta.focus(); meta.reportValidity(); return false; }
      }
      return true;
    }

    function populateResult() { const nome = document.getElementById('nome').value.trim(); document.getElementById('nomeResult').textContent = nome ? nome.split(' ')[0] : 'Empresário'; }
    function goToStep(step) { document.querySelectorAll('.step').forEach(section => section.classList.remove('active')); const section = document.getElementById(`step${step}`); section.classList.add('active'); updateProgress(step); clearError(); resetInvalidState(); if (step === 5) populateResult(); window.scrollTo({ top: 0, behavior: 'smooth' }); }

    document.querySelectorAll('[data-next]').forEach(button => { button.addEventListener('click', () => { if (validateStep(currentStep)) goToStep(Number(button.dataset.next)); }); });
    document.querySelectorAll('[data-prev]').forEach(button => { button.addEventListener('click', () => { goToStep(Number(button.dataset.prev)); }); });

    fields.forEach(field => { field.addEventListener('input', () => { field.classList.remove('invalid'); clearError(); }); field.addEventListener('change', () => { field.classList.remove('invalid'); clearError(); }); });
    frustrationInputs.forEach(input => { input.addEventListener('change', () => { document.querySelectorAll('.choice').forEach(choice => choice.classList.remove('invalid')); clearError(); }); });

    let currentTheme = window.matchMedia('(prefers-color-scheme: dark)').matches ? 'dark' : 'light';
    function renderTheme(theme) { document.documentElement.setAttribute('data-theme', theme); themeIcon.innerHTML = theme === 'dark' ? '<path d="M12 3v2M12 19v2M4.22 4.22l1.42 1.42M18.36 18.36l1.42 1.42M3 12h2M19 12h2M4.22 19.78l1.42-1.42M18.36 5.64l1.42-1.42"></path><circle cx="12" cy="12" r="4"></circle>' : '<path d="M21 12.79A9 9 0 1 1 11.21 3 7 7 0 0 0 21 12.79z"></path>'; }
    themeToggle.addEventListener('click', () => { currentTheme = currentTheme === 'dark' ? 'light' : 'dark'; renderTheme(currentTheme); });

    renderTheme(currentTheme); updateProgress(1);
  </script>
</body>
</html>
