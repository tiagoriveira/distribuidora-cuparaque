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

## [30/07/2026] — Página web no Lovable: página de quê?

**Pergunta/tensão em aberto:** o founder pediu **duas vezes** "criar uma página web no Lovable",
sem especificar o conteúdo, e não respondeu quando as opções foram apresentadas. A ambiguidade é
real porque **minutos antes ele havia decidido "só Excel, sem página web"** para o modelo
financeiro — então a página provavelmente é outra coisa, mas não se sabe qual.

**O que já se sabe:**
- Workspace definido: `yWut1L8QhIAJ9fMG61Ae` (onde ele é proprietário).
- O conector do Lovable caiu antes de qualquer coisa ser criada. **Nada foi feito lá.**

**Opções na mesa:**
- **Vitrine / cardápio da conveniência** — produtos, combos, horário, área de entrega, botão que
  abre o WhatsApp com o pedido. Prós: **é a única das quatro que gera receita**, e não depende de
  nenhuma cotação para começar a valer. Contras: é ferramenta de venda de um negócio que ainda não
  existe.
- **Painel de leitura do estudo** *(escolha provisória)* — números, os três achados, o que falta
  cotar. Prós: serve para alinhar os outros dois sócios; sem risco de divergir do Excel. Contras:
  não produz nada além de comunicação.
- **Dashboard editável do modelo financeiro** — prós: o modelo fica acessível no celular.
  Contras: **contraria a decisão de 30/07** ("planilha fica no Excel") e cria segunda fonte que
  pode divergir — exatamente o que R7 existe para evitar.
- **Painel operacional** (pedidos, estoque, ruptura) — já está no `ROADMAP.md`, esperando a loja
  existir.

**Status:** em aberto — **perguntar antes de criar.** A escolha provisória foi o painel de leitura,
mas ela não foi confirmada pelo founder.

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
