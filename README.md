<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>useridk758 v4</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;700;900&display=swap" rel="stylesheet">
    <style>
        body { font-family: 'Inter', sans-serif; background-color: #050505; color: white; margin: 0; overflow-x: hidden; }
        .bento-card { background: #0f0f0f; border: 1px solid #1f1f1f; border-radius: 20px; }
        .proxy-input { 
            background: #0a0a0a; border: 1px solid #333; outline: none; transition: all 0.3s;
        }
        .proxy-input:focus { border-color: #3b82f6; box-shadow: 0 0 20px rgba(59, 130, 246, 0.4); }
        .browser-window { border: 1px solid #333; border-radius: 15px; overflow: hidden; background: #000; }
        .browser-bar { background: #1a1a1a; padding: 10px 20px; display: flex; align-items: center; justify-content: space-between; }
    </style>
</head>
<body class="flex flex-col items-center min-h-screen p-4">

    <nav class="mt-6 bg-[#0f0f0f] border border-[#1f1f1f] rounded-full px-6 py-3 flex gap-6 mb-12 shadow-xl">
        <div class="cursor-pointer hover:scale-110 transition">🐸</div>
        <div class="cursor-pointer hover:scale-110 transition text-gray-500 hover:text-white">🎮</div>
        <div class="cursor-pointer hover:scale-110 transition text-gray-500 hover:text-white">🛠️</div>
    </nav>

    <div class="text-center mb-8">
        <h1 class="text-5xl font-black italic tracking-tighter text-white">frogie's arcade v4</h1>
        <p class="text-gray-500 text-sm mt-2 uppercase tracking-widest">The Ultimate Web Proxy</p>
    </div>

    <div class="flex gap-3 mb-10">
        <div onclick="launch('https://www.google.com/search?igu=1')" class="w-12 h-12 bento-card flex items-center justify-center cursor-pointer hover:bg-blue-600 transition">🔍</div>
        <div onclick="launch('https://www.bing.com')" class="w-12 h-12 bento-card flex items-center justify-center cursor-pointer hover:bg-teal-600 transition">🅱️</div>
        <div onclick="launch('https://duckduckgo.com')" class="w-12 h-12 bento-card flex items-center justify-center cursor-pointer hover:bg-orange-600 transition">🦆</div>
    </div>

    <div class="w-full max-w-2xl mb-12">
        <form id="proxyForm" class="relative group">
            <input 
                type="text" 
                id="urlInput"
                placeholder="Search or enter URL (e.g. tiktok.com)" 
                class="w-full proxy-input py-4 px-8 rounded-full text-center text-lg text-white"
            >
            <button type="submit" class="absolute right-3 top-2 bg-white text-black px-5 py-2 rounded-full font-bold hover:bg-blue-500 hover:text-white transition">Go</button>
        </form>
    </div>

    <div id="resultArea" class="hidden w-full max-w-6xl animate-in fade-in duration-500">
        <div class="browser-window shadow-2xl">
            <div class="browser-bar">
                <div class="flex gap-2">
                    <div onclick="closeFrame()" class="w-3 h-3 bg-red-500 rounded-full cursor-pointer"></div>
                    <div class="w-3 h-3 bg-yellow-500 rounded-full"></div>
                    <div class="w-3 h-3 bg-green-500 rounded-full"></div>
                </div>
                <span id="urlTitle" class="text-xs text-gray-400 font-mono truncate max-w-xs"></span>
                <button onclick="popOut()" class="text-[10px] bg-blue-600 px-2 py-1 rounded font-bold uppercase hover:bg-blue-400">Unblock Tab</button>
            </div>
            <div class="h-[70vh] bg-white">
                <iframe id="proxyFrame" src="" class="w-full h-full border-none"></iframe>
            </div>
        </div>
        <p class="text-center text-gray-600 text-[10px] mt-4 tracking-tighter">
            IF PAGE IS BLANK: SITES LIKE TIKTOK BLOCK "FRAMING". CLICK 'UNBLOCK TAB' TO BYPASS.
        </p>
    </div>

    <script>
        const form = document.getElementById('proxyForm');
        const input = document.getElementById('urlInput');
        const resultArea = document.getElementById('resultArea');
        const frame = document.getElementById('proxyFrame');
        const urlTitle = document.getElementById('urlTitle');

        let currentUrl = "";

        form.addEventListener('submit', (e) => {
            e.preventDefault();
            let val = input.value.trim();
            if (!val) return;

            if (!val.includes('.') || val.includes(' ')) {
                currentUrl = `https://www.google.com/search?q=${encodeURIComponent(val)}&igu=1`;
            } else {
                currentUrl = val.startsWith('http') ? val : 'https://' + val;
            }
            launch(currentUrl);
        });

        function launch(url) {
            currentUrl = url;
            urlTitle.innerText = url;
            frame.src = url;
            resultArea.classList.remove('hidden');
            window.scrollTo({ top: resultArea.offsetTop - 20, behavior: 'smooth' });
        }

        function closeFrame() {
            resultArea.classList.add('hidden');
            frame.src = "";
        }

        function popOut() {
            // This bypasses the iframe security by opening the site in a clean tab
            if (currentUrl) window.open(currentUrl, '_blank');
        }
    </script>
</body>
</html>
