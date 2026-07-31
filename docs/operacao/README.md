# Operação — memória do dia a dia

> **O que é esta pasta:** a memória operacional do negócio — o que aconteceu de fato, não o que o
> modelo projeta. Criada em 31/07/2026, quando o founder decidiu consolidar o segundo cérebro
> **neste repositório, aberto como vault do Obsidian**, em vez de mantê-lo no Notion.
>
> ⚠️ **Hoje está quase vazia, e isso está certo:** o negócio **não existe**. Não há mês para
> fechar, rotina para registrar nem fornecedor para cotar. Esta pasta é o lugar preparado para
> quando existir — não uma pendência.

---

## A divisão que evita duas fontes divergindo

| Isto | Vive aqui? | Onde vive |
|---|---|---|
| O que **aconteceu** (realizado) | ✅ Sim | Esta pasta |
| O que o modelo **projeta** (planejado) | ❌ Não | `modelo/plano_conveniencia_cuparaque.xlsx` |
| **Premissa** e seu status R1 | ❌ Não | `docs/modelo/premissas.md` |
| **Regra** vigente | ❌ Não | `CLAUDE.md` |
| Decisão **ainda não tomada** | ❌ Não | `docs/em-aberto.md` |

**A regra em uma frase: aqui entra o realizado, não o planejado.** Não é uma segunda cópia do
modelo — é o contraponto dele. Por isso as duas fontes não podem divergir: não calculam a mesma
coisa.

⚠️ **Nenhum número do modelo é repetido aqui.** Se um documento desta pasta precisa citar um valor
projetado, ele **aponta** para a planilha ou para `docs/modelo/resultados.md`. Copiar o número cria
exatamente a mentira silenciosa que a **R7** existe para impedir.

---

## O que entra

- **`cotacoes-recebidas.md`** — toda cotação real que chegar. **É o documento mais valioso deste
  repositório**, porque é o único caminho por onde um `INVENTADO` vira `COTADO`.
- **Fechamento de mês** — quando houver operação: receita real por categoria, custo real,
  pedidos/dia reais, comparados contra a meta da aba `Cascata`. É o *feedback loop* que valida ou
  derruba as premissas inventadas.
- **Rotinas e checklists** — abertura, fechamento, reposição, contagem de estoque.
- **Marketing** — o que foi publicado, quando, e o que aconteceu depois.

## O que NÃO entra

- **Número de modelo.** Vai para a planilha.
- **Regra nova.** Vai para o `CLAUDE.md`, e só depois de decidida.
- **Decisão pendente.** Vai para `docs/em-aberto.md`.
- **Anexo binário pesado.** Foto de nota e PDF de cotação podem entrar, mas com parcimônia — o Git
  versiona binário sem mostrar diff útil, e o repositório incha. Preferir transcrever o dado e
  guardar o arquivo só quando o comprovante em si importar.

---

## A regra que faz tudo isto funcionar

> ⚠️ **Um agente só enxerga o que foi commitado e enviado.**
>
> Editar no Obsidian e não dar push significa que a próxima sessão vai responder com a versão
> antiga **achando que é a atual** — e não tem como perceber sozinha. Se você registrou uma cotação
> aqui e não enviou, para qualquer IA que abrir este projeto ela **não existe**.
