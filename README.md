<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Arcade Proxy</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap" rel="stylesheet">
    <style>
        body { font-family: 'Inter', sans-serif; background-color: #050505; color: white; }
        .bento-card { background: #0f0f0f; border: 1px solid #1f1f1f; border-radius: 24px; }
        .proxy-input { 
            background: #161616; 
            border: 1px solid #333; 
            outline: none;
            transition: border-color 0.3s;
        }
        .proxy-input:focus { border-color: #3b82f6; }
    </style>
</head>
<body class="flex flex-col items-center justify-center min-h-screen p-6">

    <nav class="bg-[#0f0f0f] border border-[#1f1f1f] rounded-full px-6 py-3 flex gap-6 mb-12">
        <button class="hover:text-blue-500 transition">🎮</button>
        <button class="hover:text-blue-500 transition">🧱</button>
        <button class="hover:text-blue-500 transition">🤝</button>
        <button class="hover:text-blue-500 transition">➕</button>
    </nav>

    <h1 class="text-4xl font-bold mb-8 tracking-tight">useridk758 v1</h1>

    <div class="flex gap-4 mb-10">
        <div class="w-14 h-14 bento-card flex items-center justify-center text-2xl cursor-pointer hover:scale-110 transition">🌐</div>
        <div class="w-14 h-14 bento-card flex items-center justify-center text-2xl cursor-pointer hover:scale-110 transition">📺</div>
        <div class="w-14 h-14 bento-card flex items-center justify-center text-2xl cursor-pointer hover:scale-110 transition">💬</div>
        <div class="w-14 h-14 bento-card flex items-center justify-center text-2xl cursor-pointer hover:scale-110 transition">🎵</div>
    </div>

    <div class="w-full max-w-xl">
        <form id="proxyForm" class="relative">
            <input 
                type="text" 
                id="urlInput"
                placeholder="search anything..." 
                class="w-full proxy-input py-4 px-6 rounded-full text-center text-lg"
            >
        </form>
    </div>

    <div id="frameWrapper" class="hidden w-full max-w-5xl mt-10 h-[600px] bento-card overflow-hidden">
        <iframe id="proxyFrame" src="" class="w-full h-full border-none"></iframe>
    </div>

    <button class="mt-8
