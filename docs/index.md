# Índice de Contexto — Conveniência com Delivery (Cuparaque/MG)

> **Para qualquer IA/dev que abrir este repositório.** Este arquivo é **agnóstico de ferramenta**:
> não depende de nenhuma feature de agente específico, só de saber ler Markdown.
>
> **A regra:** leia o índice primeiro, decida o que é relevante, abra **só isso**. Nunca leia todos
> os docs "por garantia" — é justamente o desperdício que este padrão existe pra evitar.

---

## 1. Ordem de leitura (sempre, em qualquer tarefa)

1. **`CLAUDE.md`** (raiz) — a lei vigente: o que é o negócio, restrições, modelo, status dos dados.
2. **Este índice** — decide qual doc adicional ler, conforme a tarefa (tabela abaixo).

⚠️ **Se você vai tocar em QUALQUER número**, leia também `CLAUDE.md` §5 (Status dos dados) antes.
Quase todo número deste projeto é inventado, e usá-lo como fato é o erro mais grave possível aqui.

---

## 2. Tabela de roteamento — qual doc ler para qual tarefa

| Se a tarefa envolve... | Leia |
|---|---|
| Estado atual, o que falta fazer AGORA | `docs/BACKLOG.md` |
| Feature futura, não-bloqueante ("isso é roadmap ou é pra já?") | `docs/ROADMAP.md` |
| Histórico: o que já foi feito, quando e por quem | `docs/CHANGELOG.md` — use Grep pra achar o tema, não leia por inteiro |
| Decisão ainda não tomada / captura bruta pra processar depois | `docs/em-aberto.md` |
| **Mexer numa premissa, ou saber se um número é confiável** | `docs/modelo/premissas.md` |
| **Entender ou alterar um cálculo** | `docs/modelo/formulas.md` |
| **Saber o que o modelo produz hoje** | `docs/modelo/resultados.md` |
| Editar a planilha | `modelo/plano_conveniencia_cuparaque.xlsx` + `docs/modelo/formulas.md` |
| **Registrar uma cotação real que chegou** | `docs/operacao/cotacoes-recebidas.md` — **e seguir o fluxo de 5 passos de lá.** Registrar sem levar para a planilha não muda resultado nenhum |
| Fechamento de mês, rotinas, marketing — o que **aconteceu** | `docs/operacao/` |
| Conceito financeiro (o que é margem de contribuição, ciclo financeiro, VPL) | Os 7 cursos no [Notion](https://app.notion.com/p/3aca16ed6e5f815e9c87fa7ae4592859) — não estão neste repo |

---

## 3. O que cada arquivo É e NÃO é

| Arquivo | É | NÃO é |
|---|---|---|
| `CLAUDE.md` | Regra vigente, restrições, status dos dados | Histórico de sessões, roadmap |
| `docs/index.md` (este) | Índice de navegação | Fonte de verdade de qualquer regra |
| `docs/BACKLOG.md` | SÓ pendência ativa | Histórico de sessões — isso é o CHANGELOG |
| `docs/CHANGELOG.md` | Histórico cronológico (append-only) | Pendência ativa |
| `docs/ROADMAP.md` | Futuro não-bloqueante, com o motivo de estar esperando | Trabalho em andamento — isso é o BACKLOG |
| `docs/em-aberto.md` | Inbox de decisões pendentes ("segundo cérebro") | **NUNCA** fonte de verdade — só vira regra quando processado e movido |
| `docs/modelo/premissas.md` | Toda premissa + seu status de confiabilidade | Resultado — isso é `resultados.md` |
| `docs/modelo/formulas.md` | As fórmulas e como se encadeiam | Os valores |
| `docs/modelo/resultados.md` | O que o modelo produz hoje | Fonte executável — isso é a planilha |
| `docs/operacao/` | O **realizado** — o que aconteceu de fato | O **planejado** — isso é a planilha. Nenhum número de modelo é repetido lá |
| `modelo/*.xlsx` | **A fonte executável** do modelo | Documentação — não escreva explicação lá |

---

## 4. Sinais de entropia (avise o dono quando notar)

- `CLAUDE.md` acumulando narrativa/histórico em vez de só regra vigente.
- `BACKLOG.md` crescendo com sessões antigas que ninguém precisa reler pra saber o que fazer agora.
- Duas fontes dizendo coisas diferentes sobre a mesma regra.
- Um doc tão inchado que o agente é levado a lê-lo inteiro à toa.
- **Específico deste projeto:** um número aparecendo em texto sem status de confiabilidade (viola
  R1), ou um número chumbado que deveria ser input da planilha (viola R7).
- **Divergência planilha × Notion:** os cursos têm tabelas calculadas à mão que não recalculam.
  Se uma premissa mudar, elas mentem. Está mapeado no `BACKLOG.md`.

Ao mover algo entre docs, mova a **descrição** — não copie (senão as duas cópias divergem).

---

## 5. Manutenção deste índice

- Doc novo em `docs/`: adicionar linha nas tabelas §2 e §3.
- Mover item entre Backlog/Roadmap: não mexe aqui, só nos dois docs.
- ⚠️ **Reorganização estrutural** (criar/dividir/renomear doc, mudar a tabela §2) **não é
  automática** — o agente propõe e espera confirmação. A estrutura é o mapa que toda sessão segue.
