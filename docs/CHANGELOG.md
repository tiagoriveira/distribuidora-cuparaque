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

## [31/07/2026] — As duas divergências resolvidas + contexto de uma sessão do Claude no Excel (Claude)

**Contexto:** o founder colou a transcrição de uma sessão paralela — **Claude rodando dentro do
Excel**, com acesso direto ao `.xlsx` e **sem acesso a este repositório** (o conector de GitHub não
estava disponível lá). Essa sessão respondeu sobre orçamento inicial, MVP e arquitetura de "segundo
cérebro". Esta entrada processa aquele material para os docs certos.

⚠️ **Ressalva importante sobre a procedência:** aquela sessão **não operava sob as restrições
R1–R7** — ela não conseguiu ler o `CLAUDE.md`. As recomendações dela são úteis, mas não nasceram
sob as regras deste projeto e foram filtradas por elas aqui.

### As duas divergências abertas em 30/07 estão RESOLVIDAS

**1. Capital da rampagem: R$ 32.500 está certo. Meu R$ 44.850 estava errado.** `[CORREÇÃO 31/07]`
da entrada abaixo. A tabela em `resultados.md` §4.1 publica quatro pontos da curva original
(40% no mês 1, 60% no 3, 85% no 6, 97% no 10) — e a curva **é côncava, não linear**. Os
percentuais **40/50/60/70/80/85** reproduzem **exatamente** os três saldos acumulados publicados
(−8.145, −20.349, −29.124). Nenhuma outra interpolação testada fecha nos três pontos.
**O erro era a descrição em prosa** da `premissas.md` §7 — *"40% no mês 1 → 100% no mês 11"* lê-se
como reta (+6 pontos/mês), e tomá-la ao pé da letra é o que produziu R$ 44.850. Corrigido: a curva
agora é **tabela mês a mês** (`premissas.md` §7.1), não prosa. Os meses 7–9 e 11 continuam
desconhecidos e estão marcados como tal (R6).

**2. Ponto de equilíbrio: ~306, não ~302.** Confirmado por via independente: a célula
`Cascata!B29` da própria planilha traz **10,2 pedidos/dia** → 306/mês. O "~302" estava replicado em
`CLAUDE.md` §6, `resultados.md` §1 e no CHANGELOG de 29/07. Corrigido nos dois primeiros; o de
29/07 fica como está (append-only).

**A lição das duas:** ambas vieram de **número descrito em prosa em vez de tabelado**. É a mesma
falha que a R7 ataca, num lugar onde ninguém tinha olhado — a *documentação* da premissa, não a
planilha.

### O que a sessão do Excel apurou sobre a planilha

- **Não existe nenhuma seção de investimento inicial na planilha.** Não há como responder "qual o
  orçamento mínimo para começar?" — confirmado lendo o arquivo. Vira item de BACKLOG.
- **Mapa de células levantado** e registrado em `resultados.md` §1.1 (`Premissas!C22`,
  `Cascata!B22`, `Cascata!B29`, `Mix!A6:B13`, `Demanda!C10`, `Ofertas!A6:A11`, `Leia-me!A28`,
  `Leia-me!A40`). Evita reabrir o `.xlsx` só para localizar um número.
- **Confirmado que o aviso de "não verificado" já existe** na aba `Leia-me`, e que os combos da aba
  `Ofertas` carregam a mesma ressalva.
- ⚠️ **A planilha NÃO foi modificada.** Aquela sessão tentou criar as abas `Roteiro MVP` e
  `Investimento Inicial` e falhou — a conexão com o add-in do Excel caiu. Nada entrou.

### Uma recomendação daquela sessão foi rejeitada

**"Reservar 3 a 6 meses de custo fixo como colchão de caixa" (R$ 9,3 mil–R$ 18,5 mil).** Não é para
usar, por dois motivos, agora registrados em `resultados.md` §5: (a) é regra de bolso sem fonte
(R5); (b) **ignora o termo dominante** — o buraco da rampagem não é o custo fixo de R$ 3.091, é a
retirada de R$ 10.500/mês, 3,4× maior. Por isso o número real é R$ 32.500. A regra subestima o
colchão em 2–3× e erra **para o lado que quebra a empresa**.

### Decisão do founder registrada

**A pasta de gestão operacional é no Notion:**
["Conveniência Cuparaque"](https://app.notion.com/p/Convenciencia-Cuparaque-3aea16ed6e5f808d81b2cd9667bc047d)
(`3aea16ed6e5f808d81b2cd9667bc047d`), ainda vazia. Entrou no `CLAUDE.md` §7 com a ressalva de que
**não é fonte de número do modelo** — número vive na planilha.

### Três decisões abertas registradas em `docs/em-aberto.md`

1. **Arquitetura do segundo cérebro** — falta decidir a **segunda planilha** (gestão mensal de
   caixa, o realizado contra a meta). Nota registrada: ela **não** é terceira cópia do modelo,
   porque guarda o realizado, não o planejado — não há o que divergir.
2. **Caminho do MVP** — as 4 fases propostas (validação por WhatsApp → operação enxuta sem ponto →
   mirar o equilíbrio → formalização). ⚠️ Duas ressalvas anexadas: a Fase 0 valida **demanda, não
   margem**, e não substitui as cotações; e a Fase 1 já é decisão de investimento, o que **tensiona
   a R2** — que hoje não distingue MVP enxuto de investimento cheio.
3. **Distrito de Aldeia entra no raio de entrega?** Muda `Demanda!C10` direto. Pode ser a
   explicação do conflito populacional (3.958 × "~8 mil") — vale responder as duas juntas.

### Nada foi cotado

⚠️ Continua **zero** cotações reais. Nenhuma pesquisa externa foi feita nesta sessão. `CLAUDE.md`
§5 segue valendo integralmente.

---

## [30/07/2026] — Dashboard editável criado no Lovable + duas divergências aritméticas encontradas (Claude)

**Contexto:** sessão seguinte à da criação do repositório. O founder pediu, de novo, a página web no
Lovable. O escopo estava registrado como **não confirmado** em `docs/em-aberto.md`, então foi
perguntado antes de qualquer criação — como o próprio founder havia instruído.

**Decisão do founder:** entre as quatro opções em aberto, escolheu o **dashboard editável do modelo
financeiro**.

⚠️ **Essa escolha contraria a decisão de 30/07 registrada na entrada abaixo** ("planilha fica em
Excel, sem página web espelho"). A decisão nova é do founder e prevalece — mas o risco que a decisão
antiga evitava continua real: **agora existem duas fontes do mesmo modelo.** A mitigação adotada é a
única que funciona: **a página não tem nenhum resultado chumbado.** Todo número exibido é calculado
em tempo real a partir dos inputs, com as mesmas fórmulas de `docs/modelo/formulas.md`. Divergir só
é possível se as **premissas** divergirem — não os resultados.

**O que foi criado:** projeto Lovable **"Cuparaque Conecta"**
(`3e66cd92-bafc-489e-b9b4-d8a193d56977`), no workspace `yWut1L8QhIAJ9fMG61Ae`. Sete abas:
Premissas · Mix · Cascata · Demanda · DRE · Fluxo de caixa · Precificação. Motor de cálculo isolado
em `src/lib/viabilidade/model.ts`. Sem backend; estado em localStorage. Privado, não publicado.

**Conformidade com as restrições:**
- **R1** — banner fixo no topo, sem botão de fechar, declarando que nenhum número foi cotado. Todo
  valor exibido carrega selo (`INVENTADO` / `INFORMADO` / `DERIVADO` / `A CONFERIR`).
- **R7** — nenhum resultado chumbado; a cascata inteira recalcula ao mexer em qualquer input.
- **R4** — **participação de mercado virou input explícito** (slider, padrão 100%), com alerta
  quando está em 100%: *"isso não é um cenário, é um monopólio"*. Na planilha isso ainda está
  implícito em 100% — o dashboard corrigiu antes da planilha.
- **R3** — a comparação com PIB per capita só aparece acompanhada do aviso de que 40,7% do PIB local
  é administração pública.

**Duas divergências aritméticas encontradas ao reconferir a cascata** (achado desta sessão, não
resolvido — ver `docs/BACKLOG.md`):

1. **Capital da rampagem: R$ 44.850, não R$ 32.500.** Reproduzindo a curva exatamente como
   `docs/modelo/premissas.md` §7 a descreve (40% no mês 1 → 100% no mês 11, linear = +6 pontos/mês)
   com retirada integral desde o mês 1, o pior saldo acumulado dá **−R$ 44.850**. A entrada abaixo
   registra ~R$ 32.500. **Não sei qual está certo** — provavelmente a curva original tinha outro
   formato, que não ficou documentado. Não foi "corrigido" em lugar nenhum: os 12 meses da curva são
   editáveis no dashboard, então o número passa a sair de um input visível em vez de uma premissa
   implícita.
2. **Ponto de equilíbrio: ~306 pedidos/mês, não ~302.** `3.091 ÷ 10,0936 = 306,2`. Diferença
   pequena, sem efeito em nenhuma conclusão, mas o `CLAUDE.md` §6 e a entrada de 29/07 dizem ~302.

**Validação:** a cascata foi refeita à mão antes de escrever o prompt e confere no ponto que
importa — **a margem de contribuição total do mês maduro (R$ 13.591) bate exatamente com custo fixo
+ retirada (3.091 + 10.500)**, que é o fechamento que o planejamento reverso exige. Alíquota efetiva
recalculada pela tabela do Anexo I a partir do RBT12: 8,1344%. MC R$ 10,0936/pedido · 1.346,5
pedidos · R$ 74.058/mês · EBIT −R$ 666,67. O motor do dashboard foi lido linha a linha e reproduz
essas fórmulas.

**Ficou pendente:** o workspace do Lovable **ficou sem créditos** logo após o build inicial. Dois
ajustes não entraram: (a) bug de ponto flutuante exibindo `1.799999999 %` no campo de taxa de
cartão; (b) card "o que este modelo ainda não responde" na aba DRE. Estão no `docs/BACKLOG.md`.

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
