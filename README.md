# Portfólio — Lucas Dias Noronha

Portfólio profissional voltado à apresentação de projetos em **Análise de Dados, Ciência de Dados e Inteligência Artificial**.

O site reúne estudos de caso desenvolvidos com foco na investigação de problemas por meio de dados, contemplando etapas como preparação, análise exploratória, estatística, visualização e comunicação de resultados.

**Acesse o portfólio:**  
https://lucasdnoronha.github.io/portfolio/

---

## Sobre o portfólio

Este portfólio foi desenvolvido para documentar e apresentar projetos de dados de maneira estruturada, priorizando não apenas as tecnologias utilizadas, mas também o problema investigado, o processo analítico e os principais resultados obtidos.

A proposta é construir progressivamente uma coleção de estudos de caso que demonstre competências em:

- Python e pandas;
- SQL e PostgreSQL;
- Estatística;
- Análise Exploratória de Dados (EDA);
- Visualização de dados;
- Data Storytelling;
- Power BI;
- Excel;
- Git e GitHub.

---

## Projeto em destaque

### Panorama da População Indígena Brasileira — 2010–2022

Estudo baseado nos **Censos Demográficos de 2010 e 2022 do IBGE**, desenvolvido para investigar as transformações demográficas e espaciais da população indígena brasileira ao longo de doze anos.

O projeto envolve preparação e validação dos dados, análise exploratória, análise estatística, visualizações, investigação espacial e comunicação dos principais resultados.

Entre as tecnologias empregadas estão:

- Python;
- pandas;
- GeoPandas;
- Matplotlib;
- Plotly;
- Power BI;
- Streamlit.

O estudo de caso completo pode ser consultado diretamente no portfólio.

---

## Tecnologias do portfólio

O site foi construído com:

- **Astro** — framework utilizado para construção e geração estática do site;
- **HTML e CSS** — estrutura, responsividade e identidade visual;
- **JavaScript** — ecossistema e configuração do projeto;
- **Node.js e npm** — ambiente de execução e gerenciamento de dependências;
- **GitHub Actions** — automação do processo de build e publicação;
- **GitHub Pages** — hospedagem da versão pública.

A arquitetura foi deliberadamente mantida enxuta, sem a adoção de frameworks adicionais de interface, privilegiando desempenho, simplicidade e facilidade de manutenção.

---

## Estrutura do projeto

```text
portfolio/
├── .github/
│   └── workflows/
│       └── deploy.yml
│
├── public/
│   ├── images/
│   └── favicon.svg
│
├── src/
│   ├── components/
│   │   ├── Footer.astro
│   │   ├── Header.astro
│   │   └── ProjectCard.astro
│   │
│   ├── layouts/
│   │   └── BaseLayout.astro
│   │
│   ├── pages/
│   │   ├── index.astro
│   │   └── projetos/
│   │       └── panorama-populacao-indigena.astro
│   │
│   └── styles/
│       ├── global.css
│       └── tokens.css
│
├── astro.config.mjs
├── package.json
├── package-lock.json
└── README.md
```

### Organização

- `src/pages/` — páginas e rotas do site;
- `src/components/` — componentes reutilizáveis da interface;
- `src/layouts/` — estrutura compartilhada entre as páginas;
- `src/styles/` — estilos globais e tokens do design system;
- `public/` — imagens, favicon e demais arquivos estáticos;
- `.github/workflows/` — automação de build e deploy.

---

## Execução local

### Pré-requisitos

Para executar o projeto localmente, é necessário possuir:

- Node.js;
- npm.

### Instalação

Clone o repositório:

```bash
git clone git@github.com:LUCASDNORONHA/portfolio.git
```

Entre no diretório:

```bash
cd portfolio
```

Instale as dependências:

```bash
npm install
```

Inicie o ambiente de desenvolvimento:

```bash
npm run dev
```

O servidor de desenvolvimento do Astro será iniciado localmente.

---

## Comandos

| Comando | Descrição |
| --- | --- |
| `npm install` | Instala as dependências do projeto |
| `npm run dev` | Inicia o servidor local de desenvolvimento |
| `npm run build` | Gera a versão estática de produção |
| `npm run preview` | Executa localmente a versão gerada para produção |
| `npm run astro ...` | Executa comandos da CLI do Astro |

---

## Build

Para gerar a versão de produção:

```bash
npm run build
```

Os arquivos estáticos são gerados em:

```text
dist/
```

Antes de publicar alterações, a versão de produção pode ser validada localmente com:

```bash
npm run preview
```

---

## Deploy

O processo de publicação é automatizado por meio do **GitHub Actions**.

A cada `push` realizado na branch `main`, o workflow:

```text
.github/workflows/deploy.yml
```

executa o processo de build e publica a nova versão no **GitHub Pages**.

Fluxo simplificado:

```text
Alteração local
      ↓
Commit
      ↓
Push para main
      ↓
GitHub Actions
      ↓
Build do Astro
      ↓
GitHub Pages
      ↓
Portfólio atualizado
```

---

## Acessibilidade e qualidade

A implementação contempla recursos básicos de qualidade e acessibilidade, entre eles:

- HTML semântico;
- navegação por teclado;
- indicador visual de foco;
- link para salto direto ao conteúdo principal;
- suporte à preferência `prefers-reduced-motion`;
- navegação responsiva;
- textos alternativos em imagens;
- metadados para mecanismos de busca e compartilhamento;
- sitemap;
- layout responsivo.

---

## Desenvolvimento contínuo

O portfólio foi estruturado para evoluir juntamente com os projetos desenvolvidos.

Novos estudos de caso serão incorporados progressivamente, ampliando a demonstração prática de competências em análise de dados, bancos de dados, engenharia de dados, estatística, Business Intelligence e visualização.

---

## Autor

**Lucas Dias Noronha**

Estudante e profissional em formação nas áreas de Ciência de Dados, Análise de Dados e Inteligência Artificial.

- GitHub: https://github.com/LUCASDNORONHA
- Portfólio: https://lucasdnoronha.github.io/portfolio/