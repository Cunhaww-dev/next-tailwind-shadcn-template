# 🚀 Next.js 15 Boilerplate
Um template inicial robusto para projetos Next.js, pré-configurado com Next.js 15, Tailwind CSS e a biblioteca de componentes shadcn/ui.

Este projeto serve como uma base sólida e escalável para iniciar novos aplicativos web, já incluindo uma estrutura de pastas organizada e configurações essenciais.


# 💻 Tech Stack
- Framework: Next.js 15 (com App Router)
- Estilização: Tailwind CSS
- Componentes UI: shadcn/ui
- Gerenciamento de Tema: next-themes
- Linguagem: TypeScript


# ✨ Features
- ✅ Stack Moderna: Pronto para usar os recursos mais recentes do React (React 19) e Next.js 15.
- ✅ UI Pronta: shadcn/ui instalado e configurado, com o components.json na raiz e os componentes base na pasta src/components/ui.
- ✅ Dark Mode: O ThemeProvider (do next-themes) já está configurado em src/components/providers, pronto para uso.
- ✅ Estrutura Organizada: Uma arquitetura de pastas pensada para escalabilidade (veja detalhes abaixo).
- ✅ Utils Otimizadas: Inclui a função utilitária cn do shadcn para mesclagem de classes do Tailwind.


# 🚀 Como Começar
Para usar este boilerplate, você pode clonar o repositório ou, idealmente, clicar em "Use this template" no GitHub para criar um novo repositório a partir dele.

**Clone o repositório (ou use o template):**
````
git clone [URL_DO_SEU_REPOSITÓRIO] nome-do-novo-projeto
cd nome-do-novo-projeto
````
**Instale as dependências:**
Recomenda-se usar pnpm, mas npm também funciona.

````
pnpm install
# ou
yarn install
# ou
npm install
````

**Rode o servidor de desenvolvimento:**

````
npm dev
````

Abra http://localhost:3000 no seu navegador para ver o projeto em execução.


# 📂 Estrutura de Pastas
A arquitetura do projeto está centralizada na pasta src/ para facilitar a organização.
````
├── public/               # Arquivos estáticos (imagens, fontes, etc.)
├── src/
│   ├── 📁app/            # Rotas (App Router), layouts e páginas
│   │   ├── 📁(dashboard) # Exemplo de rota (layout e páginas)
│   │   ├── globals.css   # Estilos globais do Tailwind
│   │   ├── layout.tsx    # Layout raiz da aplicação
│   │   └── page.tsx      # Página inicial (Home)
│   │
│   ├── 📁components/     # Componentes React
│   │   ├── 📁layout/     # Componentes de layout (Header, Sidebar, Nav, etc.)
│   │   ├── 📁providers/  # Provedores de contexto (Ex: ThemeProvider)
│   │   ├── 📁shared/     # Componentes genéricos reutilizáveis (Ex: ModeToggle)
│   │   └── 📁ui/         # Componentes "primitivos" do shadcn/ui (gerados)
│   │
│   ├── 📁hooks/          # Hooks customizados (Ex: use-mobile)
│   └── 📁lib/            # Funções utilitárias (Ex: utils.ts para cn())
│
├── .gitignore
├── components.json       # Configuração do shadcn/ui
├── next.config.ts        # Configuração do Next.js
├── package.json
├── tailwind.config.js    # Configuração do Tailwind CSS
└── tsconfig.json         # Configuração do TypeScript
````

**Filosofia dos Componentes**
- **src/components/ui:** Contém os componentes base gerados pelo shadcn/ui (Button, Input, Card, etc.). Evite editar esses arquivos diretamente.

- **src/components/shared:** Use esta pasta para criar seus próprios componentes reutilizáveis usando os componentes da pasta ui. Por exemplo, um UserAvatar que usa o Avatar do shadcn.

- **src/components/layout:** Componentes maiores que definem a estrutura da aplicação, como AppHeader ou AppSidebar.

# 🛠️ Adicionando novos componentes shadcn/ui
Para adicionar novos componentes do shadcn/ui ao projeto, utilize o CLI oficial:

````
pnpm dlx shadcn-ui@latest add [nome-do-componente]
````

Exemplo:

````
pnpm dlx shadcn-ui@latest add card dialog alert
````
Os componentes serão adicionados automaticamente à pasta src/components/ui.


# 🧱 Arquitetura de Componentes (Escalabilidade)

Para gerenciar o crescimento da aplicação, recomendamos a organização por **Recurso (Feature-Based)**, que é a base da nossa arquitetura Híbrida.

Você pode criar novas pastas dentro de `src/components/` para agrupar o conteúdo por funcionalidade:

* **Organização Híbrida (Recomendada):** Agrupa componentes por **propósito e rota**. É mais fácil de escalar e manter.
    * **Exemplos:**
        * `src/components/forms/`: Para formulários complexos usados em várias telas.
        * `src/components/dashboard/`: Componentes específicos usados apenas nas rotas do Dashboard (`/dashboard/*`).
        * `src/components/upload/`: Componentes específicos da tela de Upload.

* **Organização por Atomic Design (Alternativa):** Se você preferir seguir estritamente o Atomic Design, pode criar pastas como `src/components/atoms`, `src/components/molecules` e `src/components/organisms`. No entanto, a organização Híbrida (que já usa `/ui` como **Átomos**) geralmente oferece melhor clareza para projetos grandes.

**A regra é:** Se o componente é exclusivo de uma rota ou feature, agrupe-o em uma pasta com o nome dessa feature.

---
[Link para visualizar o Boilerplate](next-tailwind-shadcn-template.vercel.app)
---

[Doc Shadcn](https://ui.shadcn.com/docs/components)
<br>
[Doc Next](https://nextjs.org/docs/app/getting-started/installation)
<br>
[Doc Tailwind](https://tailwindcss.com/docs/installation/tailwind-cli)
