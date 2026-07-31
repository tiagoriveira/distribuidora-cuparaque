# Em Aberto — Conveniência com Delivery (Cuparaque/MG)

> **O que é este arquivo:** o "segundo cérebro" — inbox de decisões ainda **não tomadas**,
> perguntas sem resposta e capturas brutas de conversa pra processar depois.
>
> ⚠️ **NUNCA é fonte de verdade.** Nada aqui é regra. Um item só vira regra quando é **processado
> e movido** pro doc certo (`CLAUDE.md`, `BACKLOG.md`, `ROADMAP.md`). Enquanto estiver aqui, é
> matéria-prima — um agente que tratar isto como decisão está errado.
>
> Ordem: mais recente primeiro.

---

## [31/07/2026] — ~~Arquitetura do "segundo cérebro"~~ → DECIDIDO, movido

**Decidido em 31/07/2026: o segundo cérebro é este repositório, aberto como vault do Obsidian.**
Sem base de conhecimento paralela. A descrição vigente está no `CLAUDE.md` §4 e §7; a pasta de
memória operacional é `docs/operacao/`. Histórico e critério da escolha no `docs/CHANGELOG.md`.

**O que sobrou em aberto desta discussão — a segunda planilha:** a proposta de separar
**"VISÃO"** (a planilha atual, o modelo projetado) de uma **"Gestão Mensal de Caixa"** (o realizado
mês a mês, comparado contra a meta da `Cascata`).

⚠️ **A decisão do Obsidian não resolve esta:** `docs/operacao/` é markdown — serve para registrar,
não para calcular. Fechamento de mês com comparação contra meta quer planilha.

**A favor:** é o *feedback loop* que valida ou derruba as premissas inventadas.
**Contra:** seria uma terceira fonte de números (planilha do modelo + dashboard Lovable + esta).

⚠️ **Mas o "contra" é mais fraco do que parece:** ela guarda o **realizado**, não o **planejado**.
Não é cópia do modelo, é o contraponto dele — não há o que divergir, porque não calculam a mesma
coisa.

**Status:** em aberto — e **não é urgente**: não há mês para fechar enquanto não houver operação.
Reabrir quando a Fase 1 do MVP começar.

---

## [31/07/2026] — Qual o caminho para o MVP?

**Pergunta/tensão em aberto:** o founder perguntou qual caminho de MVP seria recomendado. Uma
sessão de 31/07 propôs quatro fases; **nada foi decidido**.

**A proposta na mesa:**
- **Fase 0 — validar sem estoque:** pré-venda por WhatsApp/grupo local por 2–3 semanas, sem loja,
  testando 1–2 combos. Objetivo: ver se a recompra por domicílio é real.
- **Fase 1 — operação enxuta:** freezer doméstico + garagem, 15–20 SKUs, priorizando as
  categorias de maior margem (gelo/carvão/descartáveis, snacks). Sem alugar ponto.
- **Fase 2 — mirar o equilíbrio, não a meta plena:** o primeiro marco é **~10,2 pedidos/dia**
  (`Cascata!B29`), não os ~44,9 da meta de retirada. Capex só depois de sustentar isso 1–2 meses.
- **Fase 3 — formalização:** CNPJ, alvará de bebida e Simples quando o volume justificar.

**O que sustenta essa direção:** a aba `Ofertas` da planilha já registra que *"operar sem ponto
próprio no início é a economia mais óbvia a testar"* — a Fase 1 é a execução disso. E a Fase 0
ataca diretamente a premissa mais frágil do modelo (frequência de recompra), com custo quase zero.

⚠️ **O que essa proposta NÃO resolve, e precisa ser dito:** ela **não substitui as 7 cotações de
campo** (`BACKLOG.md`). Rodar Fase 0 e Fase 1 sem saber o CMV real do distribuidor é operar sem
saber se cada venda dá lucro. A Fase 0 valida **demanda**; ela não valida **margem**.

⚠️ **Tensão com a R2:** a Fase 1 já envolve comprar estoque e um freezer — é decisão de
investimento, ainda que pequena. Formalmente a R2 a bloqueia. Vale o founder decidir se a R2 se
aplica ao MVP enxuto ou só ao investimento cheio; hoje o texto da R2 não distingue.

**Status:** em aberto — proposta de uma sessão de IA, não decisão do founder.

---

## [31/07/2026] — O distrito de Aldeia entra no raio de entrega?

**Pergunta/tensão em aberto:** `premissas.md` §2 registra que a população de Cuparaque se concentra
"no núcleo urbano **e no distrito de Aldeia**". A premissa de **80% dos domicílios no raio de
entrega** não diz se Aldeia está dentro ou fora.

**Por que importa:** muda direto a base de `Demanda!C10` (domicílios endereçáveis), que é o
denominador do teste de realidade inteiro. **Decisão de custo baixo e impacto alto** — é só definir
o raio, mas move o veredito de plausibilidade.

**Relação com outro item aberto:** pode ser a explicação do conflito populacional (3.958 × "~8
mil") logo abaixo — se o founder pensava na região atendida e não no município. **Vale responder
as duas juntas.**

**Status:** em aberto — pergunta simples para o founder.

---

## [30/07/2026] — Isto é um emprego ou um investimento?

**Pergunta/tensão em aberto:** o modelo, como está desenhado, aloca **todo** o resultado como
pró-labore. Sobra R$ 8 de EBITDA no mês maduro, e a depreciação leva a DRE para −R$ 659. Pelo
critério de valuation, o VPL é negativo em qualquer taxa de desconto.

Isso não significa que o negócio seja ruim. Significa que **ele não é um investimento — é a compra
de três empregos de R$ 3.500/mês, financiada pelos próprios empregados.**

**O que já se sabe:**
- R$ 3.500 ÷ 270h mensais ≈ **R$ 13/hora** por sócio (9h/dia × 30 dias, sem revezamento).
- Se os sócios se revezarem, a carga individual cai e a conta por hora melhora — **mas aí
  provavelmente entra custo de pessoal**, que hoje é zero na premissa. Não modelado.
- Não existe linha de lucro-alvo sobre o capital investido. Adicioná-la aumenta o faturamento
  necessário, que já está na borda do que a cidade comporta.

**Opções na mesa:**
- **Aceitar como emprego** — decisão perfeitamente válida, se R$ 3.500 for um bom salário para o
  esforço e para a alternativa de cada sócio. Prós: modelo fecha como está. Contras: o capital
  investido não tem retorno; payback matematicamente infinito.
- **Adicionar lucro-alvo e ver se fecha** — prós: responde a pergunta certa. Contras: é provável
  que **não feche**, e descobrir isso pode matar o projeto. (Descobrir agora é mais barato que
  descobrir depois de investir.)
- **Reduzir a retirada e criar espaço** — prós: já era a alavanca mais barata no fluxo de caixa.
  Contras: R$ 13/h vira menos ainda.

**Status:** em aberto — decisão do dono. **Não decidir isso por conta própria em sessão nenhuma.**

---

## [30/07/2026] — A divergência entre o Notion e a planilha

**Pergunta/tensão em aberto:** os 7 cursos no Notion contêm tabelas calculadas à mão (rampagem,
DRE, VPL, curva de desconto, ABC por margem, cenários de participação). **Esses números não
recalculam.** Se uma premissa mudar na planilha, os cursos passam a mentir.

**O que já se sabe:**
- A R7 ("nenhum número chumbado") foi criada justamente por isso.
- A solução acordada é migrar as análises para abas vivas da planilha e deixar os cursos apontando
  para ela — está no `BACKLOG.md`.
- **O que não está decidido:** se os cursos mantêm os números como ilustração didática (marcados
  como snapshot) ou se passam a citar só a fórmula, sem número nenhum.

**Opções na mesa:**
- **Manter com marca de snapshot** — prós: o curso continua legível e didático sozinho. Contras:
  número visível desatualizado ainda engana quem lê rápido.
- **Remover os números, deixar só as fórmulas** — prós: impossível divergir. Contras: curso fica
  abstrato; a força do material está justamente em ver o R$ 32.500 aparecer.

**Status:** em aberto. Inclinação: marca de snapshot, por causa do valor didático — mas é decisão
do dono.

---

## [29/07/2026] — Conflito populacional: 3.958 ou "8 mil"?

**Pergunta/tensão em aberto:** o founder mencionou um "bairro de ~8 mil habitantes" antes de
enviar os dados de Cuparaque, que indicam **3.958 habitantes** (projeção 2026). O modelo usa 3.958.

**O que já se sabe:**
- Com 3.958 hab. e 3,1 moradores/domicílio, dão ~1.021 domicílios endereçáveis (80% no raio).
- **Se o mercado real for 8 mil**, os domicílios dobram e toda a exigência por domicílio cai pela
  metade — o que mudaria o veredito de plausibilidade de forma relevante, inclusive nos cenários
  de participação de mercado.
- A diferença pode ser: cidade × distrito, município × região atendida, ou dado desatualizado.

**Opções na mesa:**
- Confirmar que o alvo é o município de Cuparaque (3.958).
- Confirmar que o alvo inclui localidades vizinhas, e então **recalcular o mercado endereçável**.

**Status:** em aberto — **pergunta simples, impacto grande.** Vale resolver antes de qualquer
refinamento do teste de demanda.

---

## [29/07/2026] — Substituição Tributária: quanto de imposto é excesso?

**Pergunta/tensão em aberto:** bebidas e cigarros são tipicamente ICMS-ST. O varejista pode
segregar essa receita e não pagar ICMS de novo dentro do Simples. **O modelo não faz isso**, então
a alíquota efetiva de 8,13% está provavelmente superestimada.

**O que já se sabe:**
- A loja é majoritariamente bebida (cerveja 40% + refri 15% + destilados 10% = 65% do mix), então
  o efeito pode ser relevante.
- Se a alíquota cair, a margem sobe e a DRE pode inverter de sinal — o prejuízo de R$ 659/mês é
  pequeno o suficiente para ser revertido por isso.
- **A regra existe; a aplicação ao caso específico e os percentuais, não sei.**

**Status:** em aberto — **pergunta obrigatória para contador, não para IA.** Está no `BACKLOG.md`
como item manual 4.
