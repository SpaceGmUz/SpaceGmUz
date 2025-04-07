<!DOCTYPE html>
<html lang="uz">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SpaceGmUz - Gaming Portal</title>
    <script src="https://cdn.tailwindcss.com/3.4.16"></script>
    <script>tailwind.config={theme:{extend:{colors:{primary:'#00F0FF',secondary:'#FF2D95'},borderRadius:{'none':'0px','sm':'4px',DEFAULT:'8px','md':'12px','lg':'16px','xl':'20px','2xl':'24px','3xl':'32px','full':'9999px','button':'8px'}}}}</script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Pacifico&display=swap" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css2?family=Exo+2:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    <link href="https://cdn.jsdelivr.net/npm/remixicon@4.5.0/fonts/remixicon.css" rel="stylesheet">
    <style>
        :where([class^="ri-"])::before { content: "\f3c2"; }
        
        body {
            font-family: 'Exo 2', sans-serif;
            background-color: #0A0A1B;
            color: #fff;
        }
        
        .neon-border {
            position: relative;
            border: 1px solid transparent;
            background-clip: padding-box;
        }
        
        .neon-border::before {
            content: '';
            position: absolute;
            top: 0;
            right: 0;
            bottom: 0;
            left: 0;
            z-index: -1;
            margin: -2px;
            border-radius: inherit;
            background: linear-gradient(45deg, #00F0FF, #FF2D95);
        }
        
        .glow-effect {
            box-shadow: 0 0 15px rgba(0, 240, 255, 0.5);
            transition: all 0.3s ease;
        }
        
        .glow-effect:hover {
            box-shadow: 0 0 25px rgba(0, 240, 255, 0.8);
        }
        
        .hero-overlay {
            background: linear-gradient(to right, rgba(10, 10, 27, 0.9), rgba(10, 10, 27, 0.5));
        }
        
        .game-card {
            transition: all 0.3s ease;
            border: 1px solid rgba(0, 240, 255, 0.1);
        }
        
        .game-card:hover {
            transform: scale(1.03);
            border-color: #00F0FF;
            box-shadow: 0 0 20px rgba(0, 240, 255, 0.3);
        }
        
        .youtube-btn {
            position: relative;
            overflow: hidden;
            transition: all 0.3s ease;
        }
        
        .youtube-btn:hover {
            transform: scale(1.05);
            box-shadow: 0 0 30px rgba(255, 45, 149, 0.6);
        }
        
        .youtube-btn::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent, rgba(255, 45, 149, 0.3), transparent);
            transform: rotate(45deg);
            animation: shine 3s infinite;
        }
        
        @keyframes shine {
            0% {
                left: -100%;
                top: -100%;
            }
            100% {
                left: 100%;
                top: 100%;
            }
        }
        
        .slider-indicator {
            width: 10px;
            height: 10px;
            border-radius: 50%;
            background-color: rgba(255, 255, 255, 0.3);
            cursor: pointer;
            transition: all 0.3s ease;
        }
        
        .slider-indicator.active {
            background-color: #00F0FF;
            box-shadow: 0 0 10px #00F0FF;
        }
        
        .pattern-bg {
            background-image: radial-gradient(rgba(0, 240, 255, 0.1) 1px, transparent 1px);
            background-size: 20px 20px;
        }
    </style>
</head>
<body class="min-h-screen">
    <!-- Header -->
    <header class="fixed top-0 left-0 w-full h-[70px] z-50 bg-[#0A0A1B]/90 backdrop-blur-md border-b border-primary/20">
        <div class="container mx-auto px-4 h-full flex items-center justify-between">
            <a href="#" class="text-3xl font-['Pacifico'] text-primary">SpaceGmUz</a>
            
            <!-- Desktop Menu -->
            <div class="hidden md:flex items-center space-x-6">
                <a href="#" class="text-white hover:text-primary transition-colors">Bosh sahifa</a>
                <a href="#" class="text-white hover:text-primary transition-colors">O'yinlar</a>
                <a href="#" class="text-white hover:text-primary transition-colors">Yangiliklar</a>
                <a href="#" class="text-white hover:text-primary transition-colors">Jamoa</a>
                <div class="flex items-center space-x-3 ml-4">
                    <button class="px-4 py-2 rounded-button border border-white/20 text-white hover:border-primary hover:text-primary transition-all whitespace-nowrap">Kirish</button>
                    <button class="px-4 py-2 rounded-button bg-gradient-to-r from-primary to-secondary text-[#0A0A1B] font-medium hover:shadow-lg hover:shadow-primary/20 transition-all whitespace-nowrap">Ro'yxatdan o'tish</button>
                </div>
            </div>
            
            <!-- Mobile Menu Button -->
            <button class="md:hidden w-10 h-10 flex items-center justify-center text-white">
                <i class="ri-menu-line ri-lg"></i>
            </button>
        </div>
    </header>

    <!-- Mobile Menu (Hidden by default) -->
    <div class="hidden fixed inset-0 z-40 bg-[#0A0A1B] pt-[70px]">
        <div class="container mx-auto px-4 py-8 flex flex-col space-y-6">
            <a href="#" class="text-xl text-white hover:text-primary transition-colors py-2 border-b border-white/10">Bosh sahifa</a>
            <a href="#" class="text-xl text-white hover:text-primary transition-colors py-2 border-b border-white/10">O'yinlar</a>
            <a href="#" class="text-xl text-white hover:text-primary transition-colors py-2 border-b border-white/10">Yangiliklar</a>
            <a href="#" class="text-xl text-white hover:text-primary transition-colors py-2 border-b border-white/10">Jamoa</a>
            <div class="flex flex-col space-y-3 pt-4">
                <button class="w-full py-3 rounded-button border border-white/20 text-white hover:border-primary hover:text-primary transition-all">Kirish</button>
                <button class="w-full py-3 rounded-button bg-gradient-to-r from-primary to-secondary text-[#0A0A1B] font-medium hover:shadow-lg hover:shadow-primary/20 transition-all">Ro'yxatdan o'tish</button>
            </div>
        </div>
    </div>

    <main class="pt-[70px]">
        <!-- Hero Section -->
        <section class="relative h-[600px] overflow-hidden">
            <div class="absolute inset-0" style="background-image: url('https://public.readdy.ai/ai/img_res/9029da53b70e6c40c75d74e2c51d6f4b.jpg'); background-size: cover; background-position: center;"></div>
            <div class="absolute inset-0 hero-overlay"></div>
            
            <div class="relative container mx-auto px-4 h-full flex items-center">
                <div class="max-w-2xl">
                    <h1 class="text-4xl md:text-5xl lg:text-6xl font-bold mb-4 leading-tight">
                        <span class="text-white">Kelajak</span> 
                        <span class="text-primary">Gaming</span> 
                        <span class="text-white">Dunyosi</span>
                    </h1>
                    <p class="text-lg md:text-xl text-white/80 mb-8">O'zbekistondagi eng yirik gaming portali. Zamonaviy o'yinlar, yangiliklar va professional geymerlar jamoasi bilan tanishing.</p>
                    <div class="flex flex-wrap gap-4">
                        <button class="px-6 py-3 rounded-button bg-gradient-to-r from-primary to-primary/80 text-[#0A0A1B] font-medium hover:shadow-lg hover:shadow-primary/30 transition-all whitespace-nowrap">
                            <i class="ri-gamepad-line mr-2"></i>O'yinlarni ko'rish
                        </button>
                        <button class="px-6 py-3 rounded-button border border-white/30 text-white hover:border-primary hover:text-primary transition-all whitespace-nowrap">
                            <i class="ri-information-line mr-2"></i>Batafsil ma'lumot
                        </button>
                    </div>
                </div>
            </div>
            
            <!-- Slider Indicators -->
            <div class="absolute bottom-6 left-0 right-0 flex justify-center space-x-3">
                <span class="slider-indicator active"></span>
                <span class="slider-indicator"></span>
                <span class="slider-indicator"></span>
            </div>
        </section>

        <!-- Featured Games Section -->
        <section class="py-16 bg-[#080814]">
            <div class="container mx-auto px-4">
                <div class="flex justify-between items-center mb-10">
                    <h2 class="text-3xl font-bold">
                        <span class="text-white">Mashhur</span>
                        <span class="text-primary">O'yinlar</span>
                    </h2>
                    <a href="#" class="text-white/70 hover:text-primary flex items-center transition-colors">
                        Barchasini ko'rish
                        <i class="ri-arrow-right-line ml-2"></i>
                    </a>
                </div>
                
                <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                    <!-- Game Card 1 -->
                    <div class="game-card bg-[#0D0D21] rounded overflow-hidden">
                        <div class="h-48 overflow-hidden">
                            <img src="https://public.readdy.ai/ai/img_res/8ad13adff8ace621ce5dbb171bef521b.jpg" alt="Cyberpunk 2077" class="w-full h-full object-cover object-top transition-transform duration-500 hover:scale-110">
                        </div>
                        <div class="p-5">
                            <div class="flex justify-between items-center mb-3">
                                <h3 class="text-xl font-semibold">Cyberpunk 2077</h3>
                                <span class="text-xs px-2 py-1 rounded-full bg-primary/20 text-primary">RPG</span>
                            </div>
                            <p class="text-white/70 text-sm mb-4">Kelajakdagi Night City shahrida o'tadigan zamonaviy RPG o'yini.</p>
                            <div class="flex justify-between items-center">
                                <div class="flex items-center">
                                    <div class="flex">
                                        <i class="ri-star-fill text-yellow-400"></i>
                                        <i class="ri-star-fill text-yellow-400"></i>
                                        <i class="ri-star-fill text-yellow-400"></i>
                                        <i class="ri-star-fill text-yellow-400"></i>
                                        <i class="ri-star-half-fill text-yellow-400"></i>
                                    </div>
                                    <span class="text-white/70 text-sm ml-2">4.5</span>
                                </div>
                                <button class="px-3 py-1 rounded-button bg-primary/10 text-primary hover:bg-primary/20 transition-colors whitespace-nowrap">Batafsil</button>
                            </div>
                        </div>
                    </div>
                    
                    <!-- Game Card 2 -->
                    <div class="game-card bg-[#0D0D21] rounded overflow-hidden">
                        <div class="h-48 overflow-hidden">
                            <img src="https://public.readdy.ai/ai/img_res/b1ccbd645c4ef3851d135f94e21adeac.jpg" alt="Elden Ring" class="w-full h-full object-cover object-top transition-transform duration-500 hover:scale-110">
                        </div>
                        <div class="p-5">
                            <div class="flex justify-between items-center mb-3">
                                <h3 class="text-xl font-semibold">Elden Ring</h3>
                                <span class="text-xs px-2 py-1 rounded-full bg-secondary/20 text-secondary">Action RPG</span>
                            </div>
                            <p class="text-white/70 text-sm mb-4">FromSoftware studiyasidan ajoyib fantastik dunyo va qiyin janglar.</p>
                            <div class="flex justify-between items-center">
                                <div class="flex items-center">
                                    <div class="flex">
                                        <i class="ri-star-fill text-yellow-400"></i>
                                        <i class="ri-star-fill text-yellow-400"></i>
                                        <i class="ri-star-fill text-yellow-400"></i>
                                        <i class="ri-star-fill text-yellow-400"></i>
                                        <i class="ri-star-fill text-yellow-400"></i>
                                    </div>
                                    <span class="text-white/70 text-sm ml-2">4.9</span>
                                </div>
                                <button class="px-3 py-1 rounded-button bg-primary/10 text-primary hover:bg-primary/20 transition-colors whitespace-nowrap">Batafsil</button>
                            </div>
                        </div>
                    </div>
                    
                    <!-- Game Card 3 -->
                    <div class="game-card bg-[#0D0D21] rounded overflow-hidden">
                        <div class="h-48 overflow-hidden">
                            <img src="https://public.readdy.ai/ai/img_res/ee9452c261f019352f189cd09d3cc824.jpg" alt="Call of Duty" class="w-full h-full object-cover object-top transition-transform duration-500 hover:scale-110">
                        </div>
                        <div class="p-5">
                            <div class="flex justify-between items-center mb-3">
                                <h3 class="text-xl font-semibold">Call of Duty: MW III</h3>
                                <span class="text-xs px-2 py-1 rounded-full bg-blue-500/20 text-blue-400">FPS</span>
                            </div>
                            <p class="text-white/70 text-sm mb-4">Zamonaviy urush maydonlarida kechadigan janglar va maxsus operatsiyalar.</p>
                            <div class="flex justify-between items-center">
                                <div class="flex items-center">
                                    <div class="flex">
                                        <i class="ri-star-fill text-yellow-400"></i>
                                        <i class="ri-star-fill text-yellow-400"></i>
                                        <i class="ri-star-fill text-yellow-400"></i>
                                        <i class="ri-star-fill text-yellow-400"></i>
                                        <i class="ri-star-line text-yellow-400"></i>
                                    </div>
                                    <span class="text-white/70 text-sm ml-2">4.0</span>
                                </div>
                                <button class="px-3 py-1 rounded-button bg-primary/10 text-primary hover:bg-primary/20 transition-colors whitespace-nowrap">Batafsil</button>
                            </div>
                        </div>
                    </div>
                    
                    <!-- Game Card 4 -->
                    <div class="game-card bg-[#0D0D21] rounded overflow-hidden">
                        <div class="h-48 overflow-hidden">
                            <img src="https://public.readdy.ai/ai/img_res/28f6d5e99ea17eecb0463fbe2b1d9cc9.jpg" alt="Fortnite" class="w-full h-full object-cover object-top transition-transform duration-500 hover:scale-110">
                        </div>
                        <div class="p-5">
                            <div class="flex justify-between items-center mb-3">
                                <h3 class="text-xl font-semibold">Fortnite</h3>
                                <span class="text-xs px-2 py-1 rounded-full bg-green-500/20 text-green-400">Battle Royale</span>
                            </div>
                            <p class="text-white/70 text-sm mb-4">Qurilish va jang elementlarini birlashtirgan mashhur battle royale o'yini.</p>
                            <div class="flex justify-between items-center">
                                <div class="flex items-center">
                                    <div class="flex">
                                        <i class="ri-star-fill text-yellow-400"></i>
                                        <i class="ri-star-fill text-yellow-400"></i>
                                        <i class="ri-star-fill text-yellow-400"></i>
                                        <i class="ri-star-fill text-yellow-400"></i>
                                        <i class="ri-star-half-fill text-yellow-400"></i>
                                    </div>
                                    <span class="text-white/70 text-sm ml-2">4.5</span>
                                </div>
                                <button class="px-3 py-1 rounded-button bg-primary/10 text-primary hover:bg-primary/20 transition-colors whitespace-nowrap">Batafsil</button>
                            </div>
                        </div>
                    </div>
                    
                    <!-- Game Card 5 -->
                    <div class="game-card bg-[#0D0D21] rounded overflow-hidden">
                        <div class="h-48 overflow-hidden">
                            <img src="https://public.readdy.ai/ai/img_res/c5e26f5164ef1fb0137e5b7bb571df1d.jpg" alt="FIFA 23" class="w-full h-full object-cover object-top transition-transform duration-500 hover:scale-110">
                        </div>
                        <div class="p-5">
                            <div class="flex justify-between items-center mb-3">
                                <h3 class="text-xl font-semibold">EA Sports FC 24</h3>
                                <span class="text-xs px-2 py-1 rounded-full bg-orange-500/20 text-orange-400">Sport</span>
                            </div>
                            <p class="text-white/70 text-sm mb-4">Eng realistik futbol simulyatori, yangi texnologiyalar bilan.</p>
                            <div class="flex justify-between items-center">
                                <div class="flex items-center">
                                    <div class="flex">
                                        <i class="ri-star-fill text-yellow-400"></i>
                                        <i class="ri-star-fill text-yellow-400"></i>
                                        <i class="ri-star-fill text-yellow-400"></i>
                                        <i class="ri-star-half-fill text-yellow-400"></i>
                                        <i class="ri-star-line text-yellow-400"></i>
                                    </div>
                                    <span class="text-white/70 text-sm ml-2">3.5</span>
                                </div>
                                <button class="px-3 py-1 rounded-button bg-primary/10 text-primary hover:bg-primary/20 transition-colors whitespace-nowrap">Batafsil</button>
                            </div>
                        </div>
                    </div>
                    
                    <!-- Game Card 6 -->
                    <div class="game-card bg-[#0D0D21] rounded overflow-hidden">
                        <div class="h-48 overflow-hidden">
                            <img src="https://public.readdy.ai/ai/img_res/eaa577e6194bc67d399f44579c1ad726.jpg" alt="Minecraft" class="w-full h-full object-cover object-top transition-transform duration-500 hover:scale-110">
                        </div>
                        <div class="p-5">
                            <div class="flex justify-between items-center mb-3">
                                <h3 class="text-xl font-semibold">Minecraft</h3>
                                <span class="text-xs px-2 py-1 rounded-full bg-purple-500/20 text-purple-400">Sandbox</span>
                            </div>
                            <p class="text-white/70 text-sm mb-4">Cheksiz imkoniyatlar bilan to'liq ochiq dunyo qurilish o'yini.</p>
                            <div class="flex justify-between items-center">
                                <div class="flex items-center">
                                    <div class="flex">
                                        <i class="ri-star-fill text-yellow-400"></i>
                                        <i class="ri-star-fill text-yellow-400"></i>
                                        <i class="ri-star-fill text-yellow-400"></i>
                                        <i class="ri-star-fill text-yellow-400"></i>
                                        <i class="ri-star-fill text-yellow-400"></i>
                                    </div>
                                    <span class="text-white/70 text-sm ml-2">4.8</span>
                                </div>
                                <button class="px-3 py-1 rounded-button bg-primary/10 text-primary hover:bg-primary/20 transition-colors whitespace-nowrap">Batafsil</button>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- YouTube Section -->
        <section class="py-20 pattern-bg">
            <div class="container mx-auto px-4">
                <div class="max-w-3xl mx-auto text-center">
                    <h2 class="text-3xl md:text-4xl font-bold mb-4">
                        <span class="text-white">Bizning</span>
                        <span class="text-secondary">YouTube</span>
                        <span class="text-white">kanalimiz</span>
                    </h2>
                    <p class="text-white/70 mb-8">Eng so'nggi o'yin sharhlari, walkthrough'lar va gaming yangiliklari uchun YouTube kanalimizga obuna bo'ling.</p>
                    
                    <div class="relative mb-10 rounded-lg overflow-hidden">
                        <img src="https://public.readdy.ai/ai/img_res/7453fbf9c66b70247bde493dd5d7b5b6.jpg" alt="YouTube Channel" class="w-full h-auto">
                        <div class="absolute inset-0 flex items-center justify-center bg-black/40">
                            <button class="w-16 h-16 rounded-full bg-white/10 backdrop-blur-md flex items-center justify-center hover:bg-white/20 transition-colors">
                                <i class="ri-play-fill text-white ri-2x"></i>
                            </button>
                        </div>
                    </div>
                    
                    <a href="#" class="youtube-btn inline-block px-8 py-4 rounded-button bg-gradient-to-r from-secondary to-secondary/80 text-white font-medium whitespace-nowrap">
                        <i class="ri-youtube-fill mr-2"></i>Kanalga obuna bo'lish
                    </a>
                    
                    <div class="mt-8 flex flex-wrap justify-center gap-4">
                        <div class="flex items-center text-white/70">
                            <i class="ri-user-3-line mr-2"></i>
                            <span>45K+ Obunachilar</span>
                        </div>
                        <div class="flex items-center text-white/70">
                            <i class="ri-video-line mr-2"></i>
                            <span>200+ Videolar</span>
                        </div>
                        <div class="flex items-center text-white/70">
                            <i class="ri-time-line mr-2"></i>
                            <span>Har hafta yangi kontent</span>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Gaming Categories -->
        <section class="py-16 bg-[#080814]">
            <div class="container mx-auto px-4">
                <h2 class="text-3xl font-bold mb-10">
                    <span class="text-white">O'yin</span>
                    <span class="text-primary">Kategoriyalari</span>
                </h2>
                
                <div class="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-6 gap-4">
                    <!-- Category 1 -->
                    <div class="bg-[#0D0D21] rounded p-5 text-center hover:bg-[#10102A] transition-colors cursor-pointer">
                        <div class="w-16 h-16 mx-auto mb-3 rounded-full bg-primary/10 flex items-center justify-center">
                            <i class="ri-sword-line text-primary ri-xl"></i>
                        </div>
                        <h3 class="font-medium">Action</h3>
                        <p class="text-xs text-white/60 mt-1">42 o'yin</p>
                    </div>
                    
                    <!-- Category 2 -->
                    <div class="bg-[#0D0D21] rounded p-5 text-center hover:bg-[#10102A] transition-colors cursor-pointer">
                        <div class="w-16 h-16 mx-auto mb-3 rounded-full bg-secondary/10 flex items-center justify-center">
                            <i class="ri-ghost-line text-secondary ri-xl"></i>
                        </div>
                        <h3 class="font-medium">RPG</h3>
                        <p class="text-xs text-white/60 mt-1">38 o'yin</p>
                    </div>
                    
                    <!-- Category 3 -->
                    <div class="bg-[#0D0D21] rounded p-5 text-center hover:bg-[#10102A] transition-colors cursor-pointer">
                        <div class="w-16 h-16 mx-auto mb-3 rounded-full bg-blue-500/10 flex items-center justify-center">
                            <i class="ri-gun-line text-blue-400 ri-xl"></i>
                        </div>
                        <h3 class="font-medium">FPS</h3>
                        <p class="text-xs text-white/60 mt-1">29 o'yin</p>
                    </div>
                    
                    <!-- Category 4 -->
                    <div class="bg-[#0D0D21] rounded p-5 text-center hover:bg-[#10102A] transition-colors cursor-pointer">
                        <div class="w-16 h-16 mx-auto mb-3 rounded-full bg-green-500/10 flex items-center justify-center">
                            <i class="ri-boxing-line text-green-400 ri-xl"></i>
                        </div>
                        <h3 class="font-medium">Sport</h3>
                        <p class="text-xs text-white/60 mt-1">24 o'yin</p>
                    </div>
                    
                    <!-- Category 5 -->
                    <div class="bg-[#0D0D21] rounded p-5 text-center hover:bg-[#10102A] transition-colors cursor-pointer">
                        <div class="w-16 h-16 mx-auto mb-3 rounded-full bg-purple-500/10 flex items-center justify-center">
                            <i class="ri-building-line text-purple-400 ri-xl"></i>
                        </div>
                        <h3 class="font-medium">Simulator</h3>
                        <p class="text-xs text-white/60 mt-1">31 o'yin</p>
                    </div>
                    
                    <!-- Category 6 -->
                    <div class="bg-[#0D0D21] rounded p-5 text-center hover:bg-[#10102A] transition-colors cursor-pointer">
                        <div class="w-16 h-16 mx-auto mb-3 rounded-full bg-orange-500/10 flex items-center justify-center">
                            <i class="ri-road-map-line text-orange-400 ri-xl"></i>
                        </div>
                        <h3 class="font-medium">Adventure</h3>
                        <p class="text-xs text-white/60 mt-1">35 o'yin</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- Newsletter Section -->
        <section class="py-20 relative overflow-hidden">
            <div class="absolute inset-0" style="background-image: url('https://public.readdy.ai/ai/img_res/abf1500c956e11f077a8f38c0be30bf8.jpg'); background-size: cover; background-position: center; opacity: 0.2;"></div>
            
            <div class="container mx-auto px-4 relative">
                <div class="max-w-2xl mx-auto text-center">
                    <h2 class="text-3xl md:text-4xl font-bold mb-4">
                        <span class="text-white">Yangiliklarga</span>
                        <span class="text-primary">obuna bo'ling</span>
                    </h2>
                    <p class="text-white/70 mb-8">Eng so'nggi o'yin yangiliklari, chegirmalar va maxsus takliflar haqida birinchilardan bo'lib xabardor bo'ling.</p>
                    
                    <form class="flex flex-col sm:flex-row gap-3 max-w-md mx-auto">
                        <input type="email" placeholder="Email manzilingiz" class="flex-1 px-4 py-3 rounded-button bg-white/5 border border-white/10 text-white placeholder-white/40 focus:outline-none focus:border-primary">
                        <button type="submit" class="px-6 py-3 rounded-button bg-gradient-to-r from-primary to-primary/80 text-[#0A0A1B] font-medium hover:shadow-lg hover:shadow-primary/30 transition-all whitespace-nowrap">Obuna bo'lish</button>
                    </form>
                    
                    <p class="text-xs text-white/50 mt-4">Biz sizning shaxsiy ma'lumotlaringizni hurmat qilamiz. <a href="#" class="text-primary hover:underline">Maxfiylik siyosati</a>.</p>
                </div>
            </div>
        </section>
    </main>

    <!-- Footer -->
    <footer class="bg-[#070710] pt-16 pb-8">
        <div class="container mx-auto px-4">
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8 mb-12">
                <div>
                    <a href="#" class="text-3xl font-['Pacifico'] text-primary mb-4 inline-block">SpaceGmUz</a>
                    <p class="text-white/60 mb-6">O'zbekistondagi eng yirik gaming portali. Professional geymerlar va yangi boshlovchilar uchun.</p>
                    <div class="flex space-x-4">
                        <a href="#" class="w-10 h-10 rounded-full bg-white/5 flex items-center justify-center hover:bg-primary/20 hover:text-primary transition-colors">
                            <i class="ri-facebook-fill"></i>
                        </a>
                        <a href="#" class="w-10 h-10 rounded-full bg-white/5 flex items-center justify-center hover:bg-primary/20 hover:text-primary transition-colors">
                            <i class="ri-twitter-x-fill"></i>
                        </a>
                        <a href="#" class="w-10 h-10 rounded-full bg-white/5 flex items-center justify-center hover:bg-primary/20 hover:text-primary transition-colors">
                            <i class="ri-instagram-fill"></i>
                        </a>
                        <a href="#" class="w-10 h-10 rounded-full bg-white/5 flex items-center justify-center hover:bg-primary/20 hover:text-primary transition-colors">
                            <i class="ri-youtube-fill"></i>
                        </a>
                        <a href="#" class="w-10 h-10 rounded-full bg-white/5 flex items-center justify-center hover:bg-primary/20 hover:text-primary transition-colors">
                            <i class="ri-telegram-fill"></i>
                        </a>
                    </div>
                </div>
                
                <div>
                    <h3 class="text-lg font-semibold mb-4">Tezkor havolalar</h3>
                    <ul class="space-y-2">
                        <li><a href="#" class="text-white/60 hover:text-primary transition-colors">Bosh sahifa</a></li>
                        <li><a href="#" class="text-white/60 hover:text-primary transition-colors">O'yinlar katalogi</a></li>
                        <li><a href="#" class="text-white/60 hover:text-primary transition-colors">Yangiliklar</a></li>
                        <li><a href="#" class="text-white/60 hover:text-primary transition-colors">Turnirlar</a></li>
                        <li><a href="#" class="text-white/60 hover:text-primary transition-colors">Forum</a></li>
                        <li><a href="#" class="text-white/60 hover:text-primary transition-colors">Biz haqimizda</a></li>
                    </ul>
                </div>
                
                <div>
                    <h3 class="text-lg font-semibold mb-4">Yordam</h3>
                    <ul class="space-y-2">
                        <li><a href="#" class="text-white/60 hover:text-primary transition-colors">Ko'p so'raladigan savollar</a></li>
                        <li><a href="#" class="text-white/60 hover:text-primary transition-colors">Qo'llab-quvvatlash</a></li>
                        <li><a href="#" class="text-white/60 hover:text-primary transition-colors">Foydalanish shartlari</a></li>
                        <li><a href="#" class="text-white/60 hover:text-primary transition-colors">Maxfiylik siyosati</a></li>
                        <li><a href="#" class="text-white/60 hover:text-primary transition-colors">Bog'lanish</a></li>
                    </ul>
                </div>
                
                <div>
                    <h3 class="text-lg font-semibold mb-4">Bog'lanish</h3>
                    <ul class="space-y-3">
                        <li class="flex items-start">
                            <i class="ri-map-pin-line mt-1 mr-3 text-primary"></i>
                            <span class="text-white/60">Toshkent sh., Chilonzor tumani, Bunyodkor ko'chasi, 15-uy</span>
                        </li>
                        <li class="flex items-center">
                            <i class="ri-mail-line mr-3 text-primary"></i>
                            <a href="mailto:info@spacegmuz.uz" class="text-white/60 hover:text-primary transition-colors">info@spacegmuz.uz</a>
                        </li>
                        <li class="flex items-center">
                            <i class="ri-phone-line mr-3 text-primary"></i>
                            <a href="tel:+998901234567" class="text-white/60 hover:text-primary transition-colors">+998 90 123 45 67</a>
                        </li>
                    </ul>
                </div>
            </div>
            
            <hr class="border-white/10 mb-8">
            
            <div class="flex flex-col md:flex-row justify-between items-center">
                <p class="text-white/40 text-sm">&copy; 2025 SpaceGmUz. Barcha huquqlar himoyalangan.</p>
                <div class="flex items-center space-x-4 mt-4 md:mt-0">
                    <a href="#" class="text-white/40 hover:text-primary text-sm transition-colors">Maxfiylik siyosati</a>
                    <span class="text-white/40">|</span>
                    <a href="#" class="text-white/40 hover:text-primary text-sm transition-colors">Foydalanish shartlari</a>
                </div>
            </div>
        </div>
    </footer>

    <script>
        // Mobile Menu Toggle
        document.querySelector('.md\\:hidden').addEventListener('click', function() {
            const mobileMenu = document.querySelector('.hidden.fixed.inset-0');
            if (mobileMenu.classList.contains('hidden')) {
                mobileMenu.classList.remove('hidden');
                mobileMenu.classList.add('block');
            } else {
                mobileMenu.classList.remove('block');
                mobileMenu.classList.add('hidden');
            }
        });
        
        // Slider Indicators
        const indicators = document.querySelectorAll('.slider-indicator');
        let currentSlide = 0;
        
        function setActiveSlide(index) {
            indicators.forEach(indicator => indicator.classList.remove('active'));
            indicators[index].classList.add('active');
        }
        
        indicators.forEach((indicator, index) => {
            indicator.addEventListener('click', () => {
                currentSlide = index;
                setActiveSlide(currentSlide);
            });
        });
        
        // Auto slide every 5 seconds
        setInterval(() => {
            currentSlide = (currentSlide + 1) % indicators.length;
            setActiveSlide(currentSlide);
        }, 5000);
    </script>
</body>
</html>
