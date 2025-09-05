<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>EduSync - Agenda Acadêmica</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #4f46e5;
            --secondary: #10b981;
            --dark: #1e293b;
            --light: #f8fafc;
        }
        
        body {
            font-family: 'Inter', sans-serif;
            background-color: #f1f5f9;
        }
        
        .gradient-bg {
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
        }
        
        .card-shadow {
            box-shadow: 0 10px 25px -5px rgba(0, 0, 0, 0.1), 0 10px 10px -5px rgba(0, 0, 0, 0.04);
        }
        
        .input-field {
            transition: all 0.3s ease;
            border: 2px solid #e2e8f0;
        }
        
        .input-field:focus {
            border-color: var(--primary);
            box-shadow: 0 0 0 3px rgba(79, 70, 229, 0.2);
        }
        
        .btn-primary {
            background-color: var(--primary);
            transition: all 0.3s ease;
        }
        
        .btn-primary:hover {
            background-color: #4338ca;
            transform: translateY(-2px);
        }
        
        .btn-secondary {
            background-color: var(--secondary);
            transition: all 0.3s ease;
        }
        
        .btn-secondary:hover {
            background-color: #0d9488;
            transform: translateY(-2px);
        }
        
        .floating {
            animation: floating 3s ease-in-out infinite;
        }
        
        @keyframes floating {
            0% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
            100% { transform: translateY(0px); }
        }
        
        .tab-active {
            border-bottom: 3px solid var(--primary);
            color: var(--primary);
            font-weight: 600;
        }
    </style>
</head>
<body>
    <div class="min-h-screen flex flex-col">
        <!-- Header -->
        <header class="gradient-bg text-white py-6">
            <div class="container mx-auto px-4 flex justify-between items-center">
                <div class="flex items-center space-x-2">
                    <i class="fas fa-calendar-alt text-3xl"></i>
                    <h1 class="text-2xl font-bold">EduSync</h1>
                </div>
                <nav class="hidden md:flex space-x-6">
                    <a href="#" class="hover:text-gray-200 transition">Sobre</a>
                    <a href="#" class="hover:text-gray-200 transition">Recursos</a>
                    <a href="#" class="hover:text-gray-200 transition">Contato</a>
                </nav>
                <button class="md:hidden text-2xl">
                    <i class="fas fa-bars"></i>
                </button>
            </div>
        </header>

        <!-- Main Content -->
        <main class="flex-grow flex items-center justify-center py-12 px-4">
            <div class="container mx-auto flex flex-col lg:flex-row items-center justify-center gap-12">
                <!-- Hero Section -->
                <div class="lg:w-1/2 text-center lg:text-left">
                    <h2 class="text-4xl md:text-5xl font-bold text-gray-800 mb-6">Gestão Acadêmica <span class="text-indigo-600">Simplificada</span></h2>
                    <p class="text-lg text-gray-600 mb-8 max-w-lg mx-auto lg:mx-0">
                        A plataforma perfeita para professores e alunos organizarem suas atividades acadêmicas ao longo do ano.
                    </p>
                    <div class="relative w-full max-w-lg mx-auto lg:mx-0 h-64 bg-white rounded-xl card-shadow p-4 hidden lg:block">
                        <div class="absolute -top-4 -left-4 bg-indigo-100 rounded-lg p-4 w-24 h-24 flex items-center justify-center">
                            <i class="fas fa-chalkboard-teacher text-indigo-600 text-3xl"></i>
                        </div>
                        <div class="absolute -bottom-4 -right-4 bg-emerald-100 rounded-lg p-4 w-24 h-24 flex items-center justify-center">
                            <i class="fas fa-user-graduate text-emerald-600 text-3xl"></i>
                        </div>
                        <div class="absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 bg-white rounded-full w-32 h-32 flex items-center justify-center card-shadow floating">
                            <i class="fas fa-sync-alt text-indigo-600 text-4xl"></i>
                        </div>
                    </div>
                </div>

                <!-- Auth Card -->
                <div class="lg:w-1/2 max-w-md w-full">
                    <div class="bg-white rounded-xl card-shadow overflow-hidden">
                        <!-- Tabs -->
                        <div class="flex border-b">
                            <button id="login-tab" class="flex-1 py-4 px-6 text-center font-medium tab-active">
                                <i class="fas fa-sign-in-alt mr-2"></i> Login
                            </button>
                            <button id="register-tab" class="flex-1 py-4 px-6 text-center font-medium text-gray-500">
                                <i class="fas fa-user-plus mr-2"></i> Cadastro
                            </button>
                        </div>

                        <!-- Login Form -->
                        <div id="login-form" class="p-6">
                            <div class="mb-6">
                                <label for="login-email" class="block text-gray-700 mb-2">E-mail</label>
                                <input type="email" id="login-email" class="w-full px-4 py-3 rounded-lg input-field" placeholder="seu@email.com">
                            </div>
                            <div class="mb-6">
                                <label for="login-password" class="block text-gray-700 mb-2">Senha</label>
                                <input type="password" id="login-password" class="w-full px-4 py-3 rounded-lg input-field" placeholder="••••••••">
                            </div>
                            <div class="flex items-center justify-between mb-6">
                                <div class="flex items-center">
                                    <input type="checkbox" id="remember-me" class="h-4 w-4 text-indigo-600 focus:ring-indigo-500 border-gray-300 rounded">
                                    <label for="remember-me" class="ml-2 block text-sm text-gray-700">Lembrar-me</label>
                                </div>
                                <a href="#" class="text-sm text-indigo-600 hover:text-indigo-500">Esqueceu a senha?</a>
                            </div>
                            <button class="w-full py-3 px-4 rounded-lg text-white font-medium btn-primary mb-4">
                                <i class="fas fa-sign-in-alt mr-2"></i> Entrar
                            </button>
                            <div class="text-center text-sm text-gray-500">
                                Ou entre com
                            </div>
                            <div class="flex justify-center space-x-4 mt-4">
                                <button class="w-10 h-10 rounded-full bg-blue-600 text-white flex items-center justify-center">
                                    <i class="fab fa-facebook-f"></i>
                                </button>
                                <button class="w-10 h-10 rounded-full bg-red-600 text-white flex items-center justify-center">
                                    <i class="fab fa-google"></i>
                                </button>
                                <button class="w-10 h-10 rounded-full bg-gray-800 text-white flex items-center justify-center">
                                    <i class="fab fa-microsoft"></i>
                                </button>
                            </div>
                        </div>

                        <!-- Register Form -->
                        <div id="register-form" class="p-6 hidden">
                            <div class="mb-4">
                                <label class="block text-gray-700 mb-2">Tipo de Usuário</label>
                                <div class="flex space-x-4">
                                    <button class="flex-1 py-2 px-4 rounded-lg border-2 border-gray-200 text-gray-700 font-medium hover:border-indigo-500 hover:text-indigo-600 transition">
                                        <i class="fas fa-user-graduate mr-2"></i> Aluno
                                    </button>
                                    <button class="flex-1 py-2 px-4 rounded-lg border-2 border-gray-200 text-gray-700 font-medium hover:border-indigo-500 hover:text-indigo-600 transition">
                                        <i class="fas fa-chalkboard-teacher mr-2"></i> Professor
                                    </button>
                                </div>
                            </div>
                            <div class="mb-4">
                                <label for="register-name" class="block text-gray-700 mb-2">Nome Completo</label>
                                <input type="text" id="register-name" class="w-full px-4 py-3 rounded-lg input-field" placeholder="Seu nome completo">
                            </div>
                            <div class="mb-4">
                                <label for="register-email" class="block text-gray-700 mb-2">E-mail</label>
                                <input type="email" id="register-email" class="w-full px-4 py-3 rounded-lg input-field" placeholder="seu@email.com">
                            </div>
                            <div class="mb-4">
                                <label for="register-password" class="block text-gray-700 mb-2">Senha</label>
                                <input type="password" id="register-password" class="w-full px-4 py-3 rounded-lg input-field" placeholder="••••••••">
                            </div>
                            <div class="mb-6">
                                <label for="register-confirm-password" class="block text-gray-700 mb-2">Confirmar Senha</label>
                                <input type="password" id="register-confirm-password" class="w-full px-4 py-3 rounded-lg input-field" placeholder="••••••••">
                            </div>
                            <div class="flex items-center mb-6">
                                <input type="checkbox" id="terms" class="h-4 w-4 text-indigo-600 focus:ring-indigo-500 border-gray-300 rounded">
                                <label for="terms" class="ml-2 block text-sm text-gray-700">
                                    Concordo com os <a href="#" class="text-indigo-600 hover:text-indigo-500">Termos de Serviço</a> e <a href="#" class="text-indigo-600 hover:text-indigo-500">Política de Privacidade</a>
                                </label>
                            </div>
                            <button class="w-full py-3 px-4 rounded-lg text-white font-medium btn-secondary">
                                <i class="fas fa-user-plus mr-2"></i> Criar Conta
                            </button>
                        </div>
                    </div>
                </div>
            </div>
        </main>

        <!-- Footer -->
        <footer class="bg-white py-8 border-t border-gray-200">
            <div class="container mx-auto px-4">
                <div class="flex flex-col md:flex-row justify-between items-center">
                    <div class="flex items-center space-x-2 mb-4 md:mb-0">
                        <i class="fas fa-calendar-alt text-indigo-600 text-xl"></i>
                        <span class="text-lg font-semibold text-gray-800">EduSync</span>
                    </div>
                    <div class="flex space-x-6">
                        <a href="#" class="text-gray-600 hover:text-indigo-600 transition"><i class="fab fa-facebook-f"></i></a>
                        <a href="#" class="text-gray-600 hover:text-indigo-600 transition"><i class="fab fa-twitter"></i></a>
                        <a href="#" class="text-gray-600 hover:text-indigo-600 transition"><i class="fab fa-instagram"></i></a>
                        <a href="#" class="text-gray-600 hover:text-indigo-600 transition"><i class="fab fa-linkedin-in"></i></a>
                    </div>
                </div>
                <div class="mt-6 text-center md:text-left text-sm text-gray-500">
                    © 2023 EduSync. Todos os direitos reservados.
                </div>
            </div>
        </footer>
    </div>

    <script>
        // Tab switching functionality
        const loginTab = document.getElementById('login-tab');
        const registerTab = document.getElementById('register-tab');
        const loginForm = document.getElementById('login-form');
        const registerForm = document.getElementById('register-form');

        loginTab.addEventListener('click', () => {
            loginTab.classList.add('tab-active');
            loginTab.classList.remove('text-gray-500');
            registerTab.classList.remove('tab-active');
            registerTab.classList.add('text-gray-500');
            loginForm.classList.remove('hidden');
            registerForm.classList.add('hidden');
        });

        registerTab.addEventListener('click', () => {
            registerTab.classList.add('tab-active');
            registerTab.classList.remove('text-gray-500');
            loginTab.classList.remove('tab-active');
            loginTab.classList.add('text-gray-500');
            registerForm.classList.remove('hidden');
            loginForm.classList.add('hidden');
        });

        // Simulate form submission
        document.querySelector('#login-form button').addEventListener('click', (e) => {
            e.preventDefault();
            const email = document.getElementById('login-email').value;
            const password = document.getElementById('login-password').value;
            
            if(email && password) {
                window.location.href = 'calendarioescolar.html';
            } else {
                alert('Por favor, preencha todos os campos!');
            }
        });

        document.querySelector('#register-form button').addEventListener('click', (e) => {
            e.preventDefault();
            const name = document.getElementById('register-name').value;
            const email = document.getElementById('register-email').value;
            const password = document.getElementById('register-password').value;
            const confirmPassword = document.getElementById('register-confirm-password').value;
            const terms = document.getElementById('terms').checked;
            
            if(!name || !email || !password || !confirmPassword) {
                alert('Por favor, preencha todos os campos!');
                return;
            }
            
            if(password !== confirmPassword) {
                alert('As senhas não coincidem!');
                return;
            }
            
            if(!terms) {
                alert('Você deve aceitar os termos de serviço!');
                return;
            }
            
            alert('Conta criada com sucesso!');
            setTimeout(() => {
                window.location.href = 'calendarioescolar.html';
            }, 1000); // 1 segundo de espera
        });
    </script>
</body>

</html>
