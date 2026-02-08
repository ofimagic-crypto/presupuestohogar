<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Presupuesto de Hogar Pro</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <style>
        .btn-card { @apply bg-white p-6 rounded-3xl shadow-lg flex flex-col items-center justify-center transition-all hover:shadow-2xl active:scale-95 border-b-8; }
        .input-financial { @apply border-2 border-gray-200 p-3 rounded-xl focus:border-blue-500 outline-none w-full text-lg; }
        .badge { @apply px-2 py-1 rounded text-xs font-bold uppercase; }
    </style>
</head>
<body class="bg-slate-50 min-h-screen pb-10">

    <div id="login-screen" class="flex items-center justify-center h-screen p-4">
        <div class="bg-white p-8 rounded-[2rem] shadow-2xl w-full max-w-md text-center border-t-8 border-blue-900">
            <i class="fas fa-wallet text-5xl text-blue-900 mb-4"></i>
            <h1 class="text-3xl font-black text-gray-800 mb-2">Presupuesto de Hogar</h1>
            <p class="text-gray-500 mb-6 italic">Gestiona tus finanzas de manera inteligente</p>
            <input id="user" type="text" placeholder="Usuario" class="input-financial mb-3">
            <input id="pass" type="password" placeholder="Contraseña" class="input-financial mb-6">
            <button onclick="handleLogin()" class="w-full bg-blue-900 text-white p-4 rounded-2xl font-bold text-xl">Entrar / Registrarse</button>
            <p class="text-[10px] text-gray-400 mt-6 uppercase tracking-widest">Tus datos se guardan solo en este dispositivo</p>
        </div>
    </div>

    <div id="app-screen" class="hidden">
        <nav class="bg-blue-900 text-white p-4 sticky top-0 z-50 shadow-md">
            <div class="max-w-4xl mx-auto flex justify-between items-center">
                <span class="font-bold tracking-tight"><i class="fas fa-university mr-2"></i>MI PANEL FINANCIERO</span>
                <button onclick="location.reload()" class="bg-blue-800 px-4 py-2 rounded-lg text-sm"><i class="fas fa-sign-out-alt"></i></button>
            </div>
        </nav>

        <main class="p-4 max-w-4xl mx-auto">
            <div class="grid grid-cols-2 gap-4 mb-6">
                <div class="bg-white p-4 rounded-2xl shadow-sm border-l-4 border-emerald-500">
                    <p class="text-xs text-gray-500 font-bold uppercase">Total Ingresos</p>
                    <p id="top-ingresos" class="text-xl font-black text-emerald-600">$0,00</p>
                </div>
                <div class="bg-white p-4 rounded-2xl shadow-sm border-l-4 border-red-500">
                    <p class="text-xs text-gray-500 font-bold uppercase">Total Gastos</p>
                    <p id="top-gastos" class="text-xl font-black text-red-600">$0,00</p>
                </div>
            </div>

            <div id="main-menu" class="grid grid-cols-2 gap-4 mb-8">
                <button onclick="renderIngresos()" class="btn-card border-emerald-500">
                    <i class="fas fa-chart-line text-3xl text-emerald-500 mb-2"></i>
                    <span class="font-bold text-gray-700">Ingresos</span>
                </button>
                <button onclick="renderGastos()" class="btn-card border-red-500">
                    <i class="fas fa-receipt text-3xl text-red-500 mb-2"></i>
                    <span class="font-bold text-gray-700">Gastos</span>
                </button>
                <button onclick="renderListado()" class="btn-card border-blue-500">
                    <i class="fas fa-list-ul text-3xl text-blue-500 mb-2"></i>
                    <span class="font-bold text-gray-700">Listado</span>
                </button>
                <button onclick="renderClasificar()" class="btn-card border-amber-500">
                    <i class="fas fa-filter text-3xl text-amber-500 mb-2"></i>
                    <span class="font-bold text-gray-700">Clasificar</span>
                </button>
                <button onclick="renderAjuste()" class="btn-card border-purple-500 col-span-2">
                    <i class="fas fa-magic text-3xl text-purple-500 mb-2"></i>
                    <span class="font-bold text-gray-700 uppercase tracking-widest">Propuesta de Ajuste</span>
                </button>
                <button onclick="renderProyeccion()" class="btn-card border-cyan-500 col-span-2">
                    <i class="fas fa-calendar-alt text-3xl text-cyan-500 mb-2"></i>
                    <span class="font-bold text-gray-700 uppercase tracking-widest">Proyección 3 Meses</span>
                </button>
            </div>

            <div id="content-view" class="bg-white rounded-[2rem] shadow-xl p-6 hidden">
                </div>
        </main>
    </div>

    <script>
        let db = JSON.parse(localStorage.getItem('hogar_db')) || { users: {} };
        let currentU = null;

        const fmt = (val) => new Intl.NumberFormat('de-DE', { minimumFractionDigits: 2, maximumFractionDigits: 2 }).format(val);

        function handleLogin() {
            const u = document.getElementById('user').value.trim();
            const p = document.getElementById('pass').value.trim();
            if(!u || !p) return alert("Ingresa datos");

            if(!db.users[u]) {
                db.users[u] = { pass: p, ingresos: [], gastos: [], ajustes: {} };
                alert("Usuario creado localmente [cite: 4]");
            } else if(db.users[u].pass !== p) return alert("Error");

            currentU = u;
            localStorage.setItem('hogar_db', JSON.stringify(db));
            document.getElementById('login-screen').classList.add('hidden');
            document.getElementById('app-screen').classList.remove('hidden');
            updateDashboard();
        }

        function updateDashboard() {
            const data = db.users[currentU];
            const tIng = data.ingresos.reduce((a, b) => a + parseFloat(b.valor), 0);
            const tGas = data.gastos.reduce((a, b) => a + parseFloat(b.valor), 0);
            document.getElementById('top-ingresos').innerText = `$ ${fmt(tIng)}`;
            document.getElementById('top-gastos').innerText = `$ ${fmt(tGas)}`;
        }

        function renderIngresos() {
            const cv = document.getElementById('content-view');
            cv.classList.remove('hidden');
            cv.innerHTML = `
                <div class="flex justify-between items-center mb-6">
                    <h2 class="text-2xl font-black text-gray-800 uppercase">Ingresos</h2>
                    <button onclick="hideView()" class="text-gray-400 text-2xl">&times;</button>
                </div>
                <div class="space-y-4">
                    <input id="i-det" placeholder="Detalle (Max 30 carac.)" maxlength="30" class="input-financial">
                    <input id="i-val" type="number" placeholder="Valor (0.00)" class="input-financial">
                    <button onclick="addIngreso()" class="w-full bg-emerald-600 text-white p-4 rounded-xl font-bold">GUARDAR INGRESO</button>
                </div>
                <div class="mt-8" id="ing-list"></div>
            `;
            listIngresos();
        }

        function addIngreso() {
            const det = document.getElementById('i-det').value;
            const val = document.getElementById('i-val').value;
            if(!det || !val) return;
            db.users[currentU].ingresos.push({ det, valor: val, id: Date.now() });
            localStorage.setItem('hogar_db', JSON.stringify(db));
            updateDashboard();
            renderIngresos();
        }

        function listIngresos() {
            const list = document.getElementById('ing-list');
            list.innerHTML = db.users[currentU].ingresos.map(i => `
                <div class="flex justify-between border-b p-3">
                    <span class="font-medium">${i.det}</span>
                    <span class="font-bold text-emerald-600">$ ${fmt(i.valor)}</span>
                </div>
            `).join('');
        }

        function renderGastos() {
            const cv = document.getElementById('content-view');
            cv.classList.remove('hidden');
            cv.innerHTML = `
                <div class="flex justify-between items-center mb-6">
                    <h2 class="text-2xl font-black text-gray-800 uppercase">Gastos</h2>
                    <button onclick="hideView()" class="text-gray-400 text-2xl">&times;</button>
                </div>
                <div class="space-y-3 mb-6 bg-slate-50 p-4 rounded-2xl">
                    <input id="g-det" placeholder="Detalle Gasto" class="input-financial">
                    <input id="g-val" type="number" placeholder="Valor" class="input-financial">
                    <select id="g-pri" class="input-financial">
                        <option value="superfluo">Superfluo (Eliminable) [cite: 10]</option>
                        <option value="secundario">Secundario (Ajustable)</option>
                        <option value="basico">Básico (Esencial)</option>
                    </select>
                    <button onclick="addGasto()" class="w-full bg-red-500 text-white p-4 rounded-xl font-bold">REGISTRAR GASTO</button>
                </div>
                <div id="gas-list" class="space-y-2"></div>
            `;
            listGastos();
        }

        function addGasto() {
            const d = document.getElementById('g-det').value;
            const v = document.getElementById('g-val').value;
            const p = document.getElementById('g-pri').value;
            if(!d || !v) return;
            db.users[currentU].gastos.push({ det: d, valor: v, prioridad: p, fecha: new Date().toLocaleDateString(), id: Date.now() });
            localStorage.setItem('hogar_db', JSON.stringify(db));
            updateDashboard();
            renderGastos();
        }

        function listGastos() {
            const list = document.getElementById('gas-list');
            list.innerHTML = db.users[currentU].gastos.map(g => `
                <div class="flex justify-between items-center bg-white p-3 border rounded-xl shadow-sm">
                    <div class="flex flex-col">
                        <span class="font-bold text-gray-700">${g.det}</span>
                        <span class="badge ${g.prioridad === 'superfluo' ? 'bg-red-100 text-red-600' : 'bg-blue-100 text-blue-600'} w-fit">${g.prioridad}</span>
                    </div>
                    <span class="font-black">$ ${fmt(g.valor)}</span>
                </div>
            `).join('');
        }

        function renderAjuste() {
            const data = db.users[currentU];
            const cv = document.getElementById('content-view');
            cv.classList.remove('hidden');
            
            const renderBlock = (title, type, color) => {
                const filtered = data.gastos.filter(g => g.prioridad === type);
                const total = filtered.reduce((a,b) => a + parseFloat(b.valor), 0);
                return `
                    <div class="mb-6 border-l-8 p-4 bg-white shadow-md rounded-r-2xl border-${color}">
                        <h4 class="font-black text-gray-800 mb-4 uppercase">${title} - Total: $ ${fmt(total)}</h4>
                        ${filtered.map(g => `
                            <div class="flex justify-between items-center text-sm mb-2">
                                <span>${g.det}</span>
                                <div class="flex items-center gap-2">
                                    <span class="text-gray-400 line-through">$ ${fmt(g.valor)}</span>
                                    <input type="number" placeholder="Ajuste" class="w-20 p-1 border rounded text-right" 
                                           onchange="saveAjuste(${g.id}, this.value)">
                                </div>
                            </div>
                        `).join('')}
                    </div>
                `;
            };

            cv.innerHTML = `
                <div class="flex justify-between items-center mb-6">
                    <h2 class="text-2xl font-black text-purple-600 uppercase">Propuesta de Ajuste [cite: 10, 20]</h2>
                    <button onclick="hideView()" class="text-gray-400 text-2xl">&times;</button>
                </div>
                ${renderBlock('1. Superfluos (Recortar ya)', 'superfluo', 'red-500')}
                ${renderBlock('2. Secundarios', 'secundario', 'amber-500')}
                ${renderBlock('3. Básicos', 'basico', 'emerald-500')}
            `;
        }

        function renderProyeccion() {
            const cv = document.getElementById('content-view');
            cv.classList.remove('hidden');
            const data = db.users[currentU];
            const baseIng = data.ingresos.reduce((a, b) => a + parseFloat(b.valor), 0);
            const baseGas = data.gastos.reduce((a, b) => a + parseFloat(b.valor), 0);
            
            let html = `<div class="flex justify-between items-center mb-6"><h2 class="text-2xl font-black text-cyan-600 uppercase font-serif tracking-tighter">Proyección 3 Meses [cite: 23]</h2><button onclick="hideView()" class="text-gray-400 text-2xl">&times;</button></div><div class="grid grid-cols-3 gap-2">`;
            
            let saldoArrastrado = 0; // 
            for(let i=1; i<=3; i++) {
                let totalMes = (baseIng + saldoArrastrado) - baseGas;
                html += `
                    <div class="bg-white p-3 rounded-xl border-t-4 border-cyan-500 shadow text-center">
                        <p class="font-bold text-xs">MES ${i}</p>
                        <p class="text-sm ${totalMes < 0 ? 'text-red-600' : 'text-emerald-600'} font-black">$ ${fmt(totalMes)}</p>
                        ${totalMes < 0 ? '<p class="text-[8px] text-red-400 font-bold">TRABAJAR AJUSTE [cite: 25]</p>' : ''}
                    </div>
                `;
                saldoArrastrado = totalMes > 0 ? totalMes : 0; // Saldo final como ingreso del siguiente 
            }
            html += `</div>`;
            cv.innerHTML = html;
        }

        function hideView() { document.getElementById('content-view').classList.add('hidden'); }
        function saveAjuste(id, val) { 
            db.users[currentU].ajustes[id] = val; 
            localStorage.setItem('hogar_db', JSON.stringify(db));
        }

    </script>
</body>
</html>
