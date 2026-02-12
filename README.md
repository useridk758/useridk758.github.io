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
        <div onclick="launchProxy('https://www.google.
