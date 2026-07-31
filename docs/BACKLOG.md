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

### Consolidação no vault do Obsidian (decidida em 31/07)

- [ ] **Migrar os 7 cursos do Notion para o vault.** São o **único conteúdo do projeto que ainda
      vive fora do repositório** depois da decisão de 31/07. Enquanto estiverem lá: não são lidos
      automaticamente por nenhuma sessão, não têm histórico versionado, e continuam com as tabelas
      calculadas à mão que não recalculam. ⚠️ Migrar **não** resolve o problema das tabelas — isso
      depende das 6 abas novas acima. São dois trabalhos distintos.
- [ ] **Decidir o que fazer com a página do Notion** ["Conveniência
      Cuparaque"](https://app.notion.com/p/Convenciencia-Cuparaque-3aea16ed6e5f808d81b2cd9667bc047d),
      hoje praticamente vazia. Enquanto existir sem aviso, é candidata a virar segunda fonte por
      acidente. ⚠️ **Decisão do founder — não apagar nada por conta própria.**

### Abas propostas em 31/07 — aprovadas em escopo, não criadas

> Uma sessão do Claude no Excel propôs estas duas abas e **começou a criá-las, mas a conexão com o
> add-in do Excel caiu**. ⚠️ **Confirmado: a planilha NÃO foi modificada** — nenhuma das duas
> existe, e o `Leia-me` não recebeu a nota planejada.

- [ ] **Aba `Investimento Inicial`** — hoje **não existe nenhuma seção de investimento inicial na
      planilha**, e por isso não há como responder "qual o orçamento mínimo para começar?". Três
      blocos: **capex** (freezer/cervejeira/expositora, balcão, prateleiras, reforma leve, PDV) +
      **estoque de abertura** (giro inicial nas 7 categorias do `Mix`) + **capital de giro**.
      ⚠️ O bloco de capital de giro deve puxar do **fluxo de caixa (R$ 32.500)**, não de regra de
      bolso — ver a ressalva em `resultados.md` §5.
- [ ] **Aba `Roteiro MVP`** — as 4 fases propostas (validação por WhatsApp sem estoque → operação
      enxuta sem ponto → meta no equilíbrio, não na meta plena → formalização). ⚠️ **Só depois que
      o founder confirmar o caminho** — está em `docs/em-aberto.md`.
- [ ] **Investigar consignação com o distribuidor.** Estoque inicial em consignação é comum no
      varejo de bebida e reduz o capital de giro da abertura. Entra na pergunta do item manual (5),
      que já vai ser feita ao distribuidor de qualquer forma — custo marginal zero.

### Correções no modelo atual

- [ ] **Recalcular o ticket mínimo de R$ 25.** Pela fórmula de margem, um pedido nesse valor tem
      margem negativa (−R$ 16,48 pela conta direta; menos que isso na real, porque o CMV cai com
      o pedido menor, mas ainda negativo). Exige decompor o CMV por faixa de pedido.
- [ ] **Adicionar linha de lucro-alvo sobre o capital.** Hoje todo o resultado é pró-labore, o que
      torna o VPL negativo por construção. Sem essa linha, o projeto é compra de emprego, não
      investimento. ⚠️ Adicioná-la **aumenta** o faturamento necessário, que já está na borda do
      que a cidade comporta — é provável que o modelo não feche. Descobrir isso é o ponto.
- [ ] **Tornar a participação de mercado um parâmetro da aba `Demanda`** (R4). ℹ️ Já está feito no
      dashboard do Lovable (slider, padrão 100%, com alerta). **Na planilha continua implícito em
      100%** — as duas divergem nesse ponto até a planilha alcançar.
- [ ] **Alocar entrega e perdas por categoria**, para que a curva ABC por margem use margem de
      contribuição em vez de margem bruta. Hoje o gelo aparece melhor do que provavelmente é.

---

### Dashboard no Lovable — criado, com 2 ajustes travados por crédito

> **Criado em 30/07/2026.** Projeto **"Cuparaque Conecta"**
> (`3e66cd92-bafc-489e-b9b4-d8a193d56977`), workspace `yWut1L8QhIAJ9fMG61Ae`. Privado, não
> publicado. Escopo confirmado pelo founder: **dashboard editável do modelo**. Histórico completo
> no `docs/CHANGELOG.md`.

- [ ] **Corrigir bug de ponto flutuante nos campos percentuais.** O campo "Taxa de cartão/Pix"
      exibe `1.799999999 %` em vez de `1,8 %` — a fração armazenada (0.018) é multiplicada por 100
      sem arredondar. Conferir também participação e CMV na aba Mix, que usam o mesmo padrão.
- [ ] **Adicionar card "o que este modelo ainda não responde" na aba DRE:** ausência da linha de
      lucro-alvo sobre o capital, ST não implementada, curva de rampagem sem benchmark.
- ⚠️ **Ambos travados:** o workspace do Lovable **ficou sem créditos** após o build inicial.
      Destrava com créditos em https://lovable.dev/settings/billing.
- [ ] **Manter dashboard e planilha sincronizados.** São duas fontes do mesmo modelo — o risco que
      a decisão de 30/07 ("só Excel") existia para evitar. Hoje a mitigação é que **nada é
      chumbado** no dashboard: ele recalcula tudo a partir dos inputs. **Se uma premissa mudar na
      planilha, os padrões do dashboard precisam mudar junto**, senão as duas divergem na entrada.

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
- ✅ ~~Capital da rampagem: R$ 32.500 ou R$ 44.850?~~ **Resolvido em 31/07** — R$ 32.500 está certo.
  A curva real é **côncava** (40/50/60/70/80/85…), não linear; a prosa da `premissas.md` §7 é que
  descrevia errado. Agora é tabela mês a mês em `premissas.md` §7.1.
- ✅ ~~Ponto de equilíbrio: ~306 ou ~302?~~ **Resolvido em 31/07** — **~306**, confirmado pela
  célula `Cascata!B29` da própria planilha (10,2 pedidos/dia). Corrigido em `CLAUDE.md` §6 e
  `resultados.md` §1.
- ⚠️ **Meses 7, 8, 9 e 11 da curva de rampagem continuam desconhecidos** — ver `premissas.md` §7.1.
  Não afeta o R$ 32.500 (que vem dos meses 1–6 e do 10, todos publicados), mas quem implementar a
  aba `FluxoCaixa` deve tratar os 12 meses como inputs editáveis em vez de tentar recuperá-los.
- **Conflito populacional não resolvido:** o founder citou "~8 mil habitantes" antes de enviar os
  dados de Cuparaque (3.958). O modelo usa 3.958. Ver `docs/em-aberto.md`.
- **`openpyxl` não instalado** no ambiente — necessário para editar o .xlsx programaticamente.
  Requer autorização do founder (regra 9 do padrão global).
- **A planilha é binária.** O Git versiona, mas não mostra diff útil entre versões. Toda mudança
  relevante precisa ser descrita no `CHANGELOG.md` — o commit sozinho não conta a história.
