# Documentação do site

**Projeto:** site institucional de Carlos A. A. Oliveira – Advogados
**Endereço:** https://oliveiracarlos.adv.br
**Versão:** 2.0 (novembro de 2026)
**Autor:** Carlos Alexandre Albuquerque Oliveira (OAB/PA 33.996)

---

## 1. Visão geral

O site é estático: os arquivos HTML são servidos diretamente pelo GitHub Pages, sem banco de dados, sem servidor e sem etapa de compilação. Para mudar qualquer coisa, basta editar o arquivo e enviar ao repositório.

## 2. Estrutura do repositório

```
/
├── index.html            Página principal (todo o conteúdo e o CSS ficam aqui)
├── CNAME                 Domínio próprio: oliveiracarlos.adv.br
├── site.webmanifest      Nome e ícones para "Adicionar à tela inicial"
├── sitemap.xml           Mapa do site para o Google
├── robots.txt            Instruções para buscadores
├── README.md             Apresentação do projeto
├── docs/
│   └── DOCUMENTACAO.md   Este documento
└── Visual/
    ├── Favicon/          Ícones da aba do navegador e do celular
    ├── Fotografias Advogado/
    │   ├── retrato-meio-corpo.jpeg       Foto da abertura
    │   ├── retrato-fundo-cinza.jpeg      Foto da seção "Sobre"
    │   ├── tribuna.jpeg                  Galeria: contencioso
    │   ├── escritorio-trabalhando.jpeg   Galeria: consultivo
    │   └── biblioteca.jpeg               Galeria: estudo
    └── Logo/
        ├── logo-branco.png               Logo do escritório (fundos escuros)
        ├── logo-verde.png                Logo do escritório (fundos claros e Google)
        ├── ramodeoliveiraCLARO.png       Marca-d'água da abertura
        ├── lex-tecnologias.png           Logo da Lex (fundo claro)
        └── lex-tecnologias-branco.png    Logo da Lex (modo escuro)
```

## 3. Seções da página principal

| Ordem | Seção | Âncora | Conteúdo |
|---|---|---|---|
| 1 | Cabeçalho | — | Logo, menu e botão "Agendar consulta". Fica translúcido ao rolar e vira menu lateral em telas de até 1100 px. |
| 2 | Abertura | `#inicio` | Frase de posicionamento, selo "Advocacia artesanal", retrato e botões de contato |
| 3 | Números | — | Início na advocacia, especializações, áreas e atendimento |
| 4 | Sobre | `#sobre` | Apresentação e os pilares Clareza, Honestidade e Utilidade |
| 5 | Galeria | — | Três fotos de atuação |
| 6 | Áreas de atuação | `#areas` | Cinco cartões com "Saiba mais" expansível e um cartão de contato |
| 7 | Como funciona | `#consulta` | As quatro etapas da consulta |
| 8 | Formação | `#formacao` | Linha do tempo e experiências complementares |
| 9 | Artigos | `#artigos` | Cartão que leva ao perfil no Medium (https://medium.com/@oliveiracarlosadv). Os textos não ficam hospedados neste site. |
| 10 | Lex Tecnologias | `#lex` | Iniciativa de tecnologia, sete produtos e link para o portal |
| 11 | Contato | `#contato` | WhatsApp, telefone, e-mail, canal, redes e avaliação no Google |
| 12 | Rodapé | — | Navegação, contato e aviso ético |

O botão flutuante do WhatsApp aparece em todas as telas. No celular, fica só o ícone.

## 4. Identidade visual

### Cores (definidas no início do `<style>`, em `:root`)

| Variável | Cor | Uso |
|---|---|---|
| `--verde-escuro` | `#043B1F` | Fundo da abertura, cabeçalho, botões |
| `--verde-medio` | `#2A6B49` | Destaques, ícones |
| `--verde-cinza` | `#4A6659` | Textos secundários |
| `--dourado` | `#B8966A` | Detalhes, linhas, foco do teclado |
| `--whats` | `#25D366` | Botões do WhatsApp |

A seção da Lex Tecnologias usa a paleta própria da Lex (`#374D29`, `#457029`, `#556B2F`), para deixar claro que é uma iniciativa separada.

### Modo escuro
As cores de fundo, texto e borda são redefinidas automaticamente em `@media (prefers-color-scheme: dark)`, conforme a preferência do aparelho do visitante.

### Fontes (Google Fonts)
- **Playfair Display:** títulos
- **Inter:** textos

## 5. Como fazer alterações comuns

### Trocar uma foto
Substitua o arquivo em `Visual/Fotografias Advogado/` **mantendo o mesmo nome**. Prefira fotos com pelo menos 800 px de largura.

### Mudar o texto de uma área de atuação
Em `index.html`, procure o `<h3>` com o nome da área. O resumo fica no `<p>` logo abaixo, as etiquetas ficam no `<ul>` e o texto completo fica dentro de `<details>`.

### Mudar telefone, e-mail ou redes sociais
Use "Localizar e substituir" no editor:
- telefone: `5591986061300` (links) e `(91) 98606-1300` (texto)
- redes e Medium: `oliveiracarlosadv`

### Atualizar os produtos da Lex Tecnologias
Na seção `id="lex"`, cada produto é um bloco `<div class="produto">`. A etiqueta de situação usa `class="status"` (verde) ou `class="status dev"` (dourado, para produtos em desenvolvimento).

### Adicionar uma nova página
1. Duplique um HTML existente e troque o conteúdo.
2. Inclua o endereço no `sitemap.xml` e atualize a data em `<lastmod>`.

## 6. Publicação

1. Edite os arquivos.
2. Envie ao repositório (`main`):
   ```bash
   git add -A
   git commit -m "Descrição da mudança"
   git push
   ```
3. O GitHub Pages publica sozinho em 1 a 2 minutos. Acompanhe em **Settings → Pages** ou na aba **Actions**.
4. Se o navegador mostrar a versão antiga, recarregue com `Cmd + Shift + R`.

**Domínio:** o arquivo `CNAME` contém `oliveiracarlos.adv.br`. Não apague esse arquivo, ou o domínio próprio deixa de funcionar.

## 7. SEO e compartilhamento

- **`<title>` e `<meta name="description">`:** o que aparece no Google.
- **Open Graph (`og:`):** a prévia com foto ao colar o link no WhatsApp, LinkedIn e Instagram. A imagem é `Visual/Fotografias Advogado/retrato-meio-corpo.jpeg`.
- **JSON-LD (`LegalService`):** dados estruturados com nome, telefone, áreas e redes.
- **`canonical`:** indica o endereço oficial (`https://oliveiracarlos.adv.br/`).
- **`sitemap.xml` e `robots.txt`:** ajudam o Google a encontrar todas as páginas.

- **Metatags de busca:** `keywords` (termos como "advogado em Belém", "advogado trabalhista Belém"), `author`, `robots`/`googlebot` (indexação liberada, com prévia grande de imagem), idioma `pt-BR` e `hreflang`.
- **Busca local:** `geo.region` (BR-PA), `geo.placename` e coordenadas de Belém. O JSON-LD informa as cidades atendidas (Belém, Ananindeua, Marituba, Pará e Brasil).
- **JSON-LD em grafo:** `WebSite`, `WebPage`, `LegalService`/`LocalBusiness` (com catálogo das 5 áreas, contato e redes) e `Person` (OAB/PA 33.996, formação e perfis).
- **Twitter/X:** título, descrição e imagem próprios.
- **Google Search Console:** há um comentário no `<head>` indicando onde colar a tag `google-site-verification`, caso a propriedade seja confirmada por metatag.

Depois de mudanças grandes, envie o sitemap de novo no Google Search Console.

> **Importante:** metatags ajudam o Google a entender o site, mas não garantem posição. O que mais pesa na busca local é o **Perfil da Empresa no Google** (nome, categoria "Advogado", fotos, avaliações), links de outros sites e conteúdo novo com frequência.

## 8. Acessibilidade

- Todas as imagens têm texto alternativo (`alt`).
- O menu funciona pelo teclado. A tecla `Esc` fecha o menu do celular.
- O contorno dourado indica o foco ao navegar com `Tab`.
- As animações são desativadas para quem configurou "reduzir movimento" no sistema.

## 9. Ética profissional (OAB)

O conteúdo segue o Código de Ética e Disciplina da OAB e o Provimento nº 205/2021:
- não há promessa de resultado, preço nem comparação com outros profissionais;
- o aviso ético fica no rodapé;
- a Lex Tecnologias é apresentada como iniciativa de tecnologia, separada da prestação de serviços advocatícios (art. 40, IV, do CED).

Ao acrescentar conteúdo, mantenha esses cuidados.

## 10. Histórico de versões

| Versão | Data | Mudanças |
|---|---|---|
| 1.x | 2025 – jun. 2026 | Primeira landing page |
| 2.1 | 25/11/2026 | Metatags de busca, busca local, Twitter/X e JSON-LD ampliado |
| 2.0 | nov. 2026 | Novo visual (modo escuro, animações, menu lateral), fotos e logos novos, nome "Carlos A. A. Oliveira – Advogados", seções "Como funciona", formação em linha do tempo, artigos via Medium e Lex Tecnologias, imagens hospedadas no próprio repositório, manifesto, sitemap e robots atualizados |
