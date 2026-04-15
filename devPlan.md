# Meu Plano de Desenvolvimento do Portfólio Moderno em Vue.js

Este documento detalha meu planejamento e as decisões que tomei durante o desenvolvimento do meu novo portfólio, com foco em um design moderno e utilizando tecnologias atuais.

## 1. Minha Análise e Requisitos Iniciais

**Meu Objetivo:** Eu queria criar um portfólio visualmente atraente e funcional que destacasse minhas habilidades e projetos, e decidi que o Vue.js seria a tecnologia ideal para isso.

**Meu Feedback sobre o Projeto Anterior:** Eu não fiquei satisfeito com o design do portfólio anterior em Vue.js. Ele não transmitia a imagem profissional e moderna que eu buscava, então pedi um novo com um "design moderno" que realmente me representasse.

**Informações e Assets que Utilizei:**
- Meu currículo (para minhas informações pessoais, formação, idiomas, tecnologias e objetivo profissional).
- As imagens dos meus projetos anteriores (Weather App e TechNews Portal).
- Minha foto de perfil.

## 2. Minhas Escolhas de Tecnologias e Ferramentas

Para garantir que o portfólio tivesse um "design moderno" e para otimizar o processo de desenvolvimento, escolhi as seguintes tecnologias:

-   **Framework:** Vue.js 3, utilizando a Composition API para organizar meu código de forma reativa e eficiente.
-   **Estilização:** Tailwind CSS, que me permite desenvolver de forma rápida e criar um design responsivo com foco em utilitários.
-   **Build Tool:** Vite, para ter um ambiente de desenvolvimento rápido e otimizado para a versão final do site.
-   **Linguagem:** TypeScript, para adicionar tipagem estática ao meu código, o que ajuda na manutenibilidade e escalabilidade.
-   **Ícones:** Lucide Vue, para ter ícones modernos e que eu pudesse personalizar facilmente.

## 3. Meu Planejamento de Design e Estrutura

Com base no meu desejo por um design moderno, planejei o visual do meu portfólio da seguinte forma:

-   **Paleta de Cores:** Optei por tons escuros (azul-marinho, cinza escuro) como base, com toques vibrantes de azul e roxo em gradientes para dar um ar mais dinâmico.
-   **Tipografia:** Escolhi fontes limpas e modernas para garantir boa legibilidade e uma estética agradável.
-   **Efeitos Visuais:**
    -   **Glassmorphism:** Decidi usar esse efeito em cards e na navegação para um visual translúcido e elegante.
    -   **Gradientes Dinâmicos:** Incorporei gradientes animados em fundos e elementos para adicionar profundidade e movimento.
    -   **Animações Suaves:** Planejei transições e micro-interações em botões, cards e links para uma experiência de usuário fluida e agradável.
    -   **Efeito Glow na Minha Foto de Perfil:** Queria um brilho sutil ao redor da minha foto para destacá-la, mas depois ajustei para que a foto ficasse mais visível, sem excesso de brilho.
-   **Layout Responsivo:** Meu objetivo era que o design se adaptasse perfeitamente a qualquer tamanho de tela, seja desktop, tablet ou mobile.
-   **Estrutura de Seções:** Organizei o portfólio nas seguintes seções:
    -   **Hero Section:** Uma apresentação inicial impactante com meu título, subtítulo, objetivo profissional e links para minhas redes sociais.
    -   **Sobre Mim:** Detalhes pessoais, minha formação, idiomas que falo e experiências adicionais, tudo organizado em cards.
    -   **Tecnologias (Skills):** Um grid visual com as tecnologias que domino.
    -   **Projetos:** Uma galeria dos meus projetos com imagens, descrições, tecnologias usadas e funcionalidades.
    -   **Contato:** Minhas informações de contato e links para minhas redes sociais.

## 4. Minha Implementação do Conteúdo e Componentes

-   **Componente Principal (`App.vue`):** Centralizei a lógica e o layout geral do portfólio neste componente.
-   **Dados Dinâmicos:** Utilizei `ref` no Vue.js para gerenciar minhas informações pessoais e os dados dos projetos, o que facilita muito a atualização.
-   **Reutilização de Componentes:** Pensei em uma estrutura modular para que eu possa expandir o portfólio no futuro, adicionando novos componentes facilmente.

## 5. Minha Integração de Imagens e Ajustes

-   **Cópia de Assets:** Copiei minhas imagens de perfil e dos projetos para a pasta `src/assets` do novo projeto Vue.js.
-   **Ajuste do Efeito Glow:** Ajustei o efeito de brilho na minha foto de perfil para `opacity: 50%` e removi o `blur` para melhorar a visibilidade da foto, com base no meu próprio feedback.
-   **Links dos Projetos:** Incluí os links do GitHub para meus projetos Weather App (`https://github.com/dev-Gabe/WeatherApp`) e TechNews Portal (`https://github.com/dev-Gabe/TechNewsWebSite`), configurando-os para abrir em uma nova aba.

## 6. Meus Testes e Validação

-   **Testes Locais:** Executei o projeto localmente (`npm run dev`) para verificar a renderização, a responsividade e se todos os links e interações estavam funcionando corretamente.
-   **Correção de Erros:** Identifiquei e corrigi erros de compilação, especialmente aqueles relacionados ao TypeScript e à configuração do Tailwind CSS (tive que fazer a transição da v4 para v3 para garantir compatibilidade e estabilidade).
-   **Validação Visual:** Verifiquei se o design estava alinhado com o que eu planejei e com o requisito de ser "moderno".

## 7. Empacotamento e Entrega

-   **Geração de Build:** Criei a versão de produção do projeto (`npm run build`).
-   **Compactação:** Gerei um arquivo ZIP (`gabriel-portfolio-modern.zip`) contendo todo o código-fonte, mas excluindo `node_modules` e `.git` para que o pacote ficasse leve e pronto para uso.
-   **Documentação:** Incluí um `README.md` detalhado e a `LICENSE` (MIT) para facilitar a compreensão e o uso do projeto por quem for acessá-lo.

Este plano me ajudou a ter um desenvolvimento estruturado e iterativo, sempre focado na qualidade do design e em alcançar a minha satisfação com o resultado final.

