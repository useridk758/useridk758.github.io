<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>useridk758 | Arcade</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap" rel="stylesheet">
    <style>
        body { font-family: 'Inter', sans-serif; background-color: #050505; color: white; overflow-x: hidden; }
        .bento-card { background: #0f0f0f; border: 1px solid #1f1f1f; border-radius: 24px; }
        .proxy-input { 
            background: #0a0a0a; 
            border: 1px solid #333; 
            outline: none;
            transition: all 0.3s;
        }
        .proxy-input:focus { border-color: #3b82f6; box-shadow: 0 0 15px rgba(59, 130, 246, 0.3); }
        iframe { background: white; border-radius: 12px; }
    </style>
</head>
<body class="flex flex-col items-center min-h-screen p-6">

    <nav class="mt-4 bg-[#0f0f0f] border border-[#1f1f1f] rounded-full px-8 py-4 flex gap-8 mb-16 shadow-2xl">
        <div class="cursor-pointer hover:scale-125 transition">🐸</div>
        <div class="cursor-pointer hover:scale-125 transition text-gray-400 hover:text-white">🎮</div>
        <div class="cursor-pointer hover:scale-125 transition text-gray-400 hover:text-white">📁</div>
        <div class="cursor-pointer hover:scale-125 transition text-gray-400 hover:text-white">⚙️</div>
    </nav>

    <div class="text-center mb-10">
        <h1 class="text-5xl font-black mb-4 tracking-tighter italic">useridk758 v4</h1>
        <div class="flex justify-center gap-3">
            <div class="w-12 h-12 bento-card flex items-center justify-center hover:bg-blue-600 cursor-pointer transition">🌐</div>
            <div class="w-12 h-12 bento-card flex items-center justify-center hover:bg-purple-600 cursor-pointer transition">🎬</div>
            <div class="w-12 h-12 bento-card flex items-center justify-center hover:bg-red-600 cursor-pointer transition">🎧</div>
        </div>
    </div>

    <div class="w-full max-w-2xl mb-12">
        <form id="proxyForm" class="relative group">
            <input 
                type="text" 
                id="urlInput"
                placeholder="enter url or search anything..." 
                class="w-full proxy-input py-5 px-8 rounded-full text-center text-xl shadow-inner"
            >
            <button type="submit" class="absolute right-4 top-3 bg-white text-black p-2 rounded-full font-bold hover:bg-blue-500 hover:text-white transition">Go</button>
        </form>
    </div>

    <div id="resultArea" class="hidden w-full max-w-6xl">
        <div class="flex justify-between items-center mb-4 px-4">
            <span id="displayUrl" class="text-sm text-gray-500 font-mono"></span>
            <button onclick="closeFrame()" class="text-red-500 hover:underline text-sm uppercase font-bold tracking-widest">Close Window [X]</button>
        </div>
        <div class="bento-card p-2 h-[70vh] shadow-2xl">
            <iframe id="proxyFrame" src="" class="w-full h-full border-none"></iframe>
        </div>
        <p class="text-xs text-gray-600 mt-4 text-center">
            Note: If the site is blank, it's blocking the "frame." You'll need an Ultraviolet backend to unblock it.
        </p>
    </div>

    <footer class="mt-auto py-10 text-center">
        <button class="bento-card px-8 py-3 text-gray-400 hover:text-white hover:border-blue-500 transition">
            join the discord for more links
        </button>
        <p class="text-gray-700 text-[10px] mt-6 uppercase tracking-[0.2em]">privacy policy • terms of service</p>
    </footer>

    <script>
        const form = document.getElementById('proxyForm');
        const input = document.getElementById('urlInput');
        const resultArea = document.getElementById('resultArea');
        const frame = document.getElementById('proxyFrame');
        const displayUrl = document.getElementById('displayUrl');

        form.addEventListener('submit', (e) => {
            e.preventDefault();
            let val = input.value.trim();
            if (!val) return;

            // Simple Logic: If it doesn't look like a URL, search it on DuckDuckGo
            let targetUrl = val;
            if (!val.includes('.') || val.includes(' ')) {
                targetUrl = `https://duckduckgo.com/?q=${encodeURIComponent(val)}&kp=-2`;
            } else if (!val.startsWith('http')) {
                targetUrl = 'https://' + val;
            }

            displayUrl.innerText = "Loading: " + targetUrl;
            frame.src = targetUrl;
            resultArea.classList.remove('hidden');
            
            // Auto-scroll to the frame
            window.scrollTo({ top: document.body.scrollHeight, behavior: 'smooth' });
        });

        function closeFrame() {
            resultArea.classList.add('hidden');
            frame.src = "";
        }
    </script>
</body>
</html>
