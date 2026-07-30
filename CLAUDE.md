# CLAUDE.md — Conveniência com Delivery (Cuparaque/MG)

> **O que é este arquivo:** a **lei vigente** deste projeto — o que é o negócio, restrições,
> modelo financeiro, status dos dados, convenções. Curto de propósito: **não** carrega histórico
> (isso é `docs/CHANGELOG.md`) nem futuro (isso é `docs/ROADMAP.md`).
>
> Regras de **comportamento** do agente (não inventar, pedir autorização antes de escrever,
> red-team antes de elogio) vivem em `~/.claude/CLAUDE.md` e valem em todo projeto — não repita aqui.
>
> 🗺️ Depois deste arquivo, leia **`docs/index.md`** — ele diz qual doc adicional abrir para cada
> tipo de tarefa, em vez de reler tudo sempre.

---

## 1. O que é este projeto

> ⚠️ **O repositório se chama `distribuidora-cuparaque`, mas o negócio NÃO é uma distribuidora.**
> É uma **conveniência com delivery e retirada**, vendendo ao **consumidor final**. Distribuidora
> seria B2B (venda a revendedores), com margem, ticket e volume completamente diferentes — e
> **nada** deste modelo se aplicaria a ela. O nome do repo é histórico. Confirmado pelo founder em
> 30/07/2026. Se alguma sessão futura começar a raciocinar em termos de B2B, está errada.

**O que é:** avaliação de viabilidade para abrir um serviço de **conveniência com delivery e
retirada** em **Cuparaque/MG** — bebidas, snacks, gelo, carvão e mercearia emergencial, com
pedidos por WhatsApp.

**Estado atual:** é um **estudo de viabilidade**, não uma operação. Nada foi comprado, alugado ou
contratado. Nenhuma cotação real foi levantada.

**Quem:** 3 sócios, que operam o negócio eles mesmos (sem funcionário na premissa atual).

**O método — precificação reversa:** parte da meta de retirada dos sócios e volta até o volume de
vendas necessário, em vez de criar produtos e ver quanto sobra. A pergunta não é *"quanto sobra?"*,
é *"quanto preciso vender para que sobre o que eu quero?"*.

---

## 2. Restrições vinculantes (não negociáveis)

> Aquilo que **nunca** pode ser violado, com o **motivo** ao lado. Sem o motivo, uma sessão futura
> acha que a regra é arbitrária e a contorna.

| # | Restrição | Motivo | Origem |
|---|---|---|---|
| **R1** | **Todo número carrega status explícito: `COTADO` / `DERIVADO` / `INVENTADO`.** Número sem status não entra em doc nem em planilha | Hoje **quase tudo** é INVENTADO. Perder essa marcação transforma ficção em base de decisão de investimento | Briefing de origem, 29/07/2026 |
| **R2** | **Nenhuma decisão de investimento antes das 4 cotações de campo** (§ `docs/BACKLOG.md`) | O modelo inteiro repousa em premissas fictícias. Decidir sobre elas é decidir no escuro com aparência de planilha | Briefing de origem, 29/07/2026 |
| **R3** | **PIB per capita NUNCA é usado como renda familiar disponível** sem a ressalva de que 40,7% do PIB local é administração pública | PIB per capita não é renda no bolso. Usar como proxy **superestima muito** a capacidade de gasto e produz veredito falsamente otimista | Briefing §6 + curso de Concorrência |
| **R4** | **Todo teste de mercado declara a participação de mercado assumida.** Dividir a demanda por toda a população é assumir monopólio | O teste de realidade original fazia isso **sem declarar**. Com 50% de participação a exigência por domicílio dobra | Descoberto em 30/07/2026 — curso de Concorrência, Módulo 5 |
| **R5** | **Proibido "estudos mostram" / "pesquisas indicam" sem autor, ano e título** | Dado sem fonte é invenção com roupa de autoridade | Briefing de origem, 29/07/2026 |
| **R6** | **Quando não houver base: escrever "não sei com segurança" e parar.** Não preencher lacuna com estimativa plausível | Plausível tem exatamente a mesma aparência de verdadeiro, e é indistinguível para quem lê depois | Briefing de origem, 29/07/2026 |
| **R7** | **Nenhum número chumbado.** Toda premissa é célula/parâmetro editável; mexer nela recalcula a cascata inteira | Decisão do founder, 30/07/2026: *"não são números estáticos, não números hipotéticos"*. Número fixo num texto vira mentira silenciosa quando a premissa muda | Founder, 30/07/2026 |

---

## 3. O modelo financeiro vigente

**Método:** precificação reversa (meta → volume necessário), com **margem de contribuição
explícita** — que é justamente o que falta na conta ingênua "R$ 30 mil de fixo + R$ 20 mil de
lucro = R$ 50 mil de faturamento".

**A cascata, em ordem:**

1. Quanto os sócios querem tirar? *(meta)*
2. Quanto a operação custa sem vender nada? *(custo fixo)*
3. Quanto sobra de cada venda depois dos custos daquela venda? *(margem de contribuição)*
4. Quantas vendas cobrem 1 + 2? *(volume necessário)*
5. O mercado comporta esse volume? *(teste de realidade)*

Se o passo 5 der não, **volta-se aos passos 1 a 4. Não se muda a realidade.**

As fórmulas exatas estão em **`docs/modelo/formulas.md`**. Não as duplique aqui.

**Restrição técnica da planilha:** o recálculo é feito por **LibreOffice**. Não usar `XLOOKUP`,
`FILTER`, `SORT`, `UNIQUE`, `SEQUENCE`. Usar `INDEX`/`MATCH`.

---

## 4. Estrutura de arquivos

```
CLAUDE.md                  # este arquivo — a lei vigente
docs/
  index.md                 # índice de navegação: "tarefa X → leia Y"
  BACKLOG.md               # SÓ pendência ativa
  CHANGELOG.md             # histórico cronológico, append-only
  ROADMAP.md               # futuro não-bloqueante, com o motivo de esperar
  em-aberto.md             # inbox de decisões não tomadas — NUNCA fonte de verdade
  modelo/
    premissas.md           # TODA premissa, com status R1 (cotado/derivado/inventado)
    formulas.md            # as fórmulas do modelo, derivadas e conferidas
    resultados.md          # os números que saem delas
modelo/
  plano_conveniencia_cuparaque.xlsx   # o artefato vivo do modelo (7 abas, 159 fórmulas)
```

---

## 5. Status dos dados — a seção mais importante deste repositório

> **Leia isto antes de usar qualquer número deste projeto em qualquer decisão.**

| Status | O que significa | Quanto do modelo está aqui |
|---|---|---|
| `COTADO` | Preço/valor real, levantado com fornecedor, contrato ou fonte oficial | **Zero. Nenhum.** |
| `INFORMADO` | Fornecido pelo founder, não verificado de forma independente | Dados de Cuparaque (população, PIB, composição) |
| `DERIVADO` | Consequência aritmética de outros números, com a conta conferida | Todos os resultados (margem, pedidos, faturamento) |
| `INVENTADO` | Escolhido por uma IA a pedido explícito, **sem nenhuma cotação** | **Todos os custos, CMV, ticket e percentuais operacionais** |

**A consequência prática, dita sem rodeio:** a **estrutura lógica** do modelo é contabilidade
gerencial padrão e é confiável. A **aritmética** foi conferida. **Os números de entrada são
ficção autorizada.** O modelo serve hoje para responder *"que perguntas eu preciso fazer?"*, não
*"devo abrir o negócio?"*.

O detalhamento item a item está em **`docs/modelo/premissas.md`**.

---

## 6. Premissas e resultados vigentes (resumo)

> Resumo para orientação rápida. **Valores vigentes e completos:** `docs/modelo/premissas.md` e
> `docs/modelo/resultados.md`. A fonte executável é a planilha.

**Parâmetros principais** (todos ajustáveis — R7):

| Parâmetro | Valor atual | Status |
|---|---|---|
| Retirada por sócio | R$ 3.500/mês | INFORMADO — confirmado pelo founder em 30/07/2026 |
| Nº de sócios | 3 | INFORMADO |
| Ticket médio planejado | R$ 55 | INVENTADO — é a **alavanca principal** do modelo |
| CMV ponderado | 67,35% | INVENTADO (derivado do mix, também inventado) |
| Custo fixo total | R$ 3.091/mês | INVENTADO |
| Alíquota efetiva (Simples) | 8,13% | A CONFERIR — provavelmente **superestimada** (ver §7 ST) |

**Resultados que saem daí:**

| Indicador | Valor | Leitura |
|---|---|---|
| Margem de contribuição | R$ 10,09/pedido (18,4%) | Margem baixa — restringe desconto e posicionamento por preço |
| Pedidos necessários | 1.347/mês (~45/dia) | |
| Faturamento necessário | R$ 74.058/mês | |
| Ponto de equilíbrio | ~302 pedidos/mês (~10/dia) | ⚠️ Recálculo de 30/07 dá **~306** — ver `docs/BACKLOG.md`. Folga de segurança grande de qualquer forma |
| **Capital da rampagem** | **~R$ 32.500** | ⚠️ **Divergência aberta:** a curva como documentada em `premissas.md` §7 dá **R$ 44.850**. Ver `docs/BACKLOG.md` |
| **Resultado em DRE** | **−R$ 659/mês** | Prejuízo, pela depreciação não coberta |

⚠️ **Três achados de 30/07/2026 que o modelo original não mostrava** — detalhe em
`docs/modelo/resultados.md`:

1. A rampagem exige ~R$ 32,5 mil de capital **além** do investimento inicial, se os sócios
   retirarem desde o mês 1. Com retirada escalonada, o caixa nunca fica negativo.
2. Em DRE, com depreciação, o mês maduro dá **prejuízo** — o modelo não paga a reposição do
   equipamento.
3. O teste de mercado assume **100% de participação** sem declarar (→ R4).

---

## 7. Artefatos e fontes externas

| Artefato | Onde | Papel |
|---|---|---|
| **Planilha do modelo** | `modelo/plano_conveniencia_cuparaque.xlsx` | **Fonte executável.** 7 abas, 159 fórmulas encadeadas a partir de `Premissas` |
| **Dashboard editável** | Lovable, projeto `3e66cd92-bafc-489e-b9b4-d8a193d56977` ("Cuparaque Conecta") | Espelho **interativo** do modelo — 7 abas, nada chumbado, recalcula tudo dos inputs. **Não é fonte de verdade:** se divergir da planilha, a planilha manda |
| **7 cursos de gestão financeira** | [Notion](https://app.notion.com/p/3aca16ed6e5f815e9c87fa7ae4592859) | Material didático: margem, fluxo de caixa, valuation, precificação, estoque, concorrência, DRE |
| **Briefing de handoff** | Processado para `docs/CHANGELOG.md` e `docs/em-aberto.md` | Origem do projeto (29/07/2026) |

**Abas da planilha:** `Leia-me` · `Premissas` (todos os inputs) · `Mix` (CMV ponderado) ·
`Cascata` (o cálculo reverso) · `Demanda` (teste de realidade) · `Cenarios` (sensibilidade) ·
`Ofertas` (combos).

⚠️ **Substituição Tributária não implementada.** Bebidas e cigarros são tipicamente ICMS-ST; o
varejista pode segregar essa receita e reduzir a alíquota efetiva. O modelo **não** faz isso, então
o imposto está provavelmente superestimado. **Pergunta obrigatória para contador, não para IA.**

⚠️ **Divergência conhecida entre Notion e planilha:** os cursos trazem tabelas com números
calculados à mão em 30/07/2026 (rampagem, DRE, VPL, curva de desconto, ABC, participação de
mercado). **Esses números não recalculam.** Se uma premissa mudar na planilha, os cursos ficam
desatualizados. Migrar essas análises para abas vivas é item do `docs/BACKLOG.md`.

---

## 8. Convenções

- **Todo número vem com status** (R1). Em tabela, coluna de status; em texto, marcação explícita.
- **Dinheiro em reais com centavos** quando o valor unitário importa (margem por pedido, preço);
  arredondado para o real quando é agregado mensal.
- **Nunca alterar um número da planilha sem registrar** de onde veio o novo valor. Substituir um
  `INVENTADO` por um `COTADO` é a mudança mais valiosa que este projeto pode receber — e precisa
  aparecer no `docs/CHANGELOG.md`.
- **Toda análise nova nasce na planilha, não em texto** (R7). Texto explica; planilha calcula.
- **Ao citar um resultado, cite a premissa que mais o move.** "R$ 74 mil/mês" sozinho engana;
  "R$ 74 mil/mês, com ticket de R$ 55 e CMV de 67,35%, ambos inventados" informa.
- **Linguagem:** português, tom direto. Sem "estudos mostram" (R5). Sem preencher lacuna (R6).
