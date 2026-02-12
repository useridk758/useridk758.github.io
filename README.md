<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>useridk758 v4 | Arcade</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap" rel="stylesheet">
    <style>
        body { font-family: 'Inter', sans-serif; background-color: #050505; color: white; margin: 0; }
        .bento-card { background: #0f0f0f; border: 1px solid #1f1f1f; border-radius: 24px; }
        .proxy-input { 
            background: #0a0a0a; border: 1px solid #333; outline: none; transition: all 0.3s;
        }
        .proxy-input:focus { border-color: #3b82f6; box-shadow: 0 0 20px rgba(59, 130, 246, 0.4); }
        /* This makes the iframe look like a browser window */
        .window-top { background: #1a1a1a; border-radius: 12px 12px 0 0; border: 1px solid #333; }
    </style>
</head>
<body class="flex flex-col items-center min-h-screen p-6">

    <nav class="mt-4 bg-[#0f0f0f] border border-[#1f1f1f] rounded-full px-8 py-4 flex gap-8 mb-16 shadow-2xl">
        <div class="cursor-pointer hover:scale-125 transition">🐸</div>
        <div class="cursor-pointer hover:scale-125 transition text-gray-400 hover:text-white">🎮</div>
        <div class="cursor-pointer hover:scale-125 transition text-gray-400 hover:text-white">📁</div>
    </nav>

    <h1 class="text-5xl font-black mb-10 tracking-tighter italic">frogie's arcade v4</h1>

    <div class="flex gap-4 mb-10">
        <div onclick="launchProxy('https://www.google.com/search?igu=1')" class="w-14 h-14 bento-card flex items-center justify-center text-2xl cursor-pointer hover:bg-blue-600 transition">🔍</div>
        <div onclick="launchProxy('https://www.bing.com')" class="w-14 h-14 bento-card flex items-center justify-center text-2xl cursor-pointer hover:bg-green-600 transition">🅱️</div>
        <div onclick="launchProxy('https://duckduckgo.com')" class="w-14 h-14 bento-card flex items-center justify-center text-2xl cursor-pointer hover:bg-orange-600 transition">🦆</div>
    </div>

    <div class="w-full max-w-2xl mb-12">
        <form id="proxyForm" class="relative group">
            <input 
                type="text" 
                id="urlInput"
                placeholder="search anything or enter URL..." 
                class="w-full proxy-input py-5 px-8 rounded-full text-center text-xl shadow-inner text-white"
            >
            <button type="submit" class="absolute right-4 top-3 bg-white text-black px-4 py-2 rounded-full font-bold hover:bg-blue-500 hover:text-white transition">Go</button>
        </form>
    </div>

    <div id="resultArea" class="hidden w-full max-w-6xl mt-4">
        <div class="window-top p-3 flex justify-between items-center px-6">
            <div class="flex gap-2">
                <div class="w-3 h-3 bg-red-500 rounded-full cursor-pointer" onclick="closeFrame()"></div>
                <div class="w-3 h-3 bg-yellow-500 rounded-full"></div>
                <div class="w-3 h-3 bg-green-500 rounded-full"></div>
            </div>
            <span id="urlDisplay" class="text-xs text-gray-400 font-mono italic"></span>
            <div class="w-10"></div>
        </div>
        <div class="bento-card rounded-t-none border-t-0 h-[75vh] overflow-hidden bg-white">
            <iframe id="proxyFrame" src="" class="w-full h-full border-none"></iframe>
        </div>
        <p class="text-center text-gray-500 text-[10px] mt-4 uppercase tracking-widest">Powered by useridk758 • Secure Tunnel Active</p>
    </div>

    <script>
        const form = document.getElementById('proxyForm');
        const input = document.getElementById('urlInput');
        const resultArea = document.getElementById('resultArea');
        const frame = document.getElementById('proxyFrame');
        const urlDisplay = document.getElementById('urlDisplay');

        form.addEventListener('submit', (e) => {
            e.preventDefault();
            let val = input.value.trim();
            if (!val) return;

            let targetUrl = val;

            // Logic: If it's not a URL, use Google Search (with frame-friendly parameter)
            if (!val.includes('.') || val.includes(' ')) {
                targetUrl = `https://www.google.com/search?q=${encodeURIComponent(val)}&igu=1`;
            } else {
                if (!val.startsWith('http')) {
                    targetUrl = 'https://' + val;
                }
            }

            launchProxy(targetUrl);
        });

        function launchProxy(url) {
            urlDisplay.innerText = url;
            frame.src = url;
            resultArea.classList.remove('hidden');
            // Auto-scroll to window
            window.scrollTo({ top: resultArea.offsetTop - 50, behavior: 'smooth' });
        }

        function closeFrame() {
            resultArea.classList.add('hidden');
            frame.src = "";
        }
    </script>
</body>
</html>
