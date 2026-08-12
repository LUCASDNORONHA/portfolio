# AGENTS.md

## Finalidade

Este arquivo define as instruções gerais para agentes de IA que trabalhem neste repositório.

Antes de modificar código, conteúdo, arquitetura ou configuração, o agente deve compreender a estrutura existente e preservar as decisões já consolidadas no projeto.

Quando existir uma especificação normativa em `docs/especificacoes.md`, ela deve ser consultada antes de decisões de produto, escopo ou arquitetura.

---

## Visão geral do projeto

Este repositório contém o portfólio profissional de **Lucas Dias Noronha**, destinado à apresentação de projetos em:

- Análise de Dados;
- Ciência de Dados;
- Inteligência Artificial;
- Estatística;
- Business Intelligence;
- bancos de dados;
- engenharia e preparação de dados.

O portfólio é um site estático desenvolvido em **Astro**, publicado no **GitHub Pages** e implantado automaticamente por meio do **GitHub Actions**.

URL pública:

```text
https://lucasdnoronha.github.io/portfolio/
```

Repositório:

```text
LUCASDNORONHA/portfolio
```

---

## Objetivo do portfólio

O portfólio deve apresentar projetos de maneira profissional, orientada principalmente a:

- recrutadores;
- gestores;
- profissionais da área de Dados;
- avaliadores técnicos.

O objetivo não é simplesmente exibir tecnologias utilizadas.

Cada estudo de caso deve procurar demonstrar:

1. qual problema foi investigado;
2. quais dados foram utilizados;
3. como os dados foram preparados;
4. quais métodos foram empregados;
5. quais resultados foram encontrados;
6. como os resultados foram interpretados;
7. quais limitações existem;
8. onde o código e os produtos relacionados podem ser examinados.

Prioridade editorial:

```text
Problema
↓
Dados
↓
Método
↓
Evidência
↓
Interpretação
↓
Conclusão
```

Evitar páginas que funcionem apenas como listas de tecnologias ou reproduções do README dos projetos originais.

---

## Stack tecnológica

O portfólio utiliza:

- Astro;
- TypeScript em configuração estrita;
- HTML semântico;
- CSS próprio;
- Node.js;
- npm;
- Git;
- GitHub;
- GitHub Actions;
- GitHub Pages.

Integração atualmente utilizada:

- `@astrojs/sitemap`.

Não adicionar frameworks ou bibliotecas de interface sem necessidade explícita.

Evitar introduzir automaticamente:

- React;
- Vue;
- Svelte;
- Tailwind CSS;
- Bootstrap;
- bibliotecas completas de componentes.

A arquitetura deve permanecer enxuta enquanto Astro, HTML e CSS forem suficientes.

---

## Estrutura principal

```text
portfolio/
├── .github/
│   └── workflows/
│       └── deploy.yml
├── public/
│   ├── images/
│   │   └── projects/
│   └── favicon.svg
├── src/
│   ├── components/
│   │   ├── Footer.astro
│   │   ├── Header.astro
│   │   └── ProjectCard.astro
│   ├── layouts/
│   │   └── BaseLayout.astro
│   ├── pages/
│   │   ├── index.astro
│   │   └── projetos/
│   │       └── panorama-populacao-indigena.astro
│   └── styles/
│       ├── global.css
│       └── tokens.css
├── astro.config.mjs
├── package.json
├── package-lock.json
├── README.md
└── AGENTS.md
```

Se `docs/especificacoes.md` existir, ele integra a documentação normativa do projeto.

---

## Responsabilidade dos principais arquivos

### `src/layouts/BaseLayout.astro`

Responsável por:

- estrutura HTML principal;
- metadados;
- SEO;
- Open Graph;
- Twitter Cards;
- favicon;
- canonical URL;
- link de acessibilidade para salto ao conteúdo.

Novas páginas devem reutilizar este layout sempre que possível.

### `src/components/Header.astro`

Contém:

- marca `LDN`;
- navegação desktop;
- navegação móvel;
- links internos da Home.

Os links internos devem respeitar:

```astro
const base = import.meta.env.BASE_URL;
```

Nunca presumir que o site está hospedado na raiz do domínio.

### `src/components/ProjectCard.astro`

Componente reutilizável para apresentação de projetos na Home.

Recebe:

```text
title
description
image
imageAlt
technologies
href
status
```

O componente não deve montar URLs internamente. O arquivo que o utiliza é responsável por fornecer caminhos corretos.

### `src/components/Footer.astro`

Rodapé global do portfólio.

Manter simples e discreto.

### `src/styles/tokens.css`

Concentra os design tokens globais:

- cores;
- tipografia;
- espaçamentos;
- larguras;
- raios;
- tempos de transição.

Antes de criar um valor CSS recorrente, verificar se ele deve ser transformado em token.

### `src/styles/global.css`

Responsável por estilos globais, incluindo:

- box sizing;
- corpo da página;
- tipografia;
- imagens;
- links;
- foco;
- acessibilidade;
- containers;
- seções;
- preferência por redução de movimento.

Evitar estilos específicos de uma única página neste arquivo.

### `src/pages/index.astro`

A Home segue atualmente:

```text
Header
↓
Hero
↓
Projetos
↓
Sobre
↓
Competências
↓
Formação
↓
Contato
↓
Footer
```

A Home deve permanecer objetiva.

Não adicionar blocos sem justificativa clara para recrutamento ou apresentação profissional.

---

## Identidade visual

O portfólio utiliza exclusivamente tema escuro.

Direção visual:

- tecnológica;
- discreta;
- profissional;
- limpa;
- editorial;
- sem estética excessivamente futurista.

Evitar:

- gradientes neon excessivos;
- brilho artificial;
- efeitos holográficos;
- animações meramente decorativas;
- fundos visualmente carregados;
- aparência genérica de produto de IA;
- excesso de cards.

A paleta principal está definida em `tokens.css`.

Valores centrais atuais:

```text
#0B0D10
#12161B
#181E25
#27313B
#F3F6F8
#9EABB7
#4D9FFF
```

O azul deve funcionar como destaque, não como cor dominante.

---

## Tipografia

Utilizar a pilha tipográfica definida nos tokens.

A hierarquia deve favorecer:

- títulos grandes e objetivos;
- parágrafos legíveis;
- textos auxiliares discretos;
- uso moderado de fonte monoespaçada para labels e metadados.

Evitar excesso de texto em caixa alta.

Labels como `PROJETOS`, `SOBRE`, `COMPETÊNCIAS`, `RESULTADOS` e `TECNOLOGIAS` podem utilizar caixa alta e fonte monoespaçada.

---

## Responsividade

Toda implementação nova deve funcionar adequadamente em:

- desktop;
- tablet;
- smartphone.

Evitar larguras fixas que prejudiquem telas menores.

Utilizar preferencialmente:

```css
clamp()
minmax()
grid
flex
```

e preservar os breakpoints e padrões responsivos existentes sempre que forem adequados.

---

## Acessibilidade

Preservar obrigatoriamente:

- HTML semântico;
- navegação por teclado;
- `:focus-visible`;
- textos alternativos em imagens;
- `aria-label` quando necessário;
- link `Ir para o conteúdo principal`;
- suporte a `prefers-reduced-motion`.

Cada página principal deve possuir:

```astro
<main id="conteudo-principal">
```

Não remover essa convenção sem justificativa técnica.

---

## GitHub Pages e caminhos

O site está publicado no subdiretório:

```text
/portfolio/
```

A configuração está em `astro.config.mjs`:

```js
site: "https://lucasdnoronha.github.io",
base: "/portfolio/",
```

Por isso, caminhos internos não devem presumir `/` como raiz do site.

Utilizar:

```astro
const base = import.meta.env.BASE_URL;
```

Exemplos corretos:

```astro
<a href={base}>Início</a>
```

```astro
<a href={`${base}#projetos`}>Projetos</a>
```

```astro
<img
  src={`${base}images/projects/exemplo.png`}
  alt="..."
/>
```

```astro
href={`${base}projetos/nome-do-projeto`}
```

Evitar:

```astro
href="/projetos/..."
```

ou:

```astro
src="/images/..."
```

quando o recurso pertence ao próprio portfólio.

---

## Projetos e estudos de caso

Cada projeto relevante deve possuir página própria em:

```text
src/pages/projetos/
```

Formato recomendado:

```text
nome-do-projeto.astro
```

Estrutura editorial preferencial:

```text
Hero
↓
Contexto
↓
Problema / perguntas analíticas
↓
Dados e preparação
↓
Metodologia
↓
Resultados
↓
Visualizações
↓
Interpretação
↓
Produtos interativos
↓
Tecnologias
↓
Limitações
↓
Próximos passos
```

Não é obrigatório utilizar todas as seções quando não forem pertinentes.

---

## Regra para resultados

Um resultado importante deve preferencialmente seguir:

```text
Descoberta
↓
métrica ou evidência
↓
visualização
↓
interpretação
```

Evitar afirmações sem evidência quantitativa quando o projeto possui dados suficientes para sustentá-las.

Não inventar métricas, resultados, conclusões ou evidências para completar páginas do portfólio.

---

## Visualizações

As visualizações utilizadas no portfólio devem, preferencialmente, vir diretamente dos projetos originais.

Armazenar cópias destinadas ao site em:

```text
public/images/projects/<slug-do-projeto>/
```

Não modificar ou inventar resultados apenas para tornar o portfólio visualmente mais atraente.

Toda visualização deve apoiar uma conclusão ou dimensão analítica pertinente.

---

## Projeto atualmente publicado

### Panorama da População Indígena Brasileira — 2010–2022

Página:

```text
src/pages/projetos/panorama-populacao-indigena.astro
```

Repositório original:

```text
https://github.com/LUCASDNORONHA/exploracao-dados-indigenas-2010-2022
```

Produtos e dimensões relacionados incluem:

- análise em Python;
- análise geoespacial;
- Streamlit;
- Power BI;
- evolução demográfica;
- urbano × rural;
- regiões;
- estados;
- Terras Indígenas;
- distribuição espacial.

Não apresentar partes futuras ou ainda não concluídas como finalizadas.

---

## Competências prioritárias

O portfólio procura demonstrar principalmente:

- Python;
- pandas;
- SQL;
- PostgreSQL;
- Estatística;
- Análise Exploratória de Dados;
- Power BI;
- Excel;
- Visualização de Dados;
- Data Storytelling;
- Git;
- GitHub.

Ao adicionar novos projetos, distribuir competências de maneira complementar.

Evitar tentar demonstrar todas as tecnologias em todos os projetos.

---

## Inclusão de novos projetos

Ao adicionar um projeto:

1. avaliar se possui maturidade suficiente;
2. consultar as especificações pertinentes;
3. selecionar resultados verificáveis;
4. criar ou copiar imagens apropriadas quando necessário;
5. criar a página em `src/pages/projetos/`;
6. adicionar um `ProjectCard` na Home;
7. verificar responsividade;
8. verificar caminhos utilizando `BASE_URL`;
9. executar o build;
10. revisar conteúdo e links;
11. somente então considerar a implementação concluída.

Não adicionar cartões vazios como:

```text
Em breve
Projeto futuro
Coming soon
```

Projetos devem aparecer quando possuírem conteúdo suficiente para serem examinados.

---

## Regras de conteúdo

O texto deve ser escrito em português formal, claro e profissional.

Priorizar:

- precisão;
- concisão;
- evidências;
- legibilidade.

Evitar:

- hipérboles;
- autopromoção excessiva;
- frases genéricas;
- afirmações não demonstradas;
- jargão corporativo vazio.

Preferir formulações como:

```text
"Analisei..."
"Os dados indicam..."
"O resultado mostra..."
"A comparação revelou..."
```

em vez de:

```text
"Projeto incrível..."
"Insights poderosos..."
"Transformação revolucionária..."
```

---

## Formação

A Home apresenta apenas formações relacionadas diretamente a Dados e Inteligência Artificial.

Não adicionar automaticamente outras formações sem revisar previamente sua pertinência para o posicionamento profissional do portfólio.

---

## Experiência profissional

A experiência em logística pode aparecer como diferencial profissional, especialmente quando relacionada a:

- processos;
- indicadores;
- produtividade;
- gargalos;
- SLA;
- eficiência operacional;
- análise de operações.

O portfólio não deve ser apresentado como exclusivamente logístico.

A experiência logística deve funcionar como contexto aplicado à capacidade analítica.

---

## Dependências

Utilizar npm como gerenciador de pacotes.

Versionar obrigatoriamente:

```text
package.json
package-lock.json
```

Não versionar:

```text
node_modules/
dist/
.astro/
.env
.env.production
```

Consultar `.gitignore`.

Antes de instalar uma nova dependência, verificar se a funcionalidade pode ser implementada adequadamente com Astro, HTML ou CSS nativos.

---

## Comandos principais

Instalar dependências:

```bash
npm install
```

Ambiente de desenvolvimento:

```bash
npm run dev
```

Build de produção:

```bash
npm run build
```

Preview:

```bash
npm run preview
```

---

## Validação obrigatória

Antes de considerar qualquer incremento concluído:

```bash
npm run build
```

O build deve finalizar sem erros.

Quando mudanças visuais forem relevantes, executar também:

```bash
npm run preview
```

Verificar, quando aplicável:

- Home;
- páginas de projetos;
- imagens;
- links;
- versão mobile;
- navegação por teclado;
- caminhos do GitHub Pages.

---

## Deploy

O deploy é automatizado por:

```text
.github/workflows/deploy.yml
```

Branch de produção:

```text
main
```

Fluxo:

```text
alteração
↓
commit
↓
push
↓
GitHub Actions
↓
build
↓
GitHub Pages
```

Não editar diretamente arquivos dentro de:

```text
dist/
```

A pasta é gerada automaticamente.

---

## Convenção de commits

Utilizar mensagens compatíveis com Conventional Commits quando possível.

Exemplos:

```text
feat: adiciona estudo de caso de frotas
fix: corrige navegação em dispositivos móveis
docs: atualiza documentação do portfólio
style: ajusta espaçamento da seção de projetos
refactor: reorganiza componentes da página inicial
ci: atualiza workflow do GitHub Pages
chore: atualiza dependências do projeto
```

---

## Princípios de manutenção

Ao modificar o projeto:

1. compreender primeiro a estrutura existente;
2. consultar as especificações quando a alteração afetar produto, escopo ou arquitetura;
3. reutilizar componentes antes de criar duplicações;
4. preservar a identidade visual;
5. evitar dependências desnecessárias;
6. preservar acessibilidade;
7. preservar compatibilidade com GitHub Pages;
8. não remover conteúdo existente sem justificativa;
9. manter o build funcional;
10. realizar alterações incrementais;
11. favorecer legibilidade e manutenção futura.

---

## Hierarquia documental

Quando os arquivos existirem, considerar as seguintes responsabilidades:

```text
docs/especificacoes.md
→ define o produto, o escopo, os requisitos e as decisões normativas

AGENTS.md
→ define como agentes devem trabalhar no repositório

README.md
→ apresenta e documenta publicamente o projeto
```

Não duplicar desnecessariamente o conteúdo das especificações dentro deste arquivo.

Se houver conflito entre uma regra operacional deste arquivo e uma decisão normativa mais recente e explícita das especificações, interromper a alteração e reconciliar os documentos antes de prosseguir.

---

## Regra central

Sempre priorizar:

```text
clareza
+
evidência
+
consistência
+
manutenibilidade
```

em detrimento de:

```text
complexidade
+
efeitos decorativos
+
quantidade de tecnologias
```

O portfólio deve demonstrar maturidade analítica e técnica, não apenas capacidade de produzir uma interface visualmente elaborada.
