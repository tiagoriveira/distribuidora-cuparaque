# BACKLOG — Conveniência com Delivery (Cuparaque/MG)

> **Este arquivo é o handoff entre sessões/agentes — SÓ pendência ATIVA.**
> Histórico de sessões passadas → `docs/CHANGELOG.md`. Futuro não-bloqueante → `docs/ROADMAP.md`.
> Se um item foi concluído, ele **sai daqui** e vira entrada no CHANGELOG.

---

## Estado atual rápido

```
Fase          : estudo de viabilidade — nada foi comprado, alugado ou contratado
Modelo        : funcional (7 abas, 159 fórmulas), estrutura confiável
Dados         : ZERO cotações reais. Todos os custos/CMV/ticket são INVENTADOS
Concorrência  : não mapeada — pode invalidar a projeção de demanda inteira
Decisão       : BLOQUEADA por R2 (não decidir investimento antes das 4 cotações)
```

---

## 🔴 Itens manuais — só o founder faz (e destravam tudo)

> **Estes são o gargalo do projeto.** Enquanto não existirem, todo refinamento do modelo é
> refinar ficção. Ordem por impacto no resultado.

- [ ] **(1) CMV real de 2 distribuidores da região** — é a premissa de maior impacto isolado do
      modelo (67,35% da receita). Perguntar preço por categoria, não média.
- [ ] **(2) Aluguel real de um ponto** que sirva à operação.
- [ ] **(3) Conta de energia com refrigeração 24h** — pedir a um comércio parecido da cidade.
- [ ] **(4) Alíquota do Simples COM segregação de ST**, com contador. O modelo usa 8,13% e
      provavelmente superestima.
- [ ] **(5) Lead time, pedido mínimo e prazo de pagamento do distribuidor.** Descoberto em
      30/07 como a pergunta de maior impacto financeiro que ninguém faz: prazo de 30 dias levaria
      o ciclo financeiro de +16 para −14 dias, valendo mais de R$ 25 mil de capital de giro.
- [ ] **(6) Mapeamento de concorrência** — método completo no curso de Concorrência (Notion).
      Mínimo viável: inventariar pontos físicos e horários, testar quem entrega como cliente,
      conversar com 15–20 moradores, perguntar ao representante do distribuidor.
      ⚠️ Perguntar **o que a pessoa já fez**, nunca **se ela usaria**.
- [ ] **(7) Investimento inicial item a item** (freezers, balcão, reforma, moto, placa). Hoje o
      modelo usa R$ 40.000 inventados para calcular depreciação.

---

## 🔲 Pendente — livre pra trabalhar

### Planilha — tornar recalculável o que hoje está chumbado (R7)

> As análises de 30/07/2026 foram calculadas à mão e escritas em texto no Notion. **Não
> recalculam.** Se uma premissa mudar, elas passam a mentir. Migrar para abas vivas.

- [ ] **Aba `FluxoCaixa`** — rampagem mês a mês + saldo acumulado. Inputs novos: curva de rampagem
      (% por mês) e política de retirada por fase. Saída-chave: o pior saldo acumulado.
- [ ] **Aba `DRE`** — a cascata completa até lucro líquido. Inputs novos: investimento fixo e vida
      útil (→ depreciação).
- [ ] **Aba `Valuation`** — VPL, TIR, payback simples e descontado. Inputs novos: taxa de desconto,
      horizonte, lucro-alvo sobre capital.
- [ ] **Aba `Precificacao`** — curva de desconto/aumento a partir de `MC(P) = P × (1 − prop%) −
      fixos`. Mostra o volume exigido por faixa de desconto e o preço em que a margem zera.
- [ ] **Aba `Estoque`** — giro, cobertura, capital imobilizado, ABC por faturamento **e por
      margem**, ponto de pedido. Inputs novos: dias de cobertura, lead time, custo de capital.
- [ ] **Aba `Concorrencia`** — participação de mercado como **input explícito** (R4). Hoje está
      implicitamente em 100% dentro da aba `Demanda`.
- [ ] Depois de criadas: atualizar os 7 cursos no Notion com nota de snapshot apontando para a
      planilha como fonte vigente.

### Correções no modelo atual

- [ ] **Recalcular o ticket mínimo de R$ 25.** Pela fórmula de margem, um pedido nesse valor tem
      margem negativa (−R$ 16,48 pela conta direta; menos que isso na real, porque o CMV cai com
      o pedido menor, mas ainda negativo). Exige decompor o CMV por faixa de pedido.
- [ ] **Adicionar linha de lucro-alvo sobre o capital.** Hoje todo o resultado é pró-labore, o que
      torna o VPL negativo por construção. Sem essa linha, o projeto é compra de emprego, não
      investimento. ⚠️ Adicioná-la **aumenta** o faturamento necessário, que já está na borda do
      que a cidade comporta — é provável que o modelo não feche. Descobrir isso é o ponto.
- [ ] **Tornar a participação de mercado um parâmetro da aba `Demanda`** (R4).
- [ ] **Alocar entrega e perdas por categoria**, para que a curva ABC por margem use margem de
      contribuição em vez de margem bruta. Hoje o gelo aparece melhor do que provavelmente é.

---

### Página web no Lovable — pedida, não executada

- [ ] **Criar a página web no Lovable.** Pedida pelo founder em 30/07/2026 (duas vezes). **Não foi
      criada:** o conector MCP do Lovable caiu no meio da sessão. Ele estava ativo e funcional —
      os workspaces chegaram a ser listados com sucesso antes da queda.
      - **Workspace definido:** `yWut1L8QhIAJ9fMG61Ae` — "Tiago's Lovable", onde o founder é
        **proprietário** (72 projetos, plano free). O outro (`paKQonUK9nol9R7XnpVO`, 13 projetos)
        é onde ele entra como colaborador.
      - **Escopo escolhido provisoriamente:** painel de leitura do estudo de viabilidade (números
        atuais, os três achados, o que falta cotar). ⚠️ **O founder não confirmou o escopo** —
        ver `docs/em-aberto.md`, entrada de 30/07 sobre a página web. **Confirmar antes de criar.**
      - ⚠️ **Requisito não-negociável da página:** os números exibidos são `INVENTADO` (R1). O
        aviso precisa estar **em destaque, não em rodapé**. Uma página bonita com "R$ 74.058/mês"
        no topo é exatamente o mecanismo que transforma ficção em decisão — e os outros dois
        sócios não acompanharam de onde esse número saiu.
      - **Alternativas se o conector não voltar:** (a) escrever o prompt completo para o founder
        colar no Lovable; (b) entregar a mesma página como HTML publicado.

---

## 🔒 Bloqueado — aguardando algo externo

- [ ] **Qualquer decisão de investir ou não** — travado por **R2**: as 4 cotações de campo não
      existem. Destrava quando os itens manuais 1–4 estiverem respondidos.
- [ ] **Validar a alíquota efetiva** — travado pelo contador (item manual 4).
- [ ] **Calibrar a curva de rampagem** — travado pelo mapeamento de concorrência (item manual 6).
      Concorrência estabelecida torna a rampagem mais lenta, o que aumenta o capital necessário.

---

## Pendências técnicas conhecidas (não-bloqueantes)

- **Divergência de arredondamento:** a planilha traz R$ 71,54 de gasto/domicílio; o recálculo de
  30/07 dá ~R$ 72,50. Origem provável: número de domicílios. Não afeta conclusão.
- **Conflito populacional não resolvido:** o founder citou "~8 mil habitantes" antes de enviar os
  dados de Cuparaque (3.958). O modelo usa 3.958. Ver `docs/em-aberto.md`.
- **`openpyxl` não instalado** no ambiente — necessário para editar o .xlsx programaticamente.
  Requer autorização do founder (regra 9 do padrão global).
- **A planilha é binária.** O Git versiona, mas não mostra diff útil entre versões. Toda mudança
  relevante precisa ser descrita no `CHANGELOG.md` — o commit sozinho não conta a história.
