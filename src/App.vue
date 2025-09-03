<template>
  <div class="min-h-screen bg-gradient-to-br from-dark-900 via-dark-800 to-primary-900 text-white overflow-x-hidden">
    <!-- Navigation -->
    <nav class="fixed top-0 left-0 right-0 z-50 glass-dark transition-all duration-300" :class="{ 'bg-dark-900/80': scrolled }">
      <div class="container-custom">
        <div class="flex items-center justify-between py-4">
          <div class="text-2xl font-bold gradient-text">Gabriel</div>
          <div class="hidden md:flex space-x-8">
            <a href="#home" class="hover:text-primary-400 transition-colors duration-300">Início</a>
            <a href="#about" class="hover:text-primary-400 transition-colors duration-300">Sobre</a>
            <a href="#skills" class="hover:text-primary-400 transition-colors duration-300">Skills</a>
            <a href="#projects" class="hover:text-primary-400 transition-colors duration-300">Projetos</a>
            <a href="#contact" class="hover:text-primary-400 transition-colors duration-300">Contato</a>
          </div>
          <button @click="toggleMobileMenu" class="md:hidden">
            <Menu v-if="!mobileMenuOpen" :size="24" />
            <X v-else :size="24" />
          </button>
        </div>
      </div>
      
      <!-- Mobile Menu -->
      <div v-if="mobileMenuOpen" class="md:hidden glass-dark border-t border-white/10">
        <div class="container-custom py-4 space-y-4">
          <a href="#home" @click="closeMobileMenu" class="block hover:text-primary-400 transition-colors duration-300">Início</a>
          <a href="#about" @click="closeMobileMenu" class="block hover:text-primary-400 transition-colors duration-300">Sobre</a>
          <a href="#skills" @click="closeMobileMenu" class="block hover:text-primary-400 transition-colors duration-300">Skills</a>
          <a href="#projects" @click="closeMobileMenu" class="block hover:text-primary-400 transition-colors duration-300">Projetos</a>
          <a href="#contact" @click="closeMobileMenu" class="block hover:text-primary-400 transition-colors duration-300">Contato</a>
        </div>
      </div>
    </nav>

    <!-- Hero Section -->
    <section id="home" class="min-h-screen flex items-center justify-center relative overflow-hidden">
      <!-- Animated Background Elements -->
      <div class="absolute inset-0">
        <div class="absolute top-20 left-10 w-72 h-72 bg-primary-500/20 rounded-full blur-3xl animate-float"></div>
        <div class="absolute bottom-20 right-10 w-96 h-96 bg-primary-400/10 rounded-full blur-3xl animate-float" style="animation-delay: -3s;"></div>
        <div class="absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 w-64 h-64 bg-primary-600/15 rounded-full blur-3xl animate-float" style="animation-delay: -1.5s;"></div>
      </div>
      
      <div class="container-custom text-center relative z-10">
        <div class="animate-slide-down">
          <!-- Profile Image -->
          <div class="w-40 h-40 mx-auto mb-8 relative">
            <div class="w-full h-full rounded-full overflow-hidden border-4 border-primary-400/50 shadow-2xl animate-glow">
              <img :src="profileImage" alt="Gabriel Rocha" class="w-full h-full object-cover" />
            </div>
            <div class="absolute -inset-1 bg-gradient-to-r from-primary-400 to-primary-600 rounded-full opacity-50 animate-pulse"></div>
          </div>
          
          <h1 class="text-5xl md:text-7xl font-bold mb-6 animate-slide-up">
            Olá, eu sou <span class="gradient-text">Gabriel</span>
          </h1>
          
          <p class="text-xl md:text-2xl text-gray-300 mb-4 animate-slide-up" style="animation-delay: 0.2s;">
            Desenvolvedor Full Stack
          </p>
          
          <p class="text-lg text-gray-400 max-w-2xl mx-auto mb-8 animate-slide-up" style="animation-delay: 0.4s;">
            {{ personalInfo.objective }}
          </p>
          
          <div class="flex flex-wrap justify-center gap-4 animate-slide-up" style="animation-delay: 0.6s;">
            <a href="#projects" class="btn-primary">
              <Briefcase :size="20" class="inline mr-2" />
              Ver Projetos
            </a>
            <a href="#contact" class="btn-secondary">
              <MessageCircle :size="20" class="inline mr-2" />
              Entrar em Contato
            </a>
          </div>
          
          <!-- Social Links -->
          <div class="flex justify-center space-x-6 mt-12 animate-slide-up" style="animation-delay: 0.8s;">
            <a :href="personalInfo.github" target="_blank" class="p-3 glass rounded-full hover:bg-white/20 transition-all duration-300 hover:scale-110">
              <Github :size="24" />
            </a>
            <a :href="personalInfo.linkedin" target="_blank" class="p-3 glass rounded-full hover:bg-white/20 transition-all duration-300 hover:scale-110">
              <Linkedin :size="24" />
            </a>
            <a :href="`mailto:${personalInfo.email}`" class="p-3 glass rounded-full hover:bg-white/20 transition-all duration-300 hover:scale-110">
              <Mail :size="24" />
            </a>
          </div>
        </div>
      </div>
      
      <!-- Scroll Indicator -->
      <div class="absolute bottom-8 left-1/2 transform -translate-x-1/2 animate-bounce">
        <ChevronDown :size="32" class="text-primary-400" />
      </div>
    </section>

    <!-- About Section -->
    <section id="about" class="section-padding">
      <div class="container-custom">
        <div class="text-center mb-16">
          <h2 class="text-4xl md:text-5xl font-bold mb-4 gradient-text">Sobre Mim</h2>
          <p class="text-gray-400 text-lg max-w-2xl mx-auto">
            Conheça um pouco mais sobre minha jornada e experiência
          </p>
        </div>
        
        <div class="grid md:grid-cols-2 gap-12 items-center">
          <div class="space-y-6">
            <div class="card">
              <div class="flex items-center mb-4">
                <User :size="24" class="text-primary-400 mr-3" />
                <h3 class="text-xl font-semibold">Informações Pessoais</h3>
              </div>
              <div class="space-y-3 text-gray-300">
                <div class="flex items-center">
                  <Phone :size="16" class="text-primary-400 mr-3" />
                  <span>{{ personalInfo.phone }}</span>
                </div>
                <div class="flex items-center">
                  <Mail :size="16" class="text-primary-400 mr-3" />
                  <span>{{ personalInfo.email }}</span>
                </div>
                <div class="flex items-center">
                  <MapPin :size="16" class="text-primary-400 mr-3" />
                  <span>{{ personalInfo.address }}</span>
                </div>
                <div class="flex items-center">
                  <Calendar :size="16" class="text-primary-400 mr-3" />
                  <span>{{ personalInfo.birthDate }}</span>
                </div>
              </div>
            </div>
            
            <div class="card">
              <div class="flex items-center mb-4">
                <Languages :size="24" class="text-primary-400 mr-3" />
                <h3 class="text-xl font-semibold">Idiomas</h3>
              </div>
              <div class="space-y-2">
                <div v-for="(lang, index) in personalInfo.languages" :key="index" class="text-gray-300">
                  {{ lang }}
                </div>
              </div>
            </div>
          </div>
          
          <div class="space-y-6">
            <div class="card">
              <div class="flex items-center mb-4">
                <GraduationCap :size="24" class="text-primary-400 mr-3" />
                <h3 class="text-xl font-semibold">Formação</h3>
              </div>
              <div class="space-y-4">
                <div>
                  <h4 class="font-medium text-white">{{ personalInfo.education }}</h4>
                  <p class="text-gray-400">{{ personalInfo.institution }}</p>
                </div>
                <div>
                  <h4 class="font-medium text-white mb-2">Cursos</h4>
                  <div class="space-y-1">
                    <div v-for="(course, index) in personalInfo.courses" :key="index" class="text-gray-300 text-sm">
                      {{ course }}
                    </div>
                  </div>
                </div>
              </div>
            </div>
            
            <div class="card">
              <div class="flex items-center mb-4">
                <Award :size="24" class="text-primary-400 mr-3" />
                <h3 class="text-xl font-semibold">Experiência Adicional</h3>
              </div>
              <p class="text-gray-300">Robótica (KIT EV3)</p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Skills Section -->
    <section id="skills" class="section-padding bg-black/20">
      <div class="container-custom">
        <div class="text-center mb-16">
          <h2 class="text-4xl md:text-5xl font-bold mb-4 gradient-text">Tecnologias</h2>
          <p class="text-gray-400 text-lg max-w-2xl mx-auto">
            Ferramentas e tecnologias que utilizo no desenvolvimento
          </p>
        </div>
        
        <div class="grid grid-cols-2 md:grid-cols-4 lg:grid-cols-6 gap-6">
          <div v-for="(tech, index) in personalInfo.technologies" :key="index" 
               class="card text-center group cursor-pointer"
               :style="{ animationDelay: `${index * 0.1}s` }">
            <div class="w-12 h-12 mx-auto mb-3 bg-gradient-to-r from-primary-400 to-primary-600 rounded-lg flex items-center justify-center group-hover:scale-110 transition-transform duration-300">
              <div v-html="getTechIconHTML(tech)"></div>
            </div>
            <span class="text-sm font-medium">{{ tech }}</span>
          </div>
        </div>
      </div>
    </section>

    <!-- Projects Section -->
    <section id="projects" class="section-padding">
      <div class="container-custom">
        <div class="text-center mb-16">
          <h2 class="text-4xl md:text-5xl font-bold mb-4 gradient-text">Projetos</h2>
          <p class="text-gray-400 text-lg max-w-2xl mx-auto">
            Alguns dos projetos que desenvolvi
          </p>
        </div>
        
        <div class="grid md:grid-cols-2 gap-8">
          <div v-for="project in projects" :key="project.id" 
               class="card group overflow-hidden">
            <div class="relative overflow-hidden rounded-xl mb-6">
              <img :src="project.image" :alt="project.title" 
                   class="w-full h-48 object-cover group-hover:scale-110 transition-transform duration-500" />
              <div class="absolute inset-0 bg-gradient-to-t from-black/60 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300"></div>
            </div>
            
            <h3 class="text-xl font-semibold mb-3">{{ project.title }}</h3>
            <p class="text-gray-400 mb-4 leading-relaxed">{{ project.description }}</p>
            
            <div class="mb-4">
              <h4 class="text-sm font-medium text-primary-400 mb-2">Tecnologias</h4>
              <div class="flex flex-wrap gap-2">
                <span v-for="(tech, index) in project.technologies" :key="index" 
                      class="px-3 py-1 bg-primary-500/20 text-primary-300 rounded-full text-xs border border-primary-500/30">
                  {{ tech }}
                </span>
              </div>
            </div>
            
            <div class="mb-6">
              <h4 class="text-sm font-medium text-primary-400 mb-2">Funcionalidades</h4>
              <ul class="space-y-1">
                <li v-for="(feature, index) in project.features" :key="index" 
                    class="text-gray-400 text-sm flex items-center">
                  <div class="w-1.5 h-1.5 bg-primary-400 rounded-full mr-2"></div>
                  {{ feature }}
                </li>
              </ul>
            </div>
            
            <a :href="project.link" target="_blank" class="btn-primary w-full group">
              <ExternalLink :size="16" class="inline mr-2 group-hover:translate-x-1 transition-transform duration-300" />
              Ver Projeto
            </a>
          </div>
        </div>
      </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="section-padding bg-black/20">
      <div class="container-custom">
        <div class="text-center mb-16">
          <h2 class="text-4xl md:text-5xl font-bold mb-4 gradient-text">Vamos Trabalhar Juntos?</h2>
          <p class="text-gray-400 text-lg max-w-2xl mx-auto">
            Estou sempre aberto a novas oportunidades e desafios. Entre em contato!
          </p>
        </div>
        
        <div class="max-w-4xl mx-auto">
          <div class="grid md:grid-cols-3 gap-8 mb-12">
            <div class="card text-center">
              <div class="w-16 h-16 mx-auto mb-4 bg-gradient-to-r from-primary-400 to-primary-600 rounded-full flex items-center justify-center">
                <Mail :size="24" class="text-white" />
              </div>
              <h3 class="font-semibold mb-2">Email</h3>
              <p class="text-gray-400 text-sm">{{ personalInfo.email }}</p>
            </div>
            
            <div class="card text-center">
              <div class="w-16 h-16 mx-auto mb-4 bg-gradient-to-r from-primary-400 to-primary-600 rounded-full flex items-center justify-center">
                <Phone :size="24" class="text-white" />
              </div>
              <h3 class="font-semibold mb-2">Telefone</h3>
              <p class="text-gray-400 text-sm">{{ personalInfo.phone }}</p>
            </div>
            
            <div class="card text-center">
              <div class="w-16 h-16 mx-auto mb-4 bg-gradient-to-r from-primary-400 to-primary-600 rounded-full flex items-center justify-center">
                <MapPin :size="24" class="text-white" />
              </div>
              <h3 class="font-semibold mb-2">Localização</h3>
              <p class="text-gray-400 text-sm">Paranaguá, PR</p>
            </div>
          </div>
          
          <div class="flex flex-wrap justify-center gap-6">
            <a :href="`mailto:${personalInfo.email}`" class="btn-primary">
              <Mail :size="20" class="inline mr-2" />
              Enviar Email
            </a>
            <a :href="personalInfo.linkedin" target="_blank" class="btn-secondary">
              <Linkedin :size="20" class="inline mr-2" />
              LinkedIn
            </a>
            <a :href="personalInfo.github" target="_blank" class="btn-secondary">
              <Github :size="20" class="inline mr-2" />
              GitHub
            </a>
          </div>
        </div>
      </div>
    </section>

    <!-- Footer -->
    <footer class="py-12 border-t border-white/10">
      <div class="container-custom text-center">
        <p class="text-gray-400 mb-2">
          © 2025 Gabriel Francisco Rocha. Todos os direitos reservados.
        </p>
        <p class="text-gray-500 text-sm">
          Desenvolvido com Vue.js, Tailwind CSS e muito ☕
        </p>
      </div>
    </footer>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import { 
  Github, Linkedin, Mail, Phone, MapPin, Calendar, Languages, Code, 
  ExternalLink, User, GraduationCap, Award, Briefcase, MessageCircle,
  ChevronDown, Menu, X
} from 'lucide-vue-next'
import profileImage from './assets/profile.png'
import weatherAppImage from './assets/weather-app.png'
import techNewsImage from './assets/tech-news.png'

const scrolled = ref(false)
const mobileMenuOpen = ref(false)

const getTechIconClass = (tech) => {
  const iconMap = {
    // Linguagens de Programação
    "C": "devicon-c-original",
    "C#": "devicon-csharp-plain", 
    "C++": "devicon-cplusplus-plain",
    "Javascript": "devicon-javascript-plain",
    "Python": "devicon-python-plain",
    "PHP": "devicon-php-plain",
    
    // Frameworks e Bibliotecas Frontend
    "Vue.js": "devicon-vuejs-plain",
    "Angular": "devicon-angular-plain",
    "React": "devicon-react-original",
    "HTML": "devicon-html5-plain",
    "CSS": "devicon-css3-plain",
    
    // Frameworks Backend
    "Springboot": "devicon-spring-original",
    
    // Banco de Dados e Stacks
    "SQL": "devicon-mysql-original",
    "MERN e MEAN": "devicon-mysql-original", // Usando MySQL como representação de stack
  };
  
  return iconMap[tech] || "devicon-code-original";
};

const getTechIconHTML = (tech) => {
  const iconClass = getTechIconClass(tech);
  return `<i class="${iconClass}" style="font-size: 24px; color: white;"></i>`;
};

const personalInfo = ref({
  name: "Gabriel Francisco Rocha",
  title: "Desenvolvedor",
  email: "gabrielfrocha35953@gmail.com",
  phone: "+55 (41) 98410-8137",
  address: "Bockmann, Miguel Nicoláu Anastácio, N°79 – Paranaguá – Paraná",
  birthDate: "22/02/2005",
  maritalStatus: "Solteiro",
  github: "https://github.com/dev-Gabe",
  linkedin: "https://www.linkedin.com/in/gabriel-francisco-rocha-351174255/",
  education: "6° Período, Faculdade de Sistemas de Informação – Noite – Cursando",
  institution: "Instituto Superior do Litoral do Paraná",
  languages: ["Inglês (Avançado)", "Espanhol (Básico)"],
  technologies: ["C", "C#", "C++", "Javascript", "Vue.js", "Angular", "React", "HTML", "CSS", "Python", "Springboot", "SQL", "MERN e MEAN", "PHP"],
  courses: ["Alura – Cursando", "Talentos Brasil(Informática)"],
  objective: "Busco oportunidade como Desenvolvedor, aplicando meus conhecimentos em programação e contribuindo para o crescimento da empresa, enquanto desenvolvo minhas habilidades técnicas e profissionais.",
});

const projects = ref([
  {
    id: 1,
    title: "Weather App",
    image: weatherAppImage,
    description: "Aplicativo de previsão do tempo desenvolvido com Vue.js, mostrando informações meteorológicas detalhadas incluindo temperatura, umidade e pressão atmosférica.",
    technologies: ["React", "JavaScript", "CSS", "API Weather"],
    features: [
      "Busca por cidade",
      "Previsão de 5 dias",
      "Dados em tempo real",
      "Interface responsiva",
    ],
    link: "https://github.com/dev-Gabe/WeatherApp",
  },
  {
    id: 2,
    title: "TechNews Portal",
    image: techNewsImage,
    description: "Portal de notícias de tecnologia com sistema de categorização, busca avançada e interface moderna para acompanhar as últimas novidades do mundo tech.",
    technologies: ["JavaScript", "CSS", "API News"],
    features: [
      "Categorização de notícias",
      "Sistema de busca",
      "Interface responsiva",
      "Atualizações em tempo real",
    ],
    link: "https://github.com/dev-Gabe/TechNewsWebSite",
  },
]);
const closeMobileMenu = () => {
  mobileMenuOpen.value = false
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>
