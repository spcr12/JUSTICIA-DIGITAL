<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>CEJ - Consulta de Expedientes Judiciales | Poder Judicial del Perú</title>
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
    .progress-bar-fill {
      transition: width 0.1s linear;
    }
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

  <!-- CONTENEDOR PRINCIPAL DE PANTALLAS -->
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
              Bienvenido al sistema institucional de seguimiento y visualización de resoluciones, recaudos y actuados procesales. Acceda para examinar el registro digitalizado del expediente judicial.
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

      <!-- Zona de Contenido Central -->
      <div class="max-w-7xl mx-auto w-full p-4 sm:p-6 flex-grow flex flex-col">
        <!-- VISTA POR DEFECTO: ILUSTRACIÓN TEMIS (DIOSA DE LA JUSTICIA) -->
        <div id="temis-view" class="flex-grow flex flex-col items-center justify-center text-center p-8 bg-white rounded-2xl shadow-sm border border-slate-200">
          <div class="relative w-48 h-48 sm:w-64 sm:h-64 mb-6 flex items-center justify-center">
            <!-- Representación SVG de Temis / Balanza de Justicia -->
            <svg class="w-full h-full text-[#0B2240] drop-shadow-md" viewBox="0 0 200 200" fill="none" xmlns="http://www.w3.org/2000/svg">
              <circle cx="100" cy="100" r="90" fill="#f8fafc" stroke="#C5A059" stroke-width="3"/>
              <!-- Columna Central / Espada y Balanza -->
              <path d="M100 25 L100 160" stroke="#0B2240" stroke-width="4" stroke-linecap="round"/>
              <path d="M80 160 L120 160" stroke="#0B2240" stroke-width="6" stroke-linecap="round"/>
              <path d="M70 170 L130 170" stroke="#0B2240" stroke-width="4" stroke-linecap="round"/>
              <!-- Travesaño de Balanza -->
              <path d="M50 55 L150 55" stroke="#C5A059" stroke-width="4" stroke-linecap="round"/>
              <circle cx="100" cy="55" r="6" fill="#0B2240"/>
              <!-- Plato Izquierdo -->
              <path d="M50 55 L35 95" stroke="#64748b" stroke-width="2"/>
              <path d="M50 55 L65 95" stroke="#64748b" stroke-width="2"/>
              <path d="M25 95 Q50 115 75 95 Z" fill="#C5A059"/>
              <!-- Plato Derecho -->
              <path d="M150 55 L135 95" stroke="#64748b" stroke-width="2"/>
              <path d="M150 55 L165 95" stroke="#64748b" stroke-width="2"/>
              <path d="M125 95 Q150 115 175 95 Z" fill="#C5A059"/>
              <!-- Ojos Vendados / Símbolo Temis -->
              <path d="M85 40 Q100 35 115 40" stroke="#0B2240" stroke-width="3" stroke-linecap="round"/>
            </svg>
          </div>
          <h2 class="text-2xl font-bold text-[#0B2240]">Iustitia & Lex - Sistema Judicial Peruano</h2>
          <p class="text-slate-600 max-w-lg mt-2 text-sm">
            Para consultar el expediente judicial electrónico y los recaudos probatorios, haga clic en el botón <strong class="text-[#0B2240]">"Búsqueda de Expedientes"</strong> ubicado en la barra de navegación superior.
          </p>
          <button onclick="activateSearch()" class="mt-6 bg-[#0B2240] hover:bg-[#123157] text-white px-6 py-2.5 rounded-lg text-sm font-semibold flex items-center gap-2 shadow">
            <i data-lucide="search" class="w-4 h-4 text-amber-400"></i>
            Abrir Búsqueda de Expediente
          </button>
        </div>

        <!-- VISTA DE CONTENIDOS INSTITUCIONALES (Misión, Visión, etc.) -->
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
              <button onclick="cancelSearch()" class="text-slate-300 hover:text-white text-xs">Cerrar</button>
            </div>

            <div class="p-6 space-y-6">
              <!-- PASO 1: CAPTCHA OBLIGATORIO -->
              <div id="captcha-step" class="space-y-4">
                <div class="bg-amber-50 border border-amber-200 text-amber-900 px-4 py-3 rounded-lg text-xs flex items-center gap-2">
                  <i data-lucide="shield-alert" class="w-4 h-4 flex-shrink-0 text-amber-600"></i>
                  <span>Validación de seguridad obligatoria antes de consultar expedientes.</span>
                </div>

                <div class="flex flex-col sm:flex-row items-center gap-4 bg-slate-50 p-4 rounded-xl border border-slate-200">
                  <div class="flex items-center gap-3">
                    <div id="captcha-display" class="bg-slate-800 text-amber-400 font-mono tracking-widest text-2xl font-bold px-6 py-2.5 rounded-lg select-none line-through italic">
                      7B8K2
                    </div>
                    <button onclick="generateCaptcha()" title="Generar nuevo código" class="p-2 text-slate-500 hover:text-[#0B2240] hover:bg-slate-200 rounded-lg">
                      <i data-lucide="refresh-cw" class="w-5 h-5"></i>
                    </button>
                  </div>
                  <div class="flex-grow w-full">
                    <input type="text" id="captcha-input" placeholder="Ingrese el código de la imagen" class="w-full px-4 py-2 border border-slate-300 rounded-lg uppercase text-sm font-semibold focus:outline-none focus:ring-2 focus:ring-[#0B2240]">
                  </div>
                </div>

                <button onclick="validateCaptcha()" class="w-full bg-[#0B2240] hover:bg-[#123157] text-white py-2.5 rounded-lg font-semibold text-sm transition">
                  Validar Código y Continuar
                </button>
                <div id="captcha-error" class="hidden text-xs text-red-600 font-medium text-center">Código de seguridad incorrecto. Intente nuevamente.</div>
              </div>

              <!-- PASO 2: FORMULARIOS DE BÚSQUEDA (Se desbloquea tras validar CAPTCHA) -->
              <div id="query-step" class="hidden space-y-6">
                <!-- Pestañas de Búsqueda -->
                <div class="flex border-b border-slate-200 text-sm font-medium">
                  <button id="tab-btn-code" onclick="switchSearchTab('code')" class="py-2.5 px-4 text-[#0B2240] border-b-2 border-[#0B2240] font-bold">Por Código de Expediente</button>
                  <button id="tab-btn-party" onclick="switchSearchTab('party')" class="py-2.5 px-4 text-slate-500 hover:text-slate-700 border-b-2 border-transparent">Por Partes Procesales</button>
                </div>

                <!-- Formulario: Por Código -->
                <div id="form-by-code" class="space-y-4">
                  <div class="grid grid-cols-2 sm:grid-cols-4 gap-3 text-xs">
                    <div>
                      <label class="block font-semibold text-slate-600 mb-1">Correlativo</label>
                      <input id="in-correlativo" type="text" value="00174" class="w-full p-2 border rounded font-mono text-center">
                    </div>
                    <div>
                      <label class="block font-semibold text-slate-600 mb-1">Año</label>
                      <input id="in-ano" type="text" value="2019" class="w-full p-2 border rounded font-mono text-center">
                    </div>
                    <div>
                      <label class="block font-semibold text-slate-600 mb-1">Cuaderno</label>
                      <input id="in-cuaderno" type="text" value="0" class="w-full p-2 border rounded font-mono text-center">
                    </div>
                    <div>
                      <label class="block font-semibold text-slate-600 mb-1">Distrito Jud.</label>
                      <input id="in-distrito" type="text" value="2111" class="w-full p-2 border rounded font-mono text-center">
                    </div>
                  </div>
                  <div class="grid grid-cols-2 gap-3 text-xs">
                    <div>
                      <label class="block font-semibold text-slate-600 mb-1">Instancia / Órgano</label>
                      <input id="in-organo" type="text" value="JR-LA" class="w-full p-2 border rounded font-mono text-center">
                    </div>
                    <div>
                      <label class="block font-semibold text-slate-600 mb-1">Especialidad</label>
                      <input id="in-esp" type="text" value="02" class="w-full p-2 border rounded font-mono text-center">
                    </div>
                  </div>

                  <div class="p-3 bg-slate-50 rounded-lg border border-slate-200 text-xs text-slate-600 flex items-center justify-between">
                    <span>Expediente sugerido: <strong>00174-2019-0-2111-JR-LA-02</strong> (EsSalud vs Supo)</span>
                    <button onclick="autofillCode()" class="text-amber-700 font-bold hover:underline">Autocompletar</button>
                  </div>
                </div>

                <!-- Formulario: Por Partes -->
                <div id="form-by-party" class="hidden space-y-4 text-xs">
                  <div>
                    <label class="block font-semibold text-slate-600 mb-1">Distrito Judicial</label>
                    <select class="w-full p-2 border rounded">
                      <option>Puno</option>
                    </select>
                  </div>
                  <div>
                    <label class="block font-semibold text-slate-600 mb-1">Tipo de Persona</label>
                    <div class="flex gap-4">
                      <label class="flex items-center gap-1.5"><input type="radio" name="ptype" checked> Natural</label>
                      <label class="flex items-center gap-1.5"><input type="radio" name="ptype"> Jurídica</label>
                    </div>
                  </div>
                  <div>
                    <label class="block font-semibold text-slate-600 mb-1">Apellidos y Nombres / Razón Social</label>
                    <input id="in-party-name" type="text" value="Supo Quispe Andrés Leonidas" class="w-full p-2 border rounded">
                  </div>
                  <div class="flex gap-2">
                    <button onclick="setParty('Supo Quispe Andrés Leonidas')" class="px-2 py-1 bg-slate-100 rounded border hover:bg-slate-200">Supo Quispe</button>
                    <button onclick="setParty('Seguro Social de Salud - EsSalud')" class="px-2 py-1 bg-slate-100 rounded border hover:bg-slate-200">EsSalud</button>
                    <button onclick="setParty('SILSA')" class="px-2 py-1 bg-slate-100 rounded border hover:bg-slate-200">SILSA</button>
                  </div>
                </div>

                <!-- Botón Buscar -->
                <button onclick="executeSearch()" class="w-full bg-[#0B2240] hover:bg-[#123157] text-white py-3 rounded-lg font-bold text-sm flex items-center justify-center gap-2 shadow">
                  <i data-lucide="search" class="w-4 h-4"></i> Consultar Expediente Electrónico
                </button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- ========================================== -->
    <!-- PANTALLA 3: CARGA DE CONSULTA A BASE SIJ   -->
    <!-- ========================================== -->
    <section id="screen-3" class="screen flex-grow flex items-center justify-center p-4">
      <div class="max-w-md w-full text-center space-y-6">
        <div class="inline-block p-4 bg-white rounded-2xl shadow-lg border border-slate-200">
          <i data-lucide="folder-search" class="w-16 h-16 text-[#0B2240] animate-bounce mx-auto"></i>
        </div>
        <div>
          <h3 class="text-lg font-bold text-slate-800">Recuperando Cuaderno Principal y Fojas Digitalizadas</h3>
          <p class="text-xs text-slate-500 mt-1">Expediente N° 00174-2019-0-2111-JR-LA-02 - Puno</p>
        </div>
        <div class="w-full bg-slate-200 h-2 rounded-full overflow-hidden">
          <div id="p3-progress" class="bg-amber-500 h-full w-0 progress-bar-fill"></div>
        </div>
        <p class="text-xs text-slate-400">Descargando árbol de indexación cronológica EJE...</p>
      </div>
    </section>

    <!-- ========================================== -->
    <!-- PANTALLA 4: VISOR INTEGRAL DEL EXPEDIENTE  -->
    <!-- ========================================== -->
    <section id="screen-4" class="screen flex-grow flex flex-col bg-slate-100">
      <!-- Cabecera de Visor EJE -->
      <div class="bg-[#0B2240] text-white border-b-2 border-amber-500 px-4 sm:px-8 py-4">
        <div class="max-w-7xl mx-auto flex flex-wrap items-center justify-between gap-4">
          <div>
            <div class="text-xs text-amber-400 font-semibold uppercase tracking-wider">Módulo de Consulta EJE - Expediente Electrónico</div>
            <h1 class="text-xl sm:text-2xl font-bold font-mono tracking-tight text-white flex items-center gap-2">
              <i data-lucide="file-text" class="w-6 h-6 text-amber-400"></i>
              EXP. 00174-2019-0-2111-JR-LA-02
            </h1>
          </div>
          <div class="flex items-center gap-3">
            <span class="text-xs bg-emerald-500/20 text-emerald-300 border border-emerald-500/40 px-3 py-1 rounded-full font-semibold">En Trámite</span>
            <button onclick="returnToSearch()" class="bg-white/10 hover:bg-white/20 text-white text-xs px-3.5 py-2 rounded-lg flex items-center gap-1.5 transition">
              <i data-lucide="arrow-left" class="w-4 h-4"></i> Nueva Búsqueda
            </button>
          </div>
        </div>
      </div>

      <div class="max-w-7xl mx-auto w-full p-4 sm:p-6 space-y-6 flex-grow">

        <!-- 1. DATOS GENERALES DEL EXPEDIENTE (CARD) -->
        <div class="bg-white rounded-xl shadow-sm border border-slate-200 overflow-hidden">
          <div class="bg-slate-50 px-6 py-3 border-b border-slate-200 flex items-center justify-between">
            <h2 class="text-sm font-bold text-[#0B2240] uppercase tracking-wider flex items-center gap-2">
              <i data-lucide="info" class="w-4 h-4 text-amber-500"></i>
              1. Ficha Técnica y Datos Generales del Expediente
            </h2>
            <span class="text-xs text-slate-500 font-mono">Barcode: 22019001742111334000038</span>
          </div>
          <div class="p-6 grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4 text-xs">
            <div>
              <span class="text-slate-500 block">Distrito Judicial / Sede:</span>
              <span class="font-bold text-slate-800">Puno / San Román – Sede Central Juliaca (Jr. Apurímac / Pumacahua)</span>
            </div>
            <div>
              <span class="text-slate-500 block">Órgano Jurisdiccional Actual:</span>
              <span class="font-bold text-slate-800">Juzgado de Trabajo – Zona Norte – Sede Juliaca (Módulo Corporativo Laboral)</span>
            </div>
            <div>
              <span class="text-slate-500 block">Órgano de Origen:</span>
              <span class="font-semibold text-slate-700">2° Juzgado Civil Sede Juliaca (Mesa de Partes Única)</span>
            </div>
            <div>
              <span class="text-slate-500 block">Juez a Cargo:</span>
              <span class="font-bold text-[#0B2240]">Huamán Romero, Gonzalo Víctor</span>
            </div>
            <div>
              <span class="text-slate-500 block">Especialista Legal / Secretaria:</span>
              <span class="font-semibold text-slate-700">Carlos Villán, Rosario <span class="text-slate-400 font-normal">(Ant.: Iván Palomino Jara)</span></span>
            </div>
            <div>
              <span class="text-slate-500 block">Fecha y Hora de Ingreso:</span>
              <span class="font-semibold text-slate-700">26/06/2019 – 11:31:38</span>
            </div>
            <div>
              <span class="text-slate-500 block">Materia:</span>
              <span class="font-bold text-amber-700">Desnaturalización de Contrato / Desnaturalización de Intermediación Laboral</span>
            </div>
            <div>
              <span class="text-slate-500 block">Vía Procedimental:</span>
              <span class="font-semibold text-slate-700">Proceso Ordinario Laboral (Ley N° 26636)</span>
            </div>
            <div>
              <span class="text-slate-500 block">Estado Procesal:</span>
              <span class="font-semibold text-emerald-700">Contestada / Traslado de Excepciones y Medios Probatorios</span>
            </div>
          </div>
        </div>

        <!-- 2. PARTES PROCESALES Y PETITORIO -->
        <div class="grid grid-cols-1 lg:grid-cols-3 gap-6">
          <!-- Partes Procesales (2 cols) -->
          <div class="lg:col-span-2 bg-white rounded-xl shadow-sm border border-slate-200 overflow-hidden">
            <div class="bg-slate-50 px-6 py-3 border-b border-slate-200">
              <h2 class="text-sm font-bold text-[#0B2240] uppercase tracking-wider flex items-center gap-2">
                <i data-lucide="users" class="w-4 h-4 text-amber-500"></i>
                2. Sujetos Procesales y Representantes
              </h2>
            </div>
            <div class="p-6 space-y-4 text-xs">
              <!-- Demandante -->
              <div class="p-3 bg-blue-50/50 rounded-lg border border-blue-100 space-y-1">
                <div class="flex items-center justify-between">
                  <span class="font-bold text-blue-900 uppercase">Parte Demandante</span>
                  <span class="bg-blue-100 text-blue-800 px-2 py-0.5 rounded font-mono text-[10px]">DNI: 02167445</span>
                </div>
                <div class="text-sm font-bold text-slate-900">Andrés Leonidas Supo Quispe</div>
                <div class="text-slate-600">Domicilio Real: Av. Manco Cápac N° 964, Juliaca, San Román, Puno.</div>
                <div class="text-slate-600">Abogado: Dr. Lino Larico Larico (Reg. CAP N° 47) | Casilla SINOE: <strong class="text-slate-800">60375</strong></div>
                <div class="text-slate-600">Domicilio Procesal: Jr. Pumacahua N° 150, 2do Piso, Of. 205, Juliaca.</div>
              </div>

              <!-- Demandado -->
              <div class="p-3 bg-red-50/50 rounded-lg border border-red-100 space-y-1">
                <div class="flex items-center justify-between">
                  <span class="font-bold text-red-900 uppercase">Parte Demandada</span>
                  <span class="bg-red-100 text-red-800 px-2 py-0.5 rounded font-mono text-[10px]">RUC: 20131257750</span>
                </div>
                <div class="text-sm font-bold text-slate-900">Seguro Social de Salud – EsSalud (Red Asistencial Juliaca)</div>
                <div class="text-slate-600">Domicilio Real: Av. José Santos Chocano S/N, Urb. La Capilla, Juliaca.</div>
                <div class="text-slate-600">Apoderado Judicial: Abog. Hernán Rolando López Alférez (DNI 01207861 - Partida N° 11008571 Zona Reg. IX).</div>
                <div class="text-slate-600">Casilla SINOE: <strong class="text-slate-800">59629</strong> | Domicilio Proc.: Jr. Mariano Núñez N° 139, Juliaca.</div>
              </div>

              <!-- Tercero Vinculado -->
              <div class="p-3 bg-slate-50 rounded-lg border border-slate-200 space-y-1">
                <div class="flex items-center justify-between">
                  <span class="font-bold text-slate-700 uppercase">Tercero Vinculado (Empresa de Intermediación)</span>
                  <span class="bg-slate-200 text-slate-800 px-2 py-0.5 rounded font-mono text-[10px]">RUC: 20100362598</span>
                </div>
                <div class="text-sm font-bold text-slate-800">Servicios Integrados de Limpieza S.A. – SILSA</div>
                <div class="text-slate-600">Empresa prestadora de servicios de intermediación complementaria.</div>
              </div>
            </div>
          </div>

          <!-- Petitorio (1 col) -->
          <div class="bg-white rounded-xl shadow-sm border border-slate-200 overflow-hidden flex flex-col">
            <div class="bg-slate-50 px-6 py-3 border-b border-slate-200">
              <h2 class="text-sm font-bold text-[#0B2240] uppercase tracking-wider flex items-center gap-2">
                <i data-lucide="crosshair" class="w-4 h-4 text-amber-500"></i>
                3. Pretensión Demandada
              </h2>
            </div>
            <div class="p-6 space-y-4 text-xs leading-relaxed flex-grow">
              <div class="border-l-2 border-amber-500 pl-3">
                <span class="font-bold text-slate-800 block mb-1">Pretensión Principal:</span>
                <p class="text-slate-600">
                  Se declare judicialmente la <strong>desnaturalización de la intermediación laboral</strong> bajo la cual el accionante viene laborando en la Red Asistencial Juliaca de EsSalud.
                </p>
              </div>
              <div class="border-l-2 border-[#0B2240] pl-3">
                <span class="font-bold text-slate-800 block mb-1">Pretensión Accesoria:</span>
                <p class="text-slate-600">
                  Se ordene a EsSalud registrar al demandante en sus planillas de remuneraciones bajo el <strong>régimen laboral a plazo indeterminado (D. Leg. N° 728)</strong>, con retroactividad al <strong>01 de diciembre de 1996</strong>, en el puesto de <em>Almacenero</em> de la Unidad de Almacenes.
                </p>
              </div>
              <div class="bg-amber-50 p-3 rounded text-[11px] text-amber-900 border border-amber-200">
                Principio rector invocado: <strong>Primacía de la Realidad</strong> frente a contratos de locación y destaque fraudulento.
              </div>
            </div>
          </div>
        </div>

        <!-- 4. ÍNDICE CRONOLÓGICO DE ACTUADOS EJE (TABLA INTERACTIVA) -->
        <div class="bg-white rounded-xl shadow-sm border border-slate-200 overflow-hidden">
          <div class="bg-slate-50 px-6 py-4 border-b border-slate-200 flex flex-wrap items-center justify-between gap-3">
            <div>
              <h2 class="text-sm font-bold text-[#0B2240] uppercase tracking-wider flex items-center gap-2">
                <i data-lucide="layers" class="w-4 h-4 text-amber-500"></i>
                4. Índice Cronológico de Actuados Procesales (EJE)
              </h2>
              <p class="text-xs text-slate-500">Listado íntegro de folios, escritos, resoluciones y notificaciones del expediente</p>
            </div>
            <span class="text-xs bg-slate-200 text-slate-700 font-mono px-3 py-1 rounded-full">12 Actuados Registrados</span>
          </div>

          <div class="overflow-x-auto">
            <table class="w-full text-left text-xs border-collapse">
              <thead class="bg-[#0B2240] text-white uppercase text-[11px] font-semibold">
                <tr>
                  <th class="py-3 px-4 text-center w-12">N°</th>
                  <th class="py-3 px-3 w-24">Fojas</th>
                  <th class="py-3 px-3 w-28">Fecha</th>
                  <th class="py-3 px-4 w-48">Tipo de Actuado</th>
                  <th class="py-3 px-4">Descripción y Contenido Procesal</th>
                  <th class="py-3 px-4 text-center w-28">Acción</th>
                </tr>
              </thead>
              <tbody id="timeline-rows" class="divide-y divide-slate-200">
                <!-- Se poblará vía JavaScript con los 12 actuados detallados -->
              </tbody>
            </table>
          </div>
        </div>

        <!-- 5. RECAUDOS Y MEDIOS PROBATORIOS RELEVANTES (ANEXOS 1-A al 1-U) -->
        <div class="bg-white rounded-xl shadow-sm border border-slate-200 overflow-hidden">
          <div class="bg-slate-50 px-6 py-4 border-b border-slate-200 flex items-center justify-between">
            <div>
              <h2 class="text-sm font-bold text-[#0B2240] uppercase tracking-wider flex items-center gap-2">
                <i data-lucide="archive" class="w-4 h-4 text-amber-500"></i>
                5. Medios Probatorios Ofrecidos en Demanda (Anexos 1-A al 1-U)
              </h2>
              <p class="text-xs text-slate-500">Recaudos probatorios admitidos para acreditación de la primacía de la realidad</p>
            </div>
            <span class="text-xs bg-amber-100 text-amber-800 font-bold px-3 py-1 rounded-full">13 Anexos Fundamentales</span>
          </div>

          <div class="p-6 grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4 text-xs" id="probatory-cards">
            <!-- Poblar dinámicamente con JS -->
          </div>
        </div>

      </div>
    </section>

  </main>

  <!-- ============================================================== -->
  <!-- MODAL VISOR DE TEXTO JUDICIAL COMPLETO (RESOLUCIONES Y ESCRITOS) -->
  <!-- ============================================================== -->
  <div id="modal-viewer" class="fixed inset-0 bg-slate-900/80 backdrop-blur-sm z-50 hidden flex items-center justify-center p-4">
    <div class="bg-white rounded-2xl shadow-2xl max-w-4xl w-full max-h-[90vh] flex flex-col overflow-hidden border border-slate-200 animate-in fade-in zoom-in-95 duration-150">
      
      <!-- Cabecera del Documento Judicial -->
      <div class="bg-[#0B2240] text-white px-6 py-4 flex items-center justify-between border-b border-amber-500">
        <div class="flex items-center gap-3">
          <i data-lucide="file-check-2" class="w-6 h-6 text-amber-400"></i>
          <div>
            <h3 id="modal-doc-title" class="font-bold text-sm sm:text-base">Resolución Judicial N° 01</h3>
            <p id="modal-doc-subtitle" class="text-xs text-slate-300">Exp. 00174-2019-0-2111-JR-LA-02</p>
          </div>
        </div>
        <button onclick="closeViewerModal()" class="text-slate-300 hover:text-white p-1 rounded-lg">
          <i data-lucide="x" class="w-6 h-6"></i>
        </button>
      </div>

      <!-- Cuerpo del Documento (Tipografía Judicial) -->
      <div class="p-6 sm:p-8 overflow-y-auto space-y-6 text-slate-800 font-judicial leading-relaxed text-sm bg-[#fcfcfc]" id="modal-doc-body">
        <!-- Inyección dinámica -->
      </div>

      <!-- Pie del Modal con Firma y Cierre -->
      <div class="bg-slate-50 border-t border-slate-200 px-6 py-3 flex flex-wrap items-center justify-between gap-3 text-xs">
        <div class="flex items-center gap-2 text-slate-500">
          <i data-lucide="check-circle" class="w-4 h-4 text-emerald-600"></i>
          <span>Documento verificado en el Repositorio Central de Resoluciones del PJ</span>
        </div>
        <button onclick="closeViewerModal()" class="bg-slate-700 hover:bg-slate-800 text-white px-4 py-2 rounded-lg font-medium">
          Cerrar Visor
        </button>
      </div>

    </div>
  </div>

  <!-- ========================================== -->
  <!-- MODAL DE SESIÓN EXPIRADA (7 MINUTOS)       -->
  <!-- ========================================== -->
  <div id="timeout-modal" class="fixed inset-0 bg-slate-950/80 backdrop-blur-sm z-50 hidden flex items-center justify-center p-4">
    <div class="bg-white rounded-2xl p-6 sm:p-8 max-w-md w-full text-center space-y-5 shadow-2xl border border-red-200">
      <div class="w-16 h-16 mx-auto bg-red-100 rounded-full flex items-center justify-center text-red-600">
        <i data-lucide="clock-alert" class="w-8 h-8"></i>
      </div>
      <div>
        <h3 class="text-xl font-bold text-slate-900">Tiempo de Sesión Expirado</h3>
        <p class="text-slate-600 text-xs sm:text-sm mt-2">
          Por motivos de seguridad informática judicial, la sesión inactiva de 7 minutos ha finalizado.
        </p>
      </div>
      <p class="text-xs text-slate-400">Redirigiendo a la pantalla inicial en <span id="countdown-redirect">3</span> segundos...</p>
      <button onclick="forceRedirectNow()" class="w-full bg-[#0B2240] text-white py-2.5 rounded-lg text-sm font-semibold">
        Aceptar y Salir
      </button>
    </div>
  </div>

  <!-- PIE DE PÁGINA INSTITUCIONAL -->
  <footer class="bg-[#0B2240] text-slate-400 text-xs py-3 border-t border-slate-800 text-center">
    <div class="max-w-7xl mx-auto px-4 flex flex-col sm:flex-row items-center justify-between gap-2">
      <div>Poder Judicial del Perú - Corte Superior de Justicia de Puno | Sede Juliaca</div>
      <div class="text-slate-500">Simulador Didáctico de Consulta de Expedientes (EJE)</div>
    </div>
  </footer>

  <!-- ============================================================== -->
  <!-- SCRIPT LOGIC JAVASCRIPT                                         -->
  <!-- ============================================================== -->
  <script>
    // --- VARIABLES DE SESIÓN (7 MINUTOS = 420 SEGUNDOS) ---
    const TOTAL_SESSION_SECONDS = 7 * 60;
    let secondsLeft = TOTAL_SESSION_SECONDS;
    let timerInterval = null;

    // --- BASE DE DATOS DEL EXPEDIENTE 00174-2019-0-2111-JR-LA-02 ---
    const ACTUADOS = [
      {
        num: 1,
        fojas: "Fjs. 1 - 2",
        fecha: "26/06/2019",
        tipo: "Cargo / Carátula",
        desc: "Carátula oficial de ingreso CDG N° 00174-2019-0-2111-JR-LA-02 en Mesa de Partes Única de Juliaca.",
        detalle: {
          titulo: "Carátula Oficial de Ingreso - Mesa de Partes",
          contenido: `
            <div class="border p-4 bg-slate-50 text-xs font-mono space-y-2">
              <p><strong>CÓDIGO DE DIGITALIZACIÓN:</strong> 22019001742111334000038</p>
              <p><strong>EXPEDIENTE:</strong> 00174-2019-0-2111-JR-LA-02</p>
              <p><strong>SEDE:</strong> SAN ROMÁN - JULIACA</p>
              <p><strong>FECHA / HORA INGRESO:</strong> 26/06/2019 11:31:38</p>
              <p><strong>ESPECIALISTA RECEPCIÓN:</strong> IVÁN PALOMINO JARA</p>
              <p><strong>DEMANDANTE:</strong> SUPO QUISPE, ANDRÉS LEONIDAS</p>
              <p><strong>DEMANDADO:</strong> SEGURO SOCIAL DE SALUD - ESSALUD RED ASISTENCIAL JULIACA</p>
              <p><strong>MATERIA:</strong> DESNATURALIZACIÓN DE INTERMEDIACIÓN LABORAL</p>
            </div>
          `
        }
      },
      {
        num: 2,
        fojas: "Fjs. 2 - 26",
        fecha: "26/06/2019",
        tipo: "Escrito N° 01 (Demanda)",
        desc: "Demanda ordinaria laboral interpuesta por Andrés Leonidas Supo Quispe solicitando desnaturalización e incorporación a planillas.",
        detalle: {
          titulo: "Escrito N° 01: Demanda Laboral Ordinaria",
          contenido: `
            <div class="text-right text-xs mb-4"><strong>Sec:</strong> Iván Palomino Jara<br><strong>Exp:</strong> 00174-2019-0-2111-JR-LA-02<br><strong>Escrito:</strong> 01-2019</div>
            <h4 class="font-bold text-center text-base mb-4">SEÑOR JUEZ DEL SEGUNDO JUZGADO CIVIL DE SAN ROMÁN - JULIACA</h4>
            <p><strong>ANDRÉS LEONIDAS SUPO QUISPE</strong>, identificado con DNI N° 02167445, con domicilio real en Av. Manco Cápac N° 964, Juliaca, con Casilla Electrónica SINOE N° 60375, a usted respetuosamente digo:</p>
            <h5 class="font-bold mt-4">I. PETITORIO:</h5>
            <p>Interpongo demanda de <strong>DESNATURALIZACIÓN DE INTERMEDIACIÓN LABORAL</strong> contra el <strong>SEGURO SOCIAL DE SALUD - ESSALUD (RED ASISTENCIAL JULIACA)</strong>, a fin de que:</p>
            <p>1. Se declare la <strong>desnaturalización de la intermediación laboral</strong> mantenida fraudulentamente a través de SILSA desde el 01 de diciembre de 1996.</p>
            <p>2. Se ordene mi <strong>inclusión en el Libro de Planillas de Trabajadores a Plazo Indeterminado</strong> de EsSalud bajo el D. Leg. N° 728, en el cargo de Almacenero de la Unidad de Almacenes.</p>
            <h5 class="font-bold mt-4">II. FUNDAMENTOS DE HECHO:</h5>
            <p>Fui contratado nominalmente por SILSA como operario de limpieza, sin embargo, desde mi ingreso fui asignado permanentemente al Almacén Central de la Red Asistencial Juliaca, realizando recepción, custodia, despacho e inventario con software institucional SAP, bajo subordinación directa del personal jerárquico de EsSalud.</p>
          `
        }
      },
      {
        num: 3,
        fojas: "Fjs. 26 - 96",
        fecha: "26/06/2019",
        tipo: "Medios Probatorios y Anexos",
        desc: "Recaudos de la demanda: constancias SILSA, contratos de intermediación, CAP, MOF, actas de inspección laboral 226-2013 y 567-2013.",
        detalle: {
          titulo: "Recaudos y Anexos Probatorios 1-A al 1-U",
          contenido: `
            <p>Se anexan instrumentalmente 70 fojas con recaudos acreditativos:</p>
            <ul class="list-disc pl-5 space-y-1 text-xs mt-2">
              <li>Constancia SILSA de labores ininterrumpidas desde el 01/12/1996.</li>
              <li>Contratos públicos de servicios de aseo N° 0899P00051 y 1099P00101.</li>
              <li>Actas de Infracción y Requerimiento de la Zona de Trabajo de Juliaca N° 226-2013 y 567-2013 constatando la desnaturalización.</li>
              <li>Manual de Organización y Funciones (MOF) y CAP de EsSalud.</li>
              <li>Sentencia de Amparo estimatoria Exp. N° 0130-2014 por caso análogo en el mismo almacén.</li>
            </ul>
          `
        }
      },
      {
        num: 4,
        fojas: "Fjs. 97",
        fecha: "11/07/2019",
        tipo: "Cargo de Redistribución",
        desc: "Cód. 0000163165-2019-ESC-JR-LA. Redistribución por Res. Adm. N° 232-2019-CE-PJ al Juzgado de Trabajo Zona Norte.",
        detalle: {
          titulo: "Oficio y Cargo de Redistribución",
          contenido: `<p>En cumplimiento a la R.A. N° 232-2019-CE-PJ, se remite el expediente del 2° Juzgado Civil al Despacho del Juzgado de Trabajo - Zona Norte de Juliaca para conocimiento de causas laborales de la Ley 26636.</p>`
        }
      },
      {
        num: 5,
        fojas: "Fjs. 98",
        fecha: "12/07/2019",
        tipo: "Constancia de Secretaría",
        desc: "La Secretaria Judicial Rosario Carlos Villán asume formalmente la tramitación y control de la causa.",
        detalle: {
          titulo: "Razón de Secretaría",
          contenido: `<p>Doy cuenta a fojas 98 que con la fecha se asume funciones de especialista legal de causa por redistribución corporativa. Rosario Carlos Villán - Secretaria Judicial.</p>`
        }
      },
      {
        num: 6,
        fojas: "Fjs. 99",
        fecha: "13/08/2019",
        tipo: "Resolución N° 01",
        desc: "Admisorio provisional: Concede 3 días de plazo al demandante para pronunciarse sobre la comparecencia de SILSA.",
        detalle: {
          titulo: "Resolución N° 01 - Juzgado de Trabajo Zona Norte",
          contenido: `
            <div class="border-b pb-3 mb-3 text-xs">
              <strong>EXPEDIENTE:</strong> 00174-2019-0-2111-JR-LA-02<br>
              <strong>JUEZ:</strong> HUAMÁN ROMERO, GONZALO VÍCTOR<br>
              <strong>ESPECIALISTA:</strong> CARLOS VILLÁN, ROSARIO
            </div>
            <h4 class="font-bold text-center">RESOLUCIÓN NRO. 01</h4>
            <p class="text-xs text-slate-500 text-center mb-4">Juliaca, trece de agosto del año dos mil diecinueve.-</p>
            <p><strong>AUTOS Y VISTOS:</strong> Con la demanda que antecede y anexos presentados; y, <strong>CONSIDERANDO:</strong></p>
            <p><strong>Primero:</strong> Que el accionante solicita la desnaturalización de su intermediación laboral a través de la empresa Services Integrados de Limpieza S.A. (SILSA) y su incorporación a planillas de EsSalud.</p>
            <p><strong>Segundo:</strong> Que, advirtiéndose que en el petitorio no se ha emplazado directamente a la intermediadora SILSA pese a ser parte de la relación tripartita, es necesario fijar la adecuada relación jurídica procesal.</p>
            <p><strong>SE RESUELVE:</strong></p>
            <p>1. Declarar <strong>ADMISIBLE PROVISIONALMENTE</strong> la demanda interpuesta por don ANDRÉS LEONIDAS SUPO QUISPE.</p>
            <p>2. <strong>CONCEDER el plazo de TRES (03) DÍAS</strong> hábiles al accionante a fin de que subsane la omisión de precisar si demanda o no a Servicios Integrados de Limpieza S.A. (SILSA), bajo apercibimiento de rechazo y archivo.</p>
            <div class="mt-6 pt-4 border-t flex justify-between text-xs font-mono">
              <span>Firma: HUAMÁN ROMERO - Juez</span>
              <span>Firma: CARLOS VILLÁN - Especialista</span>
            </div>
          `
        }
      },
      {
        num: 7,
        fojas: "Fjs. 100",
        fecha: "15/08/2019",
        tipo: "Cédula Electrónica",
        desc: "Notificación Electrónica N° 6475-2019 al demandante (Casilla 60375) con la Resolución N° 01.",
        detalle: {
          titulo: "Cédula de Notificación Electrónica SINOE N° 6475-2019",
          contenido: `<p>Se notificó la Resolución N° 01 a la Casilla SINOE N° 60375 correspondiente al abogado defensor Dr. Lino Larico Larico el 15/08/2019 a las 14:22:10 hrs.</p>`
        }
      },
      {
        num: 8,
        fojas: "Fjs. 101 - 104",
        fecha: "21/08/2019",
        tipo: "Escrito N° 02 (Subsanación)",
        desc: "Registro N° 2849-2019. Demandante absuelve traslado señalando que el beneficio y subordinación recaen únicamente en EsSalud.",
        detalle: {
          titulo: "Escrito N° 02: Absuelve Traslado de Resolución N° 01",
          contenido: `
            <p>El demandante sustenta que no acciona contra SILSA debido a que fue la empresa usuaria (EsSalud) quien desnaturalizó el servicio al desviar sus funciones hacia labores de almacenamiento continuo y directo, operando la primacía de la realidad que traslada la relación patronal directamente a EsSalud.</p>
          `
        }
      },
      {
        num: 9,
        fojas: "Fjs. 105",
        fecha: "28/08/2019",
        tipo: "Resolución N° 02",
        desc: "Admite formalmente la demanda en proceso ordinario laboral y corre traslado a EsSalud por diez (10) días.",
        detalle: {
          titulo: "Resolución N° 02 - Admisión a Trámite Ordinario Laboral",
          contenido: `
            <div class="border-b pb-3 mb-3 text-xs">
              <strong>EXPEDIENTE:</strong> 00174-2019-0-2111-JR-LA-02<br>
              <strong>JUEZ:</strong> HUAMÁN ROMERO, GONZALO VÍCTOR<br>
              <strong>ESPECIALISTA:</strong> CARLOS VILLÁN, ROSARIO
            </div>
            <h4 class="font-bold text-center">RESOLUCIÓN NRO. 02</h4>
            <p class="text-xs text-slate-500 text-center mb-4">Juliaca, veintiocho de agosto del dos mil diecinueve.-</p>
            <p><strong>AUTOS Y VISTOS:</strong> Estando al escrito que antecede, cumpliendo con la subsanación requerida; <strong>SE RESUELVE:</strong></p>
            <p>1. Tener por <strong>SUBSANADA</strong> la demanda por parte del actor Andrés Leonidas Supo Quispe.</p>
            <p>2. <strong>ADMITIR A TRÁMITE</strong> la demanda en la vía del <strong>PROCESO ORDINARIO LABORAL</strong> conforme a la Ley N° 26636.</p>
            <p>3. <strong>CORRER TRASLADO</strong> a la demandada RED ASISTENCIAL JULIACA - ESSALUD por el término de <strong>DIEZ (10) DÍAS HÁBILES</strong>, a fin de que conteste la demanda bajo apercibimiento de declararse su rebeldía.</p>
            <div class="mt-6 pt-4 border-t flex justify-end text-xs font-mono">
              <span>Firma Digital: HUAMÁN ROMERO, GONZALO VÍCTOR (04/09/2019)</span>
            </div>
          `
        }
      },
      {
        num: 10,
        fojas: "Fjs. 106",
        fecha: "05/09/2019",
        tipo: "Cédula Electrónica",
        desc: "Notificación N° 63800-2019 de la Resolución N° 02 a la casilla electrónica del actor.",
        detalle: {
          titulo: "Cédula Electrónica SINOE N° 63800-2019",
          contenido: `<p>Notificación de la Resolución N° 02 al actor a Casilla 60375. Diligenciada válidamente.</p>`
        }
      },
      {
        num: 11,
        fojas: "Fjs. 107",
        fecha: "10/09/2019",
        tipo: "Cédula Física N° 7304-2019",
        desc: "Emplazamiento físico a EsSalud en su domicilio institucional (Av. Santos Chocano S/N, Juliaca) con demanda y recaudos.",
        detalle: {
          titulo: "Cédula de Notificación Física N° 7304-2019",
          contenido: `<p>Diligencia en Av. José Santos Chocano S/N, La Capilla, Juliaca. Emplazamiento formal a EsSalud con copias de traslado de demanda y Res. N° 02.</p>`
        }
      },
      {
        num: 12,
        fojas: "Fjs. 108 - 124+",
        fecha: "25/09/2019",
        tipo: "Escrito N° 01 (Demandada)",
        desc: "Registro N° 3461-2019. EsSalud se apersona con su apoderado Hernán Rolando López Alférez, señala casilla 59629 y contesta la demanda.",
        detalle: {
          titulo: "Escrito de Contestación de Demanda - EsSalud",
          contenido: `
            <div class="text-right text-xs mb-4"><strong>Registro:</strong> 3461-2019<br><strong>Casilla SINOE:</strong> 59629</div>
            <p><strong>HERNÁN ROLANDO LÓPEZ ALFÉREZ</strong>, apoderado del Seguro Social de Salud - EsSalud Red Asistencial Juliaca:</p>
            <p>Contesta la demanda solicitando sea declarada <strong>INFUNDADA Y/O IMPROCEDENTE</strong> bajo los siguientes extremos:</p>
            <ul class="list-disc pl-5 text-xs space-y-1 mt-2">
              <li>El accionante mantenía contrato civil y laboral exclusivo con la empresa contratista SILSA.</li>
              <li>En los instrumentos de gestión interna de EsSalud (CAP y MOF) no existe vacante presupuestada para el ingreso del actor.</li>
              <li>No concurren de manera copulativa los elementos esenciales del contrato directo con EsSalud.</li>
            </ul>
          `
        }
      }
    ];

    const RECAUDOS = [
      { id: "1-A", tit: "Copia Legalizada DNI N° 02167445", desc: "Acredita identidad del accionante Andrés Leonidas Supo Quispe." },
      { id: "1-B", tit: "Constancia de Trabajo SILSA (14/06/2018)", desc: "Certifica servicios ininterrumpidos en Red Juliaca desde el 01/12/1996." },
      { id: "1-C", tit: "Cuadro de Asignación de Personal (CAP)", desc: "Estructura orgánica de la Unidad de Almacenes de EsSalud Juliaca." },
      { id: "1-D", tit: "Manual de Org. y Funciones (MOF)", desc: "Funciones institucionales estructurales de la plaza de Almacenero." },
      { id: "1-E", tit: "Contratos de Servicios de Limpieza SILSA", desc: "Concursos Públicos N° 0899P00051 y 1099P00101 sobre intermediación." },
      { id: "1-F", tit: "Padrón Censo de Inspección Laboral", desc: "Diligencia censal in situ de trabajadores por la Zona de Trabajo Juliaca." },
      { id: "1-G", tit: "Acta de Infracción N° 226-2013-ZTPE-JUL", desc: "Sanción impuesta por el inspector Pedro M. Toledo Calero contra SILSA." },
      { id: "1-H", tit: "Acta de Requerimiento Exp. N° 567-2013", desc: "Orden formal a EsSalud de incorporar al actor a planillas D. Leg. 728." },
      { id: "1-I", tit: "Carta N° 056-OCI-ESSALUD-2012", desc: "Control Interno alerta que personal SILSA asume labores de almacenes." },
      { id: "1-LL", tit: "Memorandos N° 148, 152 y 154-GRAJUL-2013", desc: "Gerente dispone rotaciones urgentes ante las visitas inspectivas del MTPE." },
      { id: "1-Ñ", tit: "Certificados de Capacitación SAP R/3", desc: "Cursos institucionales emitidos por EsSalud al actor sobre almacenaje." },
      { id: "1-Q", tit: "Cartas de Felicitación Funcional", desc: "Reconocimientos por desempeño expedidos por jefes de Almacén EsSalud." },
      { id: "1-U", tit: "Sentencia de Vista Exp. 0130-2014", desc: "Res. N° 26 (25/04/2016) estimatoria en idéntico caso (Everth Quispe Durand)." }
    ];

    // --- NAVEGACIÓN ENTRE PANTALLAS ---
    function showScreen(screenId) {
      document.querySelectorAll('.screen').forEach(s => s.classList.remove('active'));
      const target = document.getElementById(screenId);
      if (target) target.classList.add('active');
      window.scrollTo(0, 0);
    }

    // Pantalla 0 -> Pantalla 1 -> Pantalla 2
    function goToScreen1() {
      showScreen('screen-1');
      startSessionTimer();
      let p = 0;
      const bar = document.getElementById('p1-progress');
      bar.style.width = '0%';
      const intv = setInterval(() => {
        p += 5;
        bar.style.width = p + '%';
        if (p >= 100) {
          clearInterval(intv);
          setTimeout(() => {
            showScreen('screen-2');
            lucide.createIcons();
          }, 300);
        }
      }, 50); // ~1.2 segundos
    }

    // Pantalla 2: Manejo de Vistas y Menú Estatal
    function showNavTab(tabName) {
      const temis = document.getElementById('temis-view');
      const info = document.getElementById('info-modal-content');
      const search = document.getElementById('search-view');
      const title = document.getElementById('info-title');
      const body = document.getElementById('info-body');

      search.classList.add('hidden');

      if (tabName === 'inicio') {
        info.classList.add('hidden');
        temis.classList.remove('hidden');
        return;
      }

      temis.classList.add('hidden');
      info.classList.remove('hidden');

      const infoData = {
        mision: {
          t: "Misión del Poder Judicial",
          b: "<p>Administrar Justicia a través de sus órganos jurisdiccionales, con arreglo a la Constitución y a las leyes, garantizando la seguridad jurídica, la tutela jurisdiccional efectiva y el Estado de Derecho en todo el territorio de la República del Perú.</p>"
        },
        vision: {
          t: "Visión Institucional",
          b: "<p>Ser un Poder del Estado moderno, autónomo, eficiente y transparente, reconocido por la sociedad peruana por brindar una justicia célere, confiable e inclusiva con estándares de calidad y ética.</p>"
        },
        transparencia: {
          t: "Portal de Transparencia Estándar",
          b: "<p>Acceso a la información judicial pública, compras estatales, resoluciones administrativas, presupuesto asignado a la Corte Superior de Justicia de Puno y cuadro de personal jurisdiccional.</p>"
        },
        contactanos: {
          t: "Atención al Ciudadano y Sedes Judiciales",
          b: "<p><strong>Sede Central Juliaca:</strong> Jr. Apurímac / Pumacahua, San Román, Puno.<br><strong>Módulo Laboral Zona Norte:</strong> Jr. Mariano Núñez N° 139, Juliaca.<br><strong>Central Telefónica:</strong> (051) 507000.</p>"
        }
      };

      if (infoData[tabName]) {
        title.innerText = infoData[tabName].t;
        body.innerHTML = infoData[tabName].b;
      }
    }

    function closeInfoView() {
      document.getElementById('info-modal-content').classList.add('hidden');
      document.getElementById('temis-view').classList.remove('hidden');
    }

    function activateSearch() {
      document.getElementById('temis-view').classList.add('hidden');
      document.getElementById('info-modal-content').classList.add('hidden');
      document.getElementById('search-view').classList.remove('hidden');
      generateCaptcha();
    }

    function cancelSearch() {
      document.getElementById('search-view').classList.add('hidden');
      document.getElementById('temis-view').classList.remove('hidden');
    }

    // CAPTCHA Logic
    let currentCaptcha = "";
    function generateCaptcha() {
      const chars = "ABCDEFGHJKLMNPQRSTUVWXYZ23456789";
      let code = "";
      for (let i = 0; i < 5; i++) {
        code += chars.charAt(Math.floor(Math.random() * chars.length));
      }
      currentCaptcha = code;
      const el = document.getElementById('captcha-display');
      if (el) el.innerText = code;
      const inp = document.getElementById('captcha-input');
      if (inp) inp.value = "";
      document.getElementById('captcha-error').classList.add('hidden');
    }

    function validateCaptcha() {
      const val = document.getElementById('captcha-input').value.trim().toUpperCase();
      if (val === currentCaptcha) {
        document.getElementById('captcha-step').classList.add('hidden');
        document.getElementById('query-step').classList.remove('hidden');
      } else {
        document.getElementById('captcha-error').classList.remove('hidden');
        generateCaptcha();
      }
    }

    function switchSearchTab(mode) {
      const btnCode = document.getElementById('tab-btn-code');
      const btnParty = document.getElementById('tab-btn-party');
      const formCode = document.getElementById('form-by-code');
      const formParty = document.getElementById('form-by-party');

      if (mode === 'code') {
        btnCode.className = "py-2.5 px-4 text-[#0B2240] border-b-2 border-[#0B2240] font-bold";
        btnParty.className = "py-2.5 px-4 text-slate-500 hover:text-slate-700 border-b-2 border-transparent";
        formCode.classList.remove('hidden');
        formParty.classList.add('hidden');
      } else {
        btnParty.className = "py-2.5 px-4 text-[#0B2240] border-b-2 border-[#0B2240] font-bold";
        btnCode.className = "py-2.5 px-4 text-slate-500 hover:text-slate-700 border-b-2 border-transparent";
        formParty.classList.remove('hidden');
        formCode.classList.add('hidden');
      }
    }

    function autofillCode() {
      document.getElementById('in-correlativo').value = "00174";
      document.getElementById('in-ano').value = "2019";
      document.getElementById('in-cuaderno').value = "0";
      document.getElementById('in-distrito').value = "2111";
      document.getElementById('in-organo').value = "JR-LA";
      document.getElementById('in-esp').value = "02";
    }

    function setParty(name) {
      document.getElementById('in-party-name').value = name;
    }

    // Pantalla 2 -> Pantalla 3 -> Pantalla 4
    function executeSearch() {
      showScreen('screen-3');
      let p = 0;
      const bar = document.getElementById('p3-progress');
      bar.style.width = '0%';
      const intv = setInterval(() => {
        p += 5;
        bar.style.width = p + '%';
        if (p >= 100) {
          clearInterval(intv);
          setTimeout(() => {
            renderDossier();
            showScreen('screen-4');
            lucide.createIcons();
          }, 300);
        }
      }, 50); // ~1.2 segundos
    }

    function returnToSearch() {
      showScreen('screen-2');
      activateSearch();
    }

    // --- RENDERIZADO DEL EXPEDIENTE EN PANTALLA 4 ---
    function renderDossier() {
      // 1. Renderizar tabla de actuados
      const tbody = document.getElementById('timeline-rows');
      tbody.innerHTML = '';
      ACTUADOS.forEach(act => {
        const tr = document.createElement('tr');
        tr.className = "hover:bg-slate-50 transition border-b border-slate-100";
        tr.innerHTML = `
          <td class="py-3 px-4 text-center font-bold text-slate-700">${act.num.toString().padStart(2, '0')}</td>
          <td class="py-3 px-3 font-mono font-medium text-slate-600">${act.fojas}</td>
          <td class="py-3 px-3 text-slate-500 whitespace-nowrap">${act.fecha}</td>
          <td class="py-3 px-4 font-bold text-[#0B2240]">${act.tipo}</td>
          <td class="py-3 px-4 text-slate-600 leading-relaxed">${act.desc}</td>
          <td class="py-3 px-4 text-center">
            <button onclick="openViewerModal(${act.num})" class="px-2.5 py-1.5 bg-[#0B2240] hover:bg-[#123157] text-white rounded text-[11px] font-semibold flex items-center justify-center gap-1 mx-auto shadow-sm">
              <i data-lucide="eye" class="w-3.5 h-3.5"></i>
              <span>Ver Fojas</span>
            </button>
          </td>
        `;
        tbody.appendChild(tr);
      });

      // 2. Renderizar tarjetas de medios probatorios
      const pGrid = document.getElementById('probatory-cards');
      pGrid.innerHTML = '';
      RECAUDOS.forEach(r => {
        const card = document.createElement('div');
        card.className = "p-3 bg-slate-50 hover:bg-white rounded-lg border border-slate-200 transition shadow-xs hover:shadow-sm";
        card.innerHTML = `
          <div class="flex items-center gap-2 mb-1">
            <span class="bg-amber-500 text-slate-950 font-bold px-1.5 py-0.5 rounded text-[10px] font-mono">Anexo ${r.id}</span>
            <strong class="text-[#0B2240] text-xs truncate">${r.tit}</strong>
          </div>
          <p class="text-slate-600 text-[11px] leading-snug">${r.desc}</p>
        `;
        pGrid.appendChild(card);
      });
    }

    // --- MODAL DE VISUALIZACIÓN DE FOJAS ---
    function openViewerModal(actNum) {
      const actuado = ACTUADOS.find(a => a.num === actNum);
      if (!actuado) return;

      document.getElementById('modal-doc-title').innerText = actuado.detalle.titulo;
      document.getElementById('modal-doc-subtitle').innerText = `${actuado.tipo} | ${actuado.fojas} | Fecha: ${actuado.fecha}`;
      document.getElementById('modal-doc-body').innerHTML = actuado.detalle.contenido;
      
      document.getElementById('modal-viewer').classList.remove('hidden');
      lucide.createIcons();
    }

    function closeViewerModal() {
      document.getElementById('modal-viewer').classList.add('hidden');
    }

    // --- CRONÓMETRO DE 7 MINUTOS (420 S) ---
    function startSessionTimer() {
      if (timerInterval) clearInterval(timerInterval);
      secondsLeft = TOTAL_SESSION_SECONDS;
      updateTimerDisplay();

      timerInterval = setInterval(() => {
        secondsLeft--;
        updateTimerDisplay();

        if (secondsLeft <= 0) {
          clearInterval(timerInterval);
          handleSessionTimeout();
        }
      }, 1000);
    }

    function resetTimer() {
      secondsLeft = TOTAL_SESSION_SECONDS;
      updateTimerDisplay();
    }

    function updateTimerDisplay() {
      const minutes = Math.floor(secondsLeft / 60);
      const seconds = secondsLeft % 60;
      const formatted = `${minutes.toString().padStart(2, '0')}:${seconds.toString().padStart(2, '0')}`;
      
      const timerSpan = document.getElementById('session-timer');
      const timerBadge = document.getElementById('session-timer-badge');
      if (timerSpan) timerSpan.innerText = formatted;

      // Alerta a menos de 1 minuto
      if (secondsLeft <= 60 && timerBadge) {
        timerBadge.classList.add('timer-warning');
      } else if (timerBadge) {
        timerBadge.classList.remove('timer-warning');
      }
    }

    function handleSessionTimeout() {
      closeViewerModal();
      document.getElementById('timeout-modal').classList.remove('hidden');
      lucide.createIcons();

      let cd = 3;
      const countEl = document.getElementById('countdown-redirect');
      const cdIntv = setInterval(() => {
        cd--;
        if (countEl) countEl.innerText = cd;
        if (cd <= 0) {
          clearInterval(cdIntv);
          forceRedirectNow();
        }
      }, 1000);
    }

    function forceRedirectNow() {
      document.getElementById('timeout-modal').classList.add('hidden');
      // Resetear formularios y vistas
      document.getElementById('captcha-step').classList.remove('hidden');
      document.getElementById('query-step').classList.add('hidden');
      document.getElementById('search-view').classList.add('hidden');
      document.getElementById('info-modal-content').classList.add('hidden');
      document.getElementById('temis-view').classList.remove('hidden');
      showScreen('screen-0');
      lucide.createIcons();
    }

    // Inicializar iconos de Lucide al cargar
    document.addEventListener('DOMContentLoaded', () => {
      lucide.createIcons();
    });
  </script>
</body>
</html>
