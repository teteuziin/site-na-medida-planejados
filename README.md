# Site — Na Medida Móveis Planejados e Granitos (nº9, FASE 2)

**⚠️ NÃO PUBLICAR sem aprovação do usuário.** Este pacote é a prévia para aprovação; a publicação no GitHub só acontece depois do "pode publicar".

Pacote: `index.html` + `media/` (7 vídeos, 7 pôsteres, 5 fotos, logo transparente) — 38 MB no total, maior arquivo 11,7 MB (< 25 MB).

---

## Declarações da skill Anti-Slop v2 (processo da Seção 13, na ordem)

1. **Design Read:** "Estou lendo isto como: a página oficial de uma marcenaria sob medida de Salvador para quem vai mobiliar a casa, com linguagem tátil de oficina — madeira, papel e régua — inclinando-se para tactile realism sobre uma grade de folha de projeto em CSS nativo."
2. **Dials:** DESIGN_VARIANCE **7** / MOTION_INTENSITY **5** / VISUAL_DENSITY **4** (landing de marketing local; motion contido porque a especificação do usuário fixa animações só scroll-driven e discretas).
3. **Direção estética positiva:** **Tactile realism** — porque a marca é física: madeira, pedra e uma régua no logotipo. A régua vira sistema estrutural (faixa de medição sob o header, ticks nas molduras de projeto e no formulário), o papel quente substitui o branco, e o grão sutil entra como textura de material, não como efeito.
4. **Tipografia:** display **Saira Condensed** 700/800 (letreiro de oficina, industrial, com peso real no topo) + corpo **Saira** 400/500/600/700 — mesma superfamília, contraste por largura. Tokens: h1 clamp(3.1rem, 7.4vw, 5.8rem)/1.02 · h2 clamp(2.3rem, 4.6vw, 3.6rem) · lead 1.1875rem/1.55 · corpo 1rem/1.62 · caption .8125rem. Tracking −0.02em só nos títulos grandes; balance só neles; numerais tabulares nos dados.
5. **Cor:** âncora **vermelho-régua #A40405** (mediana amostrada dos pixels vermelhos da logo oficial) — papel de ação (botões, números, foco) e destaque. Neutros quentes: `--papel #F6F1E7`, `--papel-2 #EEE4D0`, `--superficie #FFFDF7`, `--tinta #221A14`, `--tinta-2 #4C4136`, `--madeira #8A5A2B` (só gráfico), `--linha #D9CDB2`. Sem #000/#fff puros, sem gradiente de cor (os únicos repeating-linear-gradient são os ticks duros da régua — padrão de medição, justificado no gate).
6. **Quebra de layout:** hero 50/50 com a foto emoldurada como "folha de projeto"; seções numeradas 01–05 na grade de 12 colunas especificada pelo usuário; depoimentos como única faixa escura; orçamento em 5/7 (texto/formulário). Nada de cards de features: ambientes e passos são listas pautadas.

## Especificações do usuário (18/11/2026) — conferência

- Container 1400px, padding 1rem/2rem ✔ · Hero 50/50 desktop, empilhado no mobile com texto acima e foto object-cover (4/5) ✔ · Seções numeradas: grid 12 colunas (1–4 número+título, 5–7 texto, 8–12 mídia); mobile empilha número→título→texto→mídia (ordem do DOM) ✔ · Separação só por espaçamento vertical (`--sec` 6rem/4rem), nenhuma linha solta como divisor de seção ✔ · Vídeos verticais em wrapper 9/16 max-w 350px (os dois do atendimento são 4/5 na origem e usam wrapper 4/5 com o mesmo teto) ✔ · Animações SÓ scroll-driven: CSS `animation-timeline: view()` com `@supports` (sem suporte, tudo visível — fallback digno); via única, sem biblioteca ✔ · Sem fade-in-up genérico, sem bounce, sem transition-all (grep: 0) ✔ · Títulos grandes com reveal por linha (line mask, spans autorais, sem `<br>`) ✔ · Números com scale 0.9→1 + opacidade ease-out na entrada ✔ · Hover de vídeo scale 1.02 (só pointer fino) e botão de play centralizado (76px, vermelho) ✔ · Hover de botão = cor + translateY(−2px), transições com propriedades nomeadas ✔ · Tracking −0.02em e balance nos títulos grandes ✔ · Corpo max-w 65ch ✔ · Reduced-motion: animações e transições desligadas ✔.

## Conteúdo — decisões cumpridas (do dossiê)

- **Sem endereço de rua e sem horários** (duas fichas no Google, uma fechada). Localização no site: Salvador/BA; Sussuarana só como local do projeto Vivver Ulisses (vem dos posts).
- **Telefone (71) 99126-3593 (ficha do Google) NÃO entra** — divergente. Único canal: WhatsApp público dela **(71) 98120-1033** → wa.me/5571981201033 (13 dígitos, conferido no HTML).
- **Nenhum preço** (grep "R$": 0), nenhum prazo/garantia inventados. O site vende o orçamento.
- Nome no site: **João Paulo** (como ele se apresenta). Processo dela: Projeto 3D → Orçamento → Produção → Instalação. Slogans dela no hero ("Seu sonho, nosso compromisso") e no rodapé ("Compromisso, atenção e responsabilidade fazem parte de cada projeto").
- Prova legendada pelo que cada vídeo mostra: f5 = apartamento completo no Vivver; f6 = 11ª entrega *ganhando forma* (não "entregue").
- Depoimentos reais do destaque Feedbacks, como texto, **sem nomes inventados**; pontuação levemente normalizada em dois deles (o "Comcerteza" de um print virou só a frase do elogio) — registrado aqui por transparência.
- Interatividade útil: **montador de orçamento** (ambiente obrigatório com estado de erro acessível, medidas, nome, desejo) que abre o wa.me dela com a mensagem montada.

## Gate mecânico de slop (Seção 11) — manual

**Gate manual: 24/24 aprovados.** Fontes banidas 0 (Saira/Saira Condensed) · gradiente em texto 0 · gradiente roxo/rosa 0 · 3 cards idênticos 0 (listas pautadas e galeria assimétrica) · #000/#fff puros 0 (grep) · transition-all 0 (grep) · animação em layout 0 (só transform/opacity) · APCA corpo ≥ 75 (corpo 15.2:1 ≈ Lc 95+; pior par de texto 8.8:1 ≈ Lc 80+) · scroll horizontal 320–768: 0 por construção (grids colapsam, overflow-x hidden, palavras longas medidas) · balance só nos títulos grandes · `<br>` em headline 0 · peso máximo 800 real · marquees/hijacking 0 · imagem duplicada 0 (f18 excluída por ser outro ângulo do mesmo ambiente de f16) · scroll cue 0 · hero-fit-the-fold 0 (hero tem a altura do conteúdo) · nav/footer fora do template padrão (header com régua da marca; footer em 3 colunas de conteúdo real) · side-stripe 0 · card-in-card 0 · emoji de UI 0 · SVG de ícone desenhado à mão 0 (play é glifo CSS de mídia; grão é textura) · estados de interação completos (hover/focus/active em botões, links, players) · estados de input (focus, erro com aria-invalid + role=alert) · prefers-reduced-motion coberto · disciplina de tokens (cores, respiro e raio em variáveis).

**Tell Score estimado: 13/100** (alvo < 20). Resíduos honestos: o motivo da régua se repete em 3 pontos (header, moldura do hero, formulário) — é o sistema da marca, não decoração solta; e a faixa escura de depoimentos é a inversão única de ritmo.

## Pre-flight (Seção 12)

- Contraste WCAG (calculado): corpo 15.22:1 · secundário 8.81:1 · botão 7.95:1 · destaque 7.18:1 · erro 9.46:1 · depoimentos 15.22:1 e 9.43:1 — todos ≥ 4.5:1.
- Foco visível (outline 3px vermelho), teclado operável (players e formulário nativos), HTML semântico com landmarks e aria-labels, alt text descritivo em todas as imagens.
- Responsivo: auditoria estática regra a regra (390/768/1440) + auditoria do artefato hospedado. Sem navegador headless nesta VM — a conferência visual final é do usuário, como nas nº2–nº7.

## Verificações de mídia

- **ffprobe no pacote final: 7/7 vídeos com áudio AAC** (MD5 idênticos aos arquivos brutos conferidos: vivver-tour e lar-franciscano; os demais são cópias diretas).
- Áudio na origem (midias-brutas): **10/10 vídeos com AAC** — nenhum reel falado mudo; nenhum re-download necessário.
- Exclusões justificadas: f1 e f4 (artes com texto embutido — o conteúdo virou texto do site), f10 (renders/stock de terceiros + texto), f11 (meme político na abertura + overlay de texto permanente em todo o restante), f12 usada só no recorte limpo acima do painel de texto da arte, f13 (só referência de marca), f18 (ângulo duplicado do ambiente de f16).
- Logo sem fundo gerada de f14 por remoção do fundo claro com rampa suave de borda, recortada na marca; conferida sobre o papel do site.
