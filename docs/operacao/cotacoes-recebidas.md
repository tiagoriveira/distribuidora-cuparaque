# Cotações recebidas

> **Por que este é o documento mais valioso do repositório:** ele é o **único caminho** por onde um
> número deste projeto deixa de ser ficção. Hoje o modelo inteiro roda sobre valores `INVENTADO` —
> escolhidos por IA a pedido explícito, sem nenhuma cotação (`CLAUDE.md` §5). Enquanto esta página
> estiver vazia, **a contagem de `COTADO` é zero e a R2 bloqueia qualquer decisão de investimento.**

---

## Estado atual

```
Cotações recebidas : 0
Itens COTADO       : 0
R2                 : BLOQUEIA decisão de investimento
```

**Nada foi cotado.** Ver `docs/BACKLOG.md` § "Itens manuais" para as 7 perguntas de campo, em ordem
de impacto no resultado.

---

## O fluxo — uma cotação só vale quando tem as duas pernas

Registrar aqui **não basta**. Uma cotação que fica só nesta página não muda nenhum resultado,
porque o modelo não lê Markdown.

1. **Registrar aqui** — quem informou, quando, o quê, e o valor. Com o comprovante, se houver.
2. **Levar para a planilha** — `modelo/plano_conveniencia_cuparaque.xlsx`, aba `Premissas`.
   **É esta perna que recalcula a cascata inteira.**
3. **Trocar o status em `docs/modelo/premissas.md`** — de `INVENTADO` para `COTADO`, com a origem.
4. **Registrar no `docs/CHANGELOG.md`** — convenção do `CLAUDE.md` §8: *"substituir um `INVENTADO`
   por um `COTADO` é a mudança mais valiosa que este projeto pode receber"*.
5. **Sincronizar o dashboard do Lovable** — os padrões dele precisam acompanhar, senão as duas
   fontes divergem na entrada.

⚠️ **Sem o passo 2, os resultados continuam saindo do número inventado.**

---

## Como registrar

Copie o bloco abaixo para a seção "Cotações", preenchendo tudo. **Campo sem resposta fica escrito
"não perguntei" — não se preenche com estimativa** (R6).

```markdown
### [dd/mm/aaaa] — <item> — <fornecedor>

| Campo | Conteúdo |
|---|---|
| **Item cotado** | |
| **Valor** | R$ |
| **Unidade** | (por mês / por unidade / por caixa / % da receita) |
| **Fornecedor / fonte** | nome e contato |
| **Como foi obtido** | (visita / WhatsApp / telefone / tabela impressa / site) |
| **Validade da cotação** | |
| **Condições** | pedido mínimo, prazo de pagamento, lead time, frete |
| **Comprovante** | link ou arquivo, se houver |
| **Substitui qual premissa** | ex.: `premissas.md` §3 "Aluguel" |
| **Valor INVENTADO anterior** | R$ |
| **Levado para a planilha?** | ⬜ não / ✅ sim, em dd/mm |

**Observações:**
```

⚠️ **Uma cotação só, de um fornecedor só, não substitui a premissa** — vira um ponto, não um
preço de mercado. O `BACKLOG.md` pede **2 distribuidores** para o CMV justamente por isso. Com uma
única cotação, registre e marque a premissa como cotada **com a ressalva de amostra de um**.

⚠️ **Preço por categoria, nunca média.** O CMV ponderado (67,35%) sai do mix por categoria. Uma
média geral do fornecedor não alimenta a aba `Mix` e não serve.

---

## Cotações

*(nenhuma até 31/07/2026)*
