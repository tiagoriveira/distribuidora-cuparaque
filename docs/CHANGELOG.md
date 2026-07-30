# CHANGELOG — Conveniência com Delivery (Cuparaque/MG)

> **O que é este arquivo:** histórico cronológico — o que mudou, quando, por quem e **por quê**.
> Separado do `BACKLOG.md` de propósito: lá é "o que falta", aqui é "o que já foi".
>
> **Raramente precisa ser relido por inteiro** — use Grep pra achar a sessão/tema específico.
>
> Ordem: **mais recente primeiro**. Append-only: não reescreva a história. Se uma auditoria
> posterior descobrir que algo estava errado, anote como `[CORREÇÃO dd/mm]` em vez de editar o
> passado.
>
> ⚠️ As 2 entradas mais recentes deste arquivo são injetadas automaticamente no início de cada
> sessão (hook global) — então escreva cada entrada pensando em quem vai lê-la sem nenhum outro
> contexto.

---

## [30/07/2026] — Repositório criado + 6 cursos novos + 3 achados que mudam o modelo (Claude)

**Contexto:** o projeto vinha de uma sessão anterior que produziu a planilha e um curso de gestão
financeira, mas vivia solto — planilha num container efêmero, cursos no Notion, nada versionado.
O founder pediu para criar este repositório seguindo o padrão de orquestração de contexto dele
(`global-repo-orquestra-o-tiago-julho2026`), para que cada sessão de IA chegue com contexto.

**O que mudou:**

- **Repositório criado** com a estrutura do padrão: `CLAUDE.md` + `docs/` (index, BACKLOG,
  CHANGELOG, ROADMAP, em-aberto) + `docs/modelo/` (premissas, formulas, resultados).
  - `docs/modelo/` é **adição ao template padrão**, aprovada pelo founder: as premissas são o
    coração deste projeto e precisavam de lugar estável que não fosse lei, histórico nem pendência.
  - Seções de software do template (Arquitetura, Contratos de API, Modelo de dados, Comandos)
    foram **substituídas** por Modelo financeiro, Status dos dados e Artefatos — este projeto não
    tem código.
- **Planilha versionada** em `modelo/plano_conveniencia_cuparaque.xlsx` (7 abas, 159 fórmulas).
- **6 cursos novos** escritos no Notion, completando a série de 7: Fluxo de Caixa, Valuation,
  Precificação Psicológica, Gestão de Estoque, Análise de Concorrência e DRE.

**Três achados que o modelo original não mostrava** (aritmética conferida; detalhe em
`docs/modelo/resultados.md` §4):

1. **A rampagem exige ~R$ 32.500 de capital** além do investimento inicial, se os sócios retirarem
   desde o mês 1. Com retirada escalonada, o caixa nunca fica negativo — diferença de ~R$ 63 mil
   na necessidade de capital, mesma loja, mesmas vendas.
2. **Em DRE, o mês maduro dá prejuízo de R$ 659.** O EBITDA é R$ 8 por construção (o planejamento
   reverso acerta a meta com precisão de oito reais) e a depreciação o derruba. Tradução: o modelo
   não paga a reposição do equipamento.
3. **O teste de mercado assumia 100% de participação sem declarar.** Com um concorrente dividindo
   o mercado, a exigência por domicílio dobra (1,32 → 2,64 compras/mês, R$ 72 → R$ 145).

**Decisões tomadas:**

- **A retirada é R$ 3.500 POR SÓCIO** (R$ 10.500 total). Resolve a ambiguidade que estava aberta
  desde 29/07. Registrada como **parâmetro ajustável**, não valor travado — decisão explícita do
  founder de que nada é número estático.
- **O negócio é conveniência, NÃO distribuidora**, apesar do nome do repositório. Registrado em
  destaque no `CLAUDE.md` §1 para nenhuma sessão futura raciocinar em termos de B2B.
- **R7 criada:** nenhum número chumbado; toda premissa é input recalculável. Decisão do founder
  ("não são números estáticos, não números hipotéticos"). Consequência direta: as tabelas dos
  cursos no Notion, calculadas à mão, precisam virar abas vivas da planilha — está no BACKLOG.
- **R4 criada:** todo teste de mercado declara a participação assumida. É a única restrição que não
  veio do briefing original — nasceu do achado 3.
- **Planilha fica em Excel**, sem página web espelho. O `.xlsx` é o artefato do modelo.
- **Cursos ficam no Notion**, não são duplicados neste repositório — evita duas fontes divergindo.

**Validação:** planilha auditada lendo o XML do .xlsx diretamente (sem instalar dependências):
159 fórmulas confirmadas, encadeadas a partir da aba `Premissas`. Toda a aritmética dos achados
foi conferida linha a linha; a decomposição do mix fecha exatamente em `1 − 67,35%`, e a cascata
da DRE por pedido fecha em R$ 10,096, idêntica ao R$ 10,09 do modelo original.

⚠️ **Nenhuma pesquisa externa foi feita, em nenhum momento deste projeto.** Nenhuma cotação real
existe. Ver `CLAUDE.md` §5.

**Ficou pendente ao encerrar a sessão:**

- **Página web no Lovable** — pedida pelo founder, **não criada**. O conector MCP do Lovable
  esteve ativo (os workspaces chegaram a ser listados) e caiu antes de qualquer criação. O escopo
  da página **não foi confirmado** pelo founder. Detalhes operacionais em `docs/BACKLOG.md`; a
  decisão em aberto em `docs/em-aberto.md`.
- **As 6 abas novas da planilha** (FluxoCaixa, DRE, Valuation, Precificacao, Estoque,
  Concorrencia) foram planejadas e aprovadas em escopo, mas **não implementadas** — a sessão
  encerrou antes. Enquanto elas não existirem, as análises de 30/07 vivem só como texto no Notion
  e **não recalculam** (viola R7 na prática). É o maior débito técnico aberto.
- **`openpyxl` não foi instalado** — necessário para editar o .xlsx. Requer autorização explícita
  do founder (regra 9 do padrão global).

**Para quem pegar a próxima sessão:** leia `CLAUDE.md`, depois `docs/index.md`, e vá para
`docs/BACKLOG.md`. O gargalo real do projeto **não é código nem planilha** — são as 7 cotações de
campo que só o founder pode levantar. Sem elas, todo refinamento do modelo é refinar ficção (R2).

---

## [29/07/2026] — Origem: modelo financeiro por precificação reversa (Claude, sessão anterior)

**Contexto:** o founder queria avaliar a viabilidade de abrir uma conveniência com delivery em
Cuparaque/MG. Optou-se por **precificação reversa** — partir da meta de retirada dos sócios e
voltar até o volume de vendas necessário — em vez de criar produtos e ver quanto sobra.

**O que mudou:**

- **Planilha `plano_conveniencia_cuparaque.xlsx`** criada: 7 abas (Leia-me, Premissas, Mix,
  Cascata, Demanda, Cenarios, Ofertas), 159 fórmulas, recalculada sem erros.
- **Curso "Gestão Financeira na Prática"** publicado no Notion: 12 módulos + glossário, cobrindo
  margem de contribuição, CMV, markup vs. margem, ponto de equilíbrio, mix, alíquota efetiva,
  teto de mercado e como usar IA sem ser enganado por ela.

**Decisões tomadas:**

- **Margem de contribuição explícita** como núcleo do modelo. Motivo: o founder trouxe um exemplo
  (pizzaria) em que R$ 30k de fixo + R$ 20k de lucro dava R$ 100k de faturamento — conta que só
  fecha com 50% de margem implícita, que não estava declarada. O modelo torna a margem explícita e
  a deriva do mix real.
- **Todos os custos, CMV e percentuais operacionais foram INVENTADOS**, com autorização explícita
  do founder ("invente um plausível"), porque os dados não existiam. **Zero cotação real.**
- **Restrição técnica registrada:** o recálculo é LibreOffice. Não usar `XLOOKUP`, `FILTER`,
  `SORT`, `UNIQUE`, `SEQUENCE` — usar `INDEX`/`MATCH`.

**Resultado:** margem de R$ 10,09/pedido (18,4%) · 1.347 pedidos/mês · R$ 74.058 de faturamento
necessário · ~45 pedidos/dia · equilíbrio em ~302 pedidos/mês.

**Validação:** planilha recalculada, zero erros. Aritmética interna consistente.

⚠️ **Ficou em aberto:** ambiguidade da retirada (por sócio ou total — resolvida em 30/07),
conflito populacional (3.958 × "8 mil"), concorrência não mapeada, ST não implementada.
