<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Modern Portfolio</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700&display=swap" rel="stylesheet">
    <style>
        body { font-family: 'Inter', sans-serif; background-color: #050505; }
        .bento-card {
            background: #0f0f0f;
            border: 1px solid #1f1f1f;
            transition: all 0.3s ease;
        }
        .bento-card:hover {
            border-color: #3b82f6; /* Blue glow on hover */
            transform: translateY(-2px);
        }
    </style>
</head>
<body class="text-gray-200 min-h-screen p-4 md:p-10">

    <main class="max-w-5xl mx-auto">
        
        <header class="mb-12 flex justify-between items-end">
            <div>
                <h1 class="text-4xl font-bold tracking-tight text-white">John Doe</h1>
                <p class="text-gray-400 mt-2">Designer & Developer</p>
            </div>
            <a href="mailto:hello@example.com" class="bg-white text-black px-5 py-2 rounded-full font-semibold hover:bg-gray-200 transition">Contact Me</a>
        </header>

        <div class="grid grid-cols-1 md:grid-cols-4 md:grid-rows-2 gap-4">
            
            <div class="md:col-span-2 md:row-span-2 bento-card rounded-3xl p-8 flex flex-col justify-end min-h-[300px]">
                <span class="text-blue-500 font-mono text-sm mb-2 uppercase tracking-widest">About Me</span>
                <h2 class="text-2xl font-semibold text-white">Building digital experiences that don't look like shit.</h2>
                <p class="text-gray-400 mt-4 leading-relaxed">
                    I specialize in turning basic ideas into high-performance websites. Currently focused on minimalist UI and fast loading times.
                </p>
            </div>

            <div class="md:col-span-2 bento-card rounded-3xl p-6 flex justify-between items-center">
                <div>
                    <h3 class="text-xl font-bold text-white">Project Alpha</h3>
                    <p class="text-gray-500">React / Tailwind / Node</p>
                </div>
                <div class="text-3xl text-gray-700">↗</div>
            </div>

            <div class="md:col-span-1 bento-card rounded-3xl p-6 flex flex-col justify-center items-center">
                <div class="text-blue-500 text-3xl mb-2">⚡</div>
                <p class="font-bold text-white uppercase text-xs tracking-tighter">Performance</p>
            </div>

            <div class="md:col-span-1 bento-card rounded-3xl p-6 flex flex-col justify-center items-center">
                <div class="text-pink-500 text-3xl mb-2">📸</div>
                <p class="font-bold text-white uppercase text-xs tracking-tighter">Instagram</p>
            </div>

        </div>

        <footer class="mt-1
