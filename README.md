<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>CEJ - Expediente Judicial Electrónico | Poder Judicial del Perú</title>
  <!-- Tailwind CSS CDN -->
  <script src="https://cdn.tailwindcss.com"></script>
  <!-- Google Fonts: Inter & Merriweather -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=Merriweather:ital,wght@0,300;0,400;0,700;1,300&display=swap" rel="stylesheet">
  <!-- Lucide Icons -->
  <script src="https://unpkg.com/lucide@latest"></script>
  <style>
    body { font-family: 'Inter', sans-serif; }
    .font-judicial { font-family: 'Merriweather', serif; }
    .screen { display: none; }
    .screen.active { display: block; }
    .progress-bar-fill { transition: width 0.1s linear; }
    @keyframes pulse-red {
      0%, 100% { opacity: 1; }
      50% { opacity: 0.4; }
    }
    .timer-warning {
      animation: pulse-red 1s infinite;
      color: #ef4444 !important;
      border-color: #ef4444 !important;
    }
  </style>
</head>
<body class="bg-slate-100 text-slate-800 antialiased min-h-screen flex flex-col justify-between selection:bg-amber-600 selection:text-white">

  <!-- AVISO ACADÉMICO PERMANENTE -->
  <div class="bg-amber-500 text-slate-950 text-xs font-semibold px-4 py-1.5 text-center flex items-center justify-center gap-2 shadow-sm border-b border-amber-600 sticky top-0 z-50">
    <i data-lucide="graduation-cap" class="w-4 h-4"></i>
    <span>PORTAL DE SIMULACIÓN ACADÉMICA - FACULTAD DE DERECHO | USO DIDÁCTICO EXCLUSIVO</span>
  </div>

  <!-- CONTENEDOR PRINCIPAL -->
  <main class="flex-grow flex flex-col">

    <!-- ========================================== -->
    <!-- PANTALLA 0: BIENVENIDA                     -->
    <!-- ========================================== -->
    <section id="screen-0" class="screen active flex-grow flex items-center justify-center p-4">
      <div class="max-w-2xl w-full bg-white rounded-2xl shadow-2xl border border-slate-200 overflow-hidden my-8">
        <div class="bg-gradient-to-r from-[#0B2240] via-[#123157] to-[#0B2240] text-white p-8 text-center border-b-4 border-amber-500">
          <div class="w-20 h-20 mx-auto mb-4 bg-white/10 rounded-full flex items-center justify-center p-3 backdrop-blur-sm ring-2 ring-amber-400/50">
            <i data-lucide="scale" class="w-12 h-12 text-amber-400"></i>
          </div>
          <h1 class="text-2xl sm:text-3xl font-bold tracking-tight">PODER JUDICIAL DEL PERÚ</h1>
          <p class="text-amber-300 font-medium text-sm sm:text-base mt-1">Consulta de Expedientes Judiciales (CEJ) / EJE</p>
          <div class="inline-block mt-3 px-3 py-1 bg-white/10 rounded-full text-xs text-slate-200">
            Corte Superior de Justicia de Puno
          </div>
        </div>

        <div class="p-6 sm:p-8 space-y-6">
          <div class="bg-slate-50 border-l-4 border-[#0B2240] p-4 rounded-r-lg">
            <h2 class="text-sm font-bold text-[#0B2240] uppercase tracking-wider mb-1">Módulo del Expediente Judicial Electrónico (EJE)</h2>
            <p class="text-sm text-slate-600 leading-relaxed">
              Bienvenido al sistema institucional de seguimiento y visualización de resoluciones, recaudos y actuados procesales. Acceda para examinar el expediente laboral digitalizado de la sede Juliaca.
            </p>
          </div>

          <div class="grid grid-cols-1 sm:grid-cols-2 gap-4 text-xs text-slate-600">
            <div class="flex items-start gap-2 bg-slate-50 p-3 rounded-lg border border-slate-100">
              <i data-lucide="shield-check" class="w-4 h-4 text-emerald-600 flex-shrink-0 mt-0.5"></i>
              <span>Firma digital certificada y foliatura correlativa electrónica oficial.</span>
            </div>
            <div class="flex items-start gap-2 bg-slate-50 p-3 rounded-lg border border-slate-100">
              <i data-lucide="clock" class="w-4 h-4 text-amber-600 flex-shrink-0 mt-0.5"></i>
              <span>Sesión cifrada con temporizador de seguridad de 7 minutos.</span>
            </div>
          </div>

          <div class="pt-2">
            <button onclick="goToScreen1()" class="w-full bg-[#0B2240] hover:bg-[#123157] text-white font-semibold py-3.5 px-6 rounded-xl shadow-lg hover:shadow-xl transition-all duration-200 flex items-center justify-center gap-2 group">
              <span>Ingresar al Sistema de Consulta</span>
              <i data-lucide="arrow-right" class="w-5 h-5 group-hover:translate-x-1 transition-transform"></i>
            </button>
          </div>
        </div>
      </div>
    </section>

    <!-- ========================================== -->
    <!-- PANTALLA 1: CARGA DE TRANSICIÓN AL PORTAL  -->
    <!-- ========================================== -->
    <section id="screen-1" class="screen flex-grow flex items-center justify-center p-4">
      <div class="max-w-md w-full text-center space-y-6">
        <div class="relative w-24 h-24 mx-auto">
          <div class="absolute inset-0 rounded-full border-4 border-slate-200"></div>
          <div class="absolute inset-0 rounded-full border-4 border-[#0B2240] border-t-transparent animate-spin"></div>
          <div class="absolute inset-0 flex items-center justify-center">
            <i data-lucide="scale" class="w-10 h-10 text-amber-500 animate-pulse"></i>
          </div>
        </div>
        <div>
          <h3 class="text-lg font-bold text-slate-800">Conectando con el Servidor Jurisdiccional</h3>
          <p class="text-xs text-slate-500 mt-1">Corte Superior de Justicia de Puno - Sistema Integrado Judicial (SIJ)</p>
        </div>
        <div class="w-full bg-slate-200 h-2 rounded-full overflow-hidden">
          <div id="p1-progress" class="bg-[#0B2240] h-full w-0 progress-bar-fill"></div>
        </div>
        <p class="text-xs text-slate-400">Verificando credenciales de acceso institucional...</p>
      </div>
    </section>

    <!-- ========================================== -->
    <!-- PANTALLA 2: PORTAL ESTATAL Y BÚSQUEDA       -->
    <!-- ========================================== -->
    <section id="screen-2" class="screen flex-grow flex flex-col">
      <!-- Barra Superior Estatal -->
      <header class="bg-[#0B2240] text-white shadow-md">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 py-3 flex flex-wrap items-center justify-between gap-4">
          <div class="flex items-center gap-3">
            <div class="bg-white/10 p-2 rounded-lg">
              <i data-lucide="landmark" class="w-6 h-6 text-amber-400"></i>
            </div>
            <div>
              <div class="text-xs font-semibold tracking-wider text-amber-400 uppercase">Poder Judicial del Perú</div>
              <div class="text-base sm:text-lg font-bold leading-tight">Consulta de Expedientes Judiciales - CEJ</div>
            </div>
          </div>

          <!-- Cronómetro de 7 minutos -->
          <div class="flex items-center gap-3">
            <div id="session-timer-badge" class="flex items-center gap-2 bg-slate-800/80 px-3 py-1.5 rounded-lg border border-slate-700 text-xs text-slate-300 font-mono">
              <i data-lucide="timer" class="w-4 h-4 text-amber-400"></i>
              <span>Tiempo de sesión:</span>
              <strong id="session-timer" class="text-white text-sm">07:00</strong>
            </div>
            <button onclick="resetTimer()" title="Reiniciar sesión" class="p-1.5 text-slate-400 hover:text-white bg-slate-800 hover:bg-slate-700 rounded-md">
              <i data-lucide="rotate-cw" class="w-4 h-4"></i>
            </button>
          </div>
        </div>

        <!-- Menú Horizontal de Navegación Estatal -->
        <nav class="bg-[#07172c] border-t border-slate-700/60 px-4 sm:px-6">
          <div class="max-w-7xl mx-auto flex items-center overflow-x-auto gap-1 text-xs sm:text-sm font-medium">
            <button onclick="showNavTab('inicio')" class="nav-tab px-4 py-2.5 text-white border-b-2 border-amber-500 whitespace-nowrap flex items-center gap-1.5">
              <i data-lucide="home" class="w-4 h-4"></i> Inicio
            </button>
            <button onclick="showNavTab('mision')" class="nav-tab px-4 py-2.5 text-slate-300 hover:text-white border-b-2 border-transparent hover:border-slate-500 whitespace-nowrap">
              Misión
            </button>
            <button onclick="showNavTab('vision')" class="nav-tab px-4 py-2.5 text-slate-300 hover:text-white border-b-2 border-transparent hover:border-slate-500 whitespace-nowrap">
              Visión
            </button>
            <button onclick="showNavTab('transparencia')" class="nav-tab px-4 py-2.5 text-slate-300 hover:text-white border-b-2 border-transparent hover:border-slate-500 whitespace-nowrap">
              Transparencia
            </button>
            <button onclick="showNavTab('contactanos')" class="nav-tab px-4 py-2.5 text-slate-300 hover:text-white border-b-2 border-transparent hover:border-slate-500 whitespace-nowrap">
              Contáctanos
            </button>
            <button onclick="activateSearch()" class="nav-tab ml-auto px-4 py-2 text-amber-300 bg-amber-500/20 hover:bg-amber-500/30 rounded my-1 border border-amber-500/40 whitespace-nowrap flex items-center gap-1.5 font-semibold">
              <i data-lucide="search" class="w-4 h-4"></i> Búsqueda de Expedientes
            </button>
          </div>
        </nav>
      </header>

      <!-- Zona Central -->
      <div class="max-w-7xl mx-auto w-full p-4 sm:p-6 flex-grow flex flex-col">
        <!-- VISTA POR DEFECTO: TEMIS -->
        <div id="temis-view" class="flex-grow flex flex-col items-center justify-center text-center p-8 bg-white rounded-2xl shadow-sm border border-slate-200">
          <div class="relative w-48 h-48 sm:w-64 sm:h-64 mb-6 flex items-center justify-center">
            <svg class="w-full h-full text-[#0B2240] drop-shadow-md" viewBox="0 0 200 200" fill="none" xmlns="http://www.w3.org/2000/svg">
              <circle cx="100" cy="100" r="90" fill="#f8fafc" stroke="#C5A059" stroke-width="3"/>
              <path d="M100 25 L100 160" stroke="#0B2240" stroke-width="4" stroke-linecap="round"/>
              <path d="M80 160 L120 160" stroke="#0B2240" stroke-width="6" stroke-linecap="round"/>
              <path d="M70 170 L130 170" stroke="#0B2240" stroke-width="4" stroke-linecap="round"/>
              <path d="M50 55 L150 55" stroke="#C5A059" stroke-width="4" stroke-linecap="round"/>
              <circle cx="100" cy="55" r="6" fill="#0B2240"/>
              <path d="M50 55 L35 95" stroke="#64748b" stroke-width="2"/>
              <path d="M50 55 L65 95" stroke="#64748b" stroke-width="2"/>
              <path d="M25 95 Q50 115 75 95 Z" fill="#C5A059"/>
              <path d="M150 55 L135 95" stroke="#64748b" stroke-width="2"/>
              <path d="M150 55 L165 95" stroke="#64748b" stroke-width="2"/>
              <path d="M125 95 Q150 115 175 95 Z" fill="#C5A059"/>
              <path d="M85 40 Q100 35 115 40" stroke="#0B2240" stroke-width="3" stroke-linecap="round"/>
            </svg>
          </div>
          <h2 class="text-2xl font-bold text-[#0B2240]">Iustitia & Lex - Sistema Judicial Peruano</h2>
          <p class="text-slate-600 max-w-lg mt-2 text-sm">
            Para consultar el expediente judicial y sus piezas digitalizadas, haga clic en el botón <strong class="text-[#0B2240]">"Búsqueda de Expedientes"</strong> ubicado en la barra superior.
          </p>
          <button onclick="activateSearch()" class="mt-6 bg-[#0B2240] hover:bg-[#123157] text-white px-6 py-2.5 rounded-lg text-sm font-semibold flex items-center gap-2 shadow">
            <i data-lucide="search" class="w-4 h-4 text-amber-400"></i>
            Abrir Búsqueda de Expediente
          </button>
        </div>

        <!-- VISTA DE INFORMACIÓN INSTITUCIONAL -->
        <div id="info-modal-content" class="hidden bg-white p-8 rounded-2xl shadow-sm border border-slate-200 flex-grow">
          <div class="flex justify-between items-center pb-4 border-b border-slate-200 mb-6">
            <h3 id="info-title" class="text-xl font-bold text-[#0B2240]">Información</h3>
            <button onclick="closeInfoView()" class="text-slate-400 hover:text-slate-600">
              <i data-lucide="x" class="w-6 h-6"></i>
            </button>
          </div>
          <div id="info-body" class="text-slate-700 leading-relaxed text-sm space-y-4"></div>
        </div>

        <!-- VISTA DE BÚSQUEDA (CAPTCHA + FORMULARIO) -->
        <div id="search-view" class="hidden flex-grow flex flex-col justify-center max-w-3xl mx-auto w-full">
          <div class="bg-white rounded-2xl shadow-md border border-slate-200 overflow-hidden">
            <div class="bg-[#0B2240] text-white px-6 py-4 flex items-center justify-between">
              <div class="flex items-center gap-2">
                <i data-lucide="search" class="w-5 h-5 text-amber-400"></i>
                <h3 class="font-bold text-base">Consulta de Causas Judiciales</h3>
              </div>
              <button onclick
