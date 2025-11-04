
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>UMWTV South Africa - Recruitment</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Font Awesome -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&amp;display=swap" rel="stylesheet">
    <!-- GSAP for animations -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.11.4/gsap.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.11.4/ScrollTrigger.min.js"></script>
    <style>
        body {
            font-family: 'Poppins', sans-serif;
            scroll-behavior: smooth;
        }
        
        .hero-section {
            background: linear-gradient(135deg, rgba(0, 51, 102, 0.95), rgba(0, 26, 51, 0.9)), url('https://p26-doubao-search-sign.byteimg.com/tos-cn-i-be4g95zd3a/1067314817921581069~tplv-be4g95zd3a-image.jpeg?rk3s=542c0f93&x-expires=1777136378&x-signature=Y%2BHwwcPjxNBAhaNFFLUJ6jIXFqg%3D') no-repeat center center;
            background-size: cover;
        }
        
        .job-card {
            transition: all 0.3s ease;
        }
        
        .job-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px -5px rgba(0, 0, 0, 0.1), 0 10px 10px -5px rgba(0, 0, 0, 0.04);
        }
        
        .btn-primary {
            background-color: #FF6B00;
            transition: all 0.3s ease;
        }
        
        .btn-primary:hover {
            background-color: #e55a00;
            transform: translateY(-2px);
            box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
        }
        
        .btn-secondary {
            background-color: #003366;
            transition: all 0.3s ease;
        }
        
        .btn-secondary:hover {
            background-color: #002244;
            transform: translateY(-2px);
            box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
        }
        
        .section-title::after {
            content: '';
            display: block;
            width: 80px;
            height: 4px;
            background-color: #FF6B00;
            margin: 15px 0;
        }
        
        /* Animation classes */
        .fade-in {
            opacity: 0;
            transform: translateY(20px);
            transition: opacity 0.6s ease, transform 0.6s ease;
        }
        
        .fade-in.active {
            opacity: 1;
            transform: translateY(0);
        }
        
        /* Custom scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
        }
        
        ::-webkit-scrollbar-track {
            background: #f1f1f1;
        }
        
        ::-webkit-scrollbar-thumb {
            background: #003366;
            border-radius: 4px;
        }
        
        ::-webkit-scrollbar-thumb:hover {
            background: #FF6B00;
        }
        
        /* Dynamic Logo Animations */
        @keyframes float {
            0% { transform: translateY(0px) rotate(0deg); }
            50% { transform: translateY(-15px) rotate(5deg); }
            100% { transform: translateY(0px) rotate(0deg); }
        }
        
        @keyframes pulse-glow {
            0% { box-shadow: 0 0 0 0 rgba(255, 107, 0, 0.4); }
            70% { box-shadow: 0 0 0 15px rgba(255, 107, 0, 0); }
            100% { box-shadow: 0 0 0 0 rgba(255, 107, 0, 0); }
        }
        
        .dynamic-logo {
            animation: float 6s ease-in-out infinite, pulse-glow 2s infinite;
        }
        
        .dynamic-logo:hover {
            animation: float 3s ease-in-out infinite, pulse-glow 1.5s infinite;
            filter: drop-shadow(0 0 10px rgba(0, 51, 102, 0.7));
        }
        
        /* Animated blob effect */
        @keyframes blob {
            0% { transform: translate(0px, 0px) scale(1); }
            33% { transform: translate(30px, -50px) scale(1.1); }
            66% { transform: translate(-20px, 20px) scale(0.9); }
            100% { transform: translate(0px, 0px) scale(1); }
        }
        
        .animate-blob {
            animation: blob 7s infinite;
        }
        
        .animation-delay-2000 {
            animation-delay: 2s;
        }
        
        /* Mobile menu */
        .mobile-menu {
            transform: translateX(-100%);
            transition: transform 0.3s ease-in-out;
        }
        
        .mobile-menu.active {
            transform: translateX(0);
        }
        
        /* Form styles */
        .form-input:focus {
            border-color: #FF6B00;
            box-shadow: 0 0 0 3px rgba(255, 107, 0, 0.2);
        }
        
        /* Job filter */
        .filter-active {
            background-color: #003366;
            color: white;
        }
        
        /* Join Join button styles */
        .btn-join {
            position: relative;
            overflow: hidden;
            z-index: 1;
        }
        
        .btn-join::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.2), transparent);
            transition: 0.5s;
            z-index: -1;
        }
        
        .btn-join:hover::before {
            left: 100%;
        }
        
        @keyframes pulse-ring {
            0% {
                transform: scale(0.8);
                opacity: 0.8;
            }
            80%, 100% {
                opacity: 0;
                transform: scale(2);
            }
        }
        
        .btn-join::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            border-radius: 50px;
            box-shadow: 0 0 0 rgba(255, 107, 0, 0.4);
            animation: pulse-ring 2s infinite;
            z-index: -2;
        }
        
        /* Blob animation */
        @keyframes blob {
            0% {
                transform: translate(0px, 0px) scale(1);
            }
            33% {
                transform: translate(30px, -50px) scale(1.1);
            }
            66% {
                transform: translate(-20px, 20px) scale(0.9);
            }
            100% {
                transform: translate(0px, 0px) scale(1);
            }
        }
        
        .animate-blob {
            animation: blob 7s infinite;
        }
        
        .animation-delay-2000 {
            animation-delay: 2s;
        }
        
        /* Responsive adjustments */
        @media (max-width: 768px) {
            .section-title::after {
                margin: 10px auto;
            }
            
            .btn-join {
                padding: 12px 32px;
                font-size: 14px;
            }
            
            .bg-gradient-to-r.from-orange-500.to-red-500 p.text-2xl {
                font-size: 1.5rem;
            }
            
            .bg-gradient-to-r.from-orange-500.to-red-500 p.text-xl {
                font-size: 1.25rem;
            }
        }
    </style>
</head>
<body class="bg-gray-50">
    <!-- Logo Section with Dynamic Animation -->
    <div class="bg-white py-6 shadow-md">
        <div class="container mx-auto px-4 flex justify-center">
            <div class="relative w-full max-w-3xl">
                <!-- Animated background elements -->
                <div class="absolute -top-10 -right-10 w-40 h-40 rounded-full bg-blue-100 opacity-30 animate-blob"></div>
                <div class="absolute -bottom-10 -left-10 w-40 h-40 rounded-full bg-orange-100 opacity-30 animate-blob animation-delay-2000"></div>
                
                <!-- Logo with dynamic effects -->
                <div class="relative z-10 flex justify-center">
                    <img src="https://p26-flow-imagex-download-sign.byteimg.com/tos-cn-i-a9rns2rl98/87df8cb566d54680b49ff589920dc30f.png~tplv-a9rns2rl98-24:720:720.png?rcl=2025102820381826D578200EB339E86037&amp;rk3s=8e244e95&amp;rrcfp=8a172a1a&amp;x-expires=1762259899&amp;x-signature=41ow19X9N9udO4WhyaU782nSdX0%3D" alt="UMWTV Logo" class="h-32 md:h-40 transition-all duration-500 hover:scale-105 transform dynamic-logo">
                </div>
                
                <!-- Subtitle -->
                <div class="text-center mt-4">
                    <p class="text-xl font-medium text-gray-700 tracking-wide">
                        <span class="animate-pulse">Creating 3 million online jobs in South Africa</span>
                    </p>
                </div>
            </div>
        </div>
    </div>

    <!-- Hero Section -->
    <section id="home" class="hero-section min-h-screen flex items-center pt-16">
        <div class="container mx-auto px-4 py-16">
            <div class="flex flex-col md:flex-row items-center">
                <div class="md:w-1/2 text-white mb-10 md:mb-0">
                    <h1 class="text-4xl md:text-5xl lg:text-6xl font-bold mb-6 leading-tight">
                        Welcome to <span class="text-orange-500">UMWTV</span> South Africa
                    </h1>
                    <div class="bg-gradient-to-r from-orange-500 to-red-500 text-white p-6 rounded-lg mb-8 shadow-xl relative overflow-hidden animate-pulse border-4 border-white">
                        <!-- Decorative elements -->
                        <div class="absolute top-0 left-0 w-full h-2 bg-white opacity-30"></div>
                        <div class="absolute bottom-0 right-0 w-full h-2 bg-white opacity-30"></div>
                        
                        <!-- Content -->
                        <p class="text-2xl md:text-3xl font-bold mb-2 relative z-10">
                            <i class="fas fa-bullhorn mr-3"></i> We are recruiting online part-time assistants!
                        </p>
                        <p class="text-xl md:text-2xl font-medium relative z-10">
                            <i class="fas fa-check-circle mr-2"></i> Easily make money from home
                            <span class="mx-2">•</span>
                            <i class="fas fa-mobile-alt mr-2"></i> Watch videos on your phone
                        </p>
                        
                        <!-- Animated background elements -->
                        <div class="absolute -top-10 -right-10 w-40 h-40 rounded-full bg-white opacity-10 animate-blob"></div>
                        <div class="absolute -bottom-10 -left-10 w-40 h-40 rounded-full bg-white opacity-10 animate-blob animation-delay-2000"></div>
                    </div>
                    <p class="text-xl mb-8 text-gray-200">
                        Join our mission to create 3 million online jobs in South Africa over the next two years.
                    </p>

                </div>
                <div class="md:w-1/2 flex flex-col items-center">
                    <img src="https://p3-flow-imagex-sign.byteimg.com/tos-cn-i-a9rns2rl98/rc/pc/super_tool/b04f85f6e65f434aa919d096dfcffc17~tplv-a9rns2rl98-image.image?rcl=20251028020640B7A25B07B315424AE4AA&amp;rk3s=8e244e95&amp;rrcfp=f06b921b&amp;x-expires=1764180435&amp;x-signature=D8TTMlTu3cyn%2BckNaCmK9xGh0AM%3D" alt="Happy African man with smartphone and bank card" class="rounded-lg shadow-2xl w-full">
                    <a href="https://wa.me/27732627476" class="mt-6 btn-join bg-gradient-to-r from-orange-500 to-red-500 text-white font-bold py-4 px-12 rounded-full shadow-lg transform transition hover:scale-105 hover:shadow-xl focus:outline-none focus:ring-2 focus:ring-orange-500 focus:ring-opacity-50 animate-pulse">
                        <i class="fab fa-whatsapp mr-2"></i> Contact via WhatsApp
                    </a>
                    <a href="https://chat.whatsapp.com/Dm9sHGsVT1WGxzZFq9bgDB" class="mt-4 btn-join bg-gradient-to-r from-green-500 to-teal-500 text-white font-bold py-4 px-12 rounded-full shadow-lg transform transition hover:scale-105 hover:shadow-xl focus:outline-none focus:ring-2 focus:ring-green-500 focus:ring-opacity-50 animate-pulse">
                        <i class="fab fa-whatsapp mr-2"></i> Part-time job consultation group
                    </a>
                </div>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="py-20 bg-white">
        <div class="container mx-auto px-4">
            <h2 class="section-title text-3xl md:text-4xl font-bold text-center mb-16">About UMWTV South Africa</h2>
            
            <div class="flex flex-col md:flex-row items-center mb-16">
                <div class="md:w-1/2 mb-10 md:mb-0">
                    <img src="https://p26-doubao-search-sign.byteimg.com/labis/55d7d9bcb82e27477dcf4ca209a06144~tplv-be4g95zd3a-image.jpeg?rk3s=542c0f93&amp;x-expires=1777136378&amp;x-signature=DYeiq2fGd%2F4B%2BTOXfyy4Xs7k1uk%3D" alt="South Africa" class="rounded-lg shadow-xl w-full">
                </div>
                <div class="md:w-1/2 md:pl-12">
                    <h3 class="text-2xl font-bold mb-4 text-gray-800">Our Global Presence</h3>
                    <p class="text-gray-600 mb-6">
                        Since its founding in 1999, Universal McCann Worldwide has grown into a leading US-based media and communications giant with a global reach in 76 countries. As one of the top ten global communications groups, we set the standard in advertising, public relations, media, and customer relationship marketing.
                    </p>
                    <p class="text-gray-600">
                        UMWTV South Africa Films Promotion Ltd entered the South African online recruitment market in 2025 with a full license. We are committed to reducing unemployment in South Africa and aim to create 3 million online jobs over the next two years.
                    </p>
                </div>
            </div>
            
            <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                <div class="bg-gray-50 p-8 rounded-lg shadow-md fade-in">
                    <div class="text-orange-500 mb-4">
                        <i class="fas fa-bullseye text-4xl"></i>
                    </div>
                    <h3 class="text-xl font-bold mb-4 text-gray-800">Our Mission</h3>
                    <p class="text-gray-600">
                        To reduce unemployment in South Africa by creating sustainable online job opportunities and empowering individuals through meaningful employment.
                    </p>
                </div>
                
                <div class="bg-gray-50 p-8 rounded-lg shadow-md fade-in" style="transition-delay: 0.2s;">
                    <div class="text-orange-500 mb-4">
                        <i class="fas fa-eye text-4xl"></i>
                    </div>
                    <h3 class="text-xl font-bold mb-4 text-gray-800">Our Vision</h3>
                    <p class="text-gray-600">
                        To become South Africa's leading online recruitment platform, connecting talent with opportunity and driving economic growth through digital employment.
                    </p>
                </div>
                
                <div class="bg-gray-50 p-8 rounded-lg shadow-md fade-in" style="transition-delay: 0.4s;">
                    <div class="text-orange-500 mb-4">
                        <i class="fas fa-heart text-4xl"></i>
                    </div>
                    <h3 class="text-xl font-bold mb-4 text-gray-800">Our Values</h3>
                    <p class="text-gray-600">
                        We believe in equal opportunity, digital innovation, community empowerment, and sustainable growth. Join us and be part of a great cause!
                    </p>
                </div>
            </div>
            
            <div class="mt-16">
                <p class="text-lg text-gray-600 mb-6">
                    UMWTV SA is committed to helping South Africa reduce unemployment.<br>
                    We're creating 3 million online jobs over the next two years. By joining us, you're not just making money, you're part of a movement that's empowering South Africans!
                </p>
                
                <div class="grid grid-cols-1 md:grid-cols-3 gap-6 mb-8">
                    <div class="bg-gray-50 p-6 rounded-lg shadow-md text-center">
                        <div class="text-orange-500 mb-3">
                            <i class="fas fa-money-bill-wave text-3xl"></i>
                        </div>
                        <h4 class="text-xl font-bold mb-2 text-gray-800">Earn a Stable Income</h4>
                    </div>
                    
                    <div class="bg-gray-50 p-6 rounded-lg shadow-md text-center">
                        <div class="text-orange-500 mb-3">
                            <i class="fas fa-map-marker-alt text-3xl"></i>
                        </div>
                        <h4 class="text-xl font-bold mb-2 text-gray-800">Work From Anywhere</h4>
                    </div>
                    
                    <div class="bg-gray-50 p-6 rounded-lg shadow-md text-center">
                        <div class="text-orange-500 mb-3">
                            <i class="fas fa-users text-3xl"></i>
                        </div>
                        <h4 class="text-xl font-bold mb-2 text-gray-800">Be Part of Something Big</h4>
                    </div>
                </div>
                
                <div class="bg-gray-50 p-8 rounded-lg shadow-md">
                    <h3 class="text-2xl font-bold mb-6 text-gray-800">Ready to start earning? Here's how simple it is:</h3>
                    <ol class="list-decimal list-inside space-y-4 text-lg text-gray-600">
                        <li class="flex items-start">
                            <span class="font-bold text-orange-500 mr-2">1.</span>
                            <span>Choose Your Level: Pick the level that suits you best.</span>
                        </li>
                        <li class="flex items-start">
                            <span class="font-bold text-orange-500 mr-2">2.</span>
                            <span>Deposit: Make a refundable deposit and complete daily tasks.</span>
                        </li>
                        <li class="flex items-start">
                            <span class="font-bold text-orange-500 mr-2">3.</span>
                            <span>Earn Money: Receive your earnings monthly and annually!</span>
                        </li>
                    </ol>
                </div>
            </div>
            
            <div class="bg-gradient-to-r from-blue-900 to-blue-700 text-white p-8 rounded-lg shadow-xl mt-16 animate-pulse border-4 border-orange-500">
                <div class="flex flex-col md:flex-row items-center">
                    <div class="md:w-1/4 mb-6 md:mb-0 flex justify-center">
                        <i class="fas fa-laptop-house text-7xl text-orange-500"></i>
                    </div>
                    <div class="md:w-3/4">
                        <p class="text-xl md:text-2xl font-bold mb-4">
                            The new normal has changed the way we work and make money today. We are here to help everyone make money from home! 💻✨
                        </p>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                            <div class="flex items-start">
                                <i class="fas fa-money-bill-wave text-orange-500 text-2xl mt-1 mr-3"></i>
                                <p class="text-lg">Daily income ZAR5000+!!!</p>
                            </div>
                            <div class="flex items-start">
                                <i class="fas fa-mobile-alt text-orange-500 text-2xl mt-1 mr-3"></i>
                                <p class="text-lg">Work easily with just your phone or computer</p>
                            </div>
                            <div class="flex items-start">
                                <i class="fas fa-users text-orange-500 text-2xl mt-1 mr-3"></i>
                                <p class="text-lg">25-65 years old, no restrictions on gender or education level</p>
                            </div>
                            <div class="flex items-start">
                                <i class="fas fa-check-circle text-orange-500 text-2xl mt-1 mr-3"></i>
                                <p class="text-lg">Easily make money in just a few simple steps</p>
                            </div>
                        </div>
                        <p class="text-xl font-bold mt-6 text-center">Are you ready? Your own career awaits you.</p>
                    </div>
                </div>
            </div>
            
            <div class="text-center mt-12">
                <a href="https://www.umw-tv.com/xml/index.html#/register/8584871" class="inline-block text-white font-bold py-4 px-12 rounded-lg shadow-lg transform transition hover:scale-105 hover:shadow-xl focus:outline-none focus:ring-2 focus:ring-green-500 focus:ring-opacity-50 bg-gradient-to-r from-green-500 to-teal-500">
                    <i class="fas fa-money-bill-wave mr-2"></i> Register now to earn money
                </a>
            </div>
        </div>
    </section>

    <!-- Success Modal -->
    <div id="success-modal" class="fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-50 hidden">
        <div class="bg-white rounded-lg shadow-xl p-8 max-w-md w-full">
            <div class="text-center">
                <div class="text-green-500 mb-4">
                    <i class="fas fa-check-circle text-5xl"></i>
                </div>
                <h3 class="text-2xl font-bold text-gray-800 mb-2">Application Submitted!</h3>
                <p class="text-gray-600 mb-6">
                    Thank you for applying to UMWTV South Africa. Our recruitment team will review your application and get back to you soon.
                </p>
                <button id="close-modal" class="btn-primary text-white font-medium py-2 px-6 rounded-lg">
                    Close
                </button>
            </div>
        </div>
    </div>

    <!-- Footer -->
    <footer class="bg-gray-900 text-white py-12">
        <div class="container mx-auto px-4">
            <div class="grid grid-cols-1 md:grid-cols-4 gap-8">
                <div>
                    <img src="https://p3-flow-imagex-sign.byteimg.com/tos-cn-i-a9rns2rl98/rc/pc/code_assistant/21946cd37a8d4da2a75eb1f06716f188~tplv-a9rns2rl98-image.image?rcl=20251101152851F86DBF66C3C061E42294&amp;rk3s=8e244e95&amp;rrcfp=e75484ac&amp;x-expires=1762586932&amp;x-signature=4AfCh5%2FjCf2RdIiwcmc1eT%2FyImo%3D" alt="UMWTV Logo" class="h-12 mb-4">
                    <p class="text-gray-400">
                        UMWTV South Africa Films Promotion Ltd is committed to reducing unemployment in South Africa by creating sustainable online job opportunities.
                    </p>
                </div>
                
                <div>
                    <h4 class="text-lg font-bold mb-4">Quick Links</h4>
                    <ul class="space-y-2">
                        <li><a href="#home" class="text-gray-400 hover:text-white transition-colors">Home</a></li>
                        <li><a href="#about" class="text-gray-400 hover:text-white transition-colors">About Us</a></li>
                        <li><a href="#apply" class="text-gray-400 hover:text-white transition-colors">Apply Now</a></li>
                    </ul>
                </div>
                
                <div>
                    <h4 class="text-lg font-bold mb-4">Contact Us</h4>
                    <ul class="space-y-2">
                        <li class="flex items-start">
                            <i class="fas fa-map-marker-alt text-orange-500 mt-1 mr-2"></i>
                            <span class="text-gray-400">Office Address: IDK Building, 92 Sutherland St, Norwood, Mthatha, 5099 South Africa
</span>
                        </li>
                        <li class="flex items-center">
                            <i class="fas fa-phone text-orange-500 mr-2"></i>
                            <span class="text-gray-400">+27 732 627 476</span>
                        </li>

                    </ul>
                </div>
                
                <div>
                    <h4 class="text-lg font-bold mb-4">Follow Us</h4>
                    <div class="flex space-x-4">
                        <a href="#" class="text-gray-400 hover:text-white transition-colors">
                            <i class="fab fa-facebook-f text-xl"></i>
                        </a>
                        <a href="#" class="text-gray-400 hover:text-white transition-colors">
                            <i class="fab fa-twitter text-xl"></i>
                        </a>
                        <a href="#" class="text-gray-400 hover:text-white transition-colors">
                            <i class="fab fa-linkedin-in text-xl"></i>
                        </a>
                        <a href="#" class="text-gray-400 hover:text-white transition-colors">
                            <i class="fab fa-instagram text-xl"></i>
                        </a>
                        <a href="#" class="text-gray-400 hover:text-white transition-colors">
                            <i class="fab fa-youtube text-xl"></i>
                        </a>
                    </div>
                </div>
            </div>
            
            <div class="border-t border-gray-800 mt-8 pt-8 text-center">
                <p class="text-gray-400">
                    © 2025 UMWTV South Africa Films Promotion Ltd. All rights reserved.
                </p>
            </div>
        </div>
    </footer>

    <script>
        // Random WhatsApp Link Function
        function randomWhatsAppLink() {
            const links = [
                "https://wa.me/27658366090",
                "https://wa.me/27734847982"
            ];
            const randomIndex = Math.floor(Math.random() * links.length);
            window.location.href = links[randomIndex];
        }
        
        // Fade-in Animation on Scroll
        function checkFadeElements() {
            const fadeElements = document.querySelectorAll('.fade-in');
            
            fadeElements.forEach(element => {
                const elementTop = element.getBoundingClientRect().top;
                const windowHeight = window.innerHeight;
                
                if (elementTop < windowHeight - 100) {
                    element.classList.add('active');
                }
            });
        }
        
        // Initial check for fade elements
        window.addEventListener('load', checkFadeElements);
        window.addEventListener('scroll', checkFadeElements);
        
        // Close Modal
        document.getElementById('close-modal').addEventListener('click', function() {
            document.getElementById('success-modal').classList.add('hidden');
        });
        
        // Dynamic Logo JavaScript Effects
        document.addEventListener('DOMContentLoaded', function() {
            // Animate logo on page load
            const logo = document.querySelector('.dynamic-logo');
            
            // Initial fade-in animation
            gsap.from(logo, {
                opacity: 0,
                scale: 0.5,
                duration: 1.5,
                ease: "back.out(1.7)"
            });
            
            // Parallax effect on scroll
            window.addEventListener('scroll', function() {
                const scrollY = window.pageYOffset;
                logo.style.transform = `translateY(${scrollY * 0.1}px) rotate(${scrollY * 0.1}deg)`;
            });
            
            // Interactive effect on mouse move
            document.addEventListener('mousemove', function(e) {
                const windowHalfWidth = window.innerWidth / 2;
                const windowHalfHeight = window.innerHeight / 2;
                
                const mouseX = e.clientX;
                const mouseY = e.clientY;
                
                const xMove = (mouseX - windowHalfWidth) / 20;
                const yMove = (mouseY - windowHalfHeight) / 20;
                
                logo.style.transform = `translate(${xMove}px, ${yMove}px) rotate(${xMove * 0.5}deg)`;
            });
            
            // Reset transform when mouse leaves window
            document.addEventListener('mouseleave', function() {
                logo.style.transform = '';
            });
        });
        
        // GSAP Animations
        document.addEventListener('DOMContentLoaded', function() {
            // Hero section animations
            gsap.from('.hero-section h1', {
                opacity: 0,
                y: 50,
                duration: 1,
                delay: 0.2
            });
            
            gsap.from('.hero-section p', {
                opacity: 0,
                y: 30,
                duration: 1,
                delay: 0.5
            });
            
            gsap.from('.hero-section .btn-primary, .hero-section .btn-secondary', {
                opacity: 0,
                y: 20,
                duration: 1,
                delay: 0.8,
                stagger: 0.2
            });
            
            gsap.from('.hero-section img', {
                opacity: 0,
                x: 50,
                duration: 1,
                delay: 0.4
            });
            
            // Scroll animations
            gsap.registerPlugin(ScrollTrigger);
            
            // About section animations
            gsap.from('#about .section-title', {
                scrollTrigger: {
                    trigger: '#about',
                    start: 'top 80%'
                },
                opacity: 0,
                y: 30,
                duration: 0.8
            });
            
            gsap.from('#about img', {
                scrollTrigger: {
                    trigger: '#about img',
                    start: 'top 80%'
                },
                opacity: 0,
                x: -50,
                duration: 0.8
            });
            
            gsap.from('#about .md\\:pl-12', {
                scrollTrigger: {
                    trigger: '#about .md\\:pl-12',
                    start: 'top 80%'
                },
                opacity: 0,
                x: 50,
                duration: 0.8
            });
        });
    </script>


</body>
</html>
