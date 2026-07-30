# Fórmulas do Modelo

> **O que é este arquivo:** as fórmulas e como se encadeiam. **Não** carrega valores (isso é
> `premissas.md`) nem resultados (isso é `resultados.md`).
>
> A fonte executável é `modelo/plano_conveniencia_cuparaque.xlsx`. Este arquivo documenta a
> **lógica**; a planilha a **executa**. Se divergirem, a planilha manda.
>
> ⚠️ **Restrição técnica:** o recálculo é feito por **LibreOffice**. Não usar `XLOOKUP`, `FILTER`,
> `SORT`, `UNIQUE`, `SEQUENCE`. Usar `INDEX`/`MATCH`.

---

## 1. O encadeamento (quem alimenta quem)

```
Premissas ──┬──> Mix ──────────> CMV ponderado ──┐
            │                                     │
            ├──> Custos fixos ────────────────────┼──> Cascata ──> Pedidos, Faturamento
            │                                     │        │
            └──> Custos variáveis ────────────────┘        ├──> Demanda (teste de realidade)
                                                            ├──> Cenarios (sensibilidade)
                                                            └──> Ofertas (combos)
```

**Toda aba puxa de `Premissas`.** Nenhum número é digitado duas vezes. Alterar uma célula em
`Premissas` recalcula a cascata inteira — é o que a R7 exige.

Contagem atual: **159 fórmulas** — `Premissas` 7 · `Mix` 18 · `Cascata` 21 · `Demanda` 10 ·
`Cenarios` 84 · `Ofertas` 19.

---

## 2. O núcleo — margem de contribuição e volume necessário

```
Margem de contribuição por pedido =
      Ticket × (1 − CMV% − Imposto% − Cartão% − Perdas%)
    − (custo_entrega − taxa_entrega_cobrada) × %pedidos_delivery
    − embalagem_por_pedido

Pedidos necessários/mês  = (Custo fixo total + Retirada total) ÷ MC por pedido

Faturamento necessário/mês = Pedidos necessários × Ticket médio

Ponto de equilíbrio (pedidos/mês) = Custo fixo total ÷ MC por pedido
```

**Por que o ponto de equilíbrio usa a mesma fórmula:** é o volume necessário com o lucro desejado
zerado.

⚠️ **O erro que essa formulação corrige:** a conta ingênua *"R$ 30 mil de fixo + R$ 20 mil de
lucro = R$ 50 mil de faturamento"* está errada, porque faturamento não é margem. Com margem de
25%, seriam R$ 200 mil — quatro vezes o número errado.

---

## 3. Mix e CMV ponderado

```
CMV ponderado    = Σ (participação da categoria × CMV da categoria)
Margem bruta cat = 1 − CMV da categoria

Contribuição da categoria à margem total =
      participação × (1 − CMV) ÷ Σ[participação × (1 − CMV)]
```

**Checagem de consistência obrigatória:** a soma das participações deve dar 100%, e
`Σ[participação × (1 − CMV)]` deve fechar com `1 − CMV ponderado`. A planilha implementa a
primeira; a segunda foi conferida à mão em 30/07/2026 e fecha em 0,3265.

**Consequência não óbvia:** mudar **o que** você vende muda sua margem sem mexer em nenhum preço.

---

## 4. Tributário

```
Alíquota efetiva = (RBT12 × alíquota nominal − parcela a deduzir) ÷ RBT12
```

Onde `RBT12` = receita bruta dos últimos 12 meses. A faixa é localizada por `INDEX`/`MATCH` na
tabela do Anexo I.

**Problema circular:** a alíquota depende do faturamento, e o faturamento planejado depende da
alíquota. **Resolve-se por iteração** — chuta, calcula, ajusta uma ou duas vezes até convergir.

---

## 5. Teste de realidade (aba `Demanda`)

```
Domicílios endereçáveis = população ÷ moradores_por_domicílio × %_no_raio_de_entrega

Compras por domicílio/mês exigidas = pedidos necessários ÷ domicílios endereçáveis
Gasto por domicílio/mês            = faturamento necessário ÷ domicílios endereçáveis
```

⚠️ **R4 — a fórmula acima assume 100% de participação de mercado.** A versão correta é:

```
Domicílios que sobram para você = domicílios endereçáveis × participação_de_mercado_assumida
```

**A participação hoje não é um parâmetro da planilha** — está implicitamente em 100%. Torná-la
input é item do `BACKLOG.md`.

⚠️ **R3 — o denominador de renda.** O modelo compara o gasto exigido com o PIB per capita
(`PIB per capita ÷ 12 × moradores_por_domicílio`). **PIB per capita não é renda disponível.** Como
40,7% do PIB local é administração pública, o indicador é otimista por construção. Se a renda real
for metade, dobre o percentual resultante.

---

## 6. Análise de preço — margem em função do preço

> Derivada em 30/07/2026 para responder *"quanto de volume um desconto exige?"*. **Ainda não está
> na planilha** — item do `BACKLOG.md`.

A derivação separa os custos em dois tipos, que é o passo que quase todo mundo pula:

```
Custos FIXOS em reais por pedido (não caem com desconto):
    CMV + entrega_líquida + embalagem

Custos PROPORCIONAIS à receita (caem junto com o preço):
    imposto% + cartão% + perdas%

Logo:
    MC(P) = P × (1 − proporcionais%) − fixos_em_reais
```

```
Volume extra necessário para empatar após desconto = MC(P_original) ÷ MC(P_com_desconto) − 1
Volume tolerável de perda após aumento             = 1 − MC(P_original) ÷ MC(P_maior)
Preço em que a margem zera                         = fixos_em_reais ÷ (1 − proporcionais%)
```

⚠️ **Por que a conta de cabeça erra:** a intuição diz "margem de 18,4%, desconto de 10%, sobra
8,4%". Errado nos dois sentidos — o CMV **não** cai com o desconto (piora), mas imposto e cartão
caem (melhora um pouco). Só o cálculo resolve.

---

## 7. Fluxo de caixa e rampagem

> **Ainda não está na planilha** — item do `BACKLOG.md`.

```
Resultado do mês    = MC total do mês − custo fixo − retirada do mês
MC total do mês     = faturamento_do_mês × margem_de_contribuição%
faturamento_do_mês  = faturamento_maduro × %_da_curva_de_rampagem[mês]

Saldo acumulado[n]  = Saldo acumulado[n−1] + Resultado[n]
```

**A linha que decide tudo é o saldo acumulado**, não o resultado do mês. O **pior valor** dela é o
capital que precisa existir antes de abrir.

```
Capital necessário = investimento fixo
                   + estoque inicial
                   + |pior saldo acumulado|      ← o que o modelo original não mostrava
                   + caixa mínimo de reserva
```

**Ciclo financeiro:**
```
Ciclo operacional = PME + PMR
Ciclo financeiro  = PME + PMR − PMP
NCG ≈ ciclo financeiro (dias) × desembolso médio diário
```

Ciclo positivo = você financia a operação. Negativo = o fornecedor financia você.

---

## 8. Estoque

> **Ainda não está na planilha** — item do `BACKLOG.md`.

```
Giro de estoque   = CMV do período ÷ estoque médio
Cobertura (dias)  = estoque médio ÷ CMV diário
Estoque necessário = CMV diário × dias de cobertura desejados

Ponto de pedido   = (consumo diário × lead time) + estoque de segurança
Estoque segurança = consumo diário × dias de folga desejados

Custo de carregar estoque = estoque médio × custo de capital ao ano
```

⚠️ **Giro usa CMV, nunca faturamento.** Estoque está a custo; faturamento tem margem embutida.
Misturar infla o indicador.

---

## 9. DRE

> **Ainda não está na planilha** — item do `BACKLOG.md`.

```
    Receita bruta
(−) Impostos sobre venda
=   Receita líquida
(−) CMV
=   Lucro bruto
(−) Despesas de venda (cartão, perdas, embalagem, entrega)
=   [Margem de contribuição]        ← linha gerencial; não existe em DRE contábil
(−) Custos fixos operacionais
(−) Pró-labore
=   EBITDA
(−) Depreciação                     ← a linha que só a DRE enxerga
=   EBIT
(+/−) Resultado financeiro
=   Lucro líquido
```

⚠️ **Por que a DRE importa mesmo tendo a margem de contribuição:** depreciação **não sai da
conta**, então o fluxo de caixa a ignora corretamente; e **não é custo daquela venda**, então a
margem de contribuição a ignora corretamente. **Existe um custo real que nenhuma das duas
mostra** — e é onde o modelo deste projeto vira negativo.

```
Depreciação mensal = investimento fixo ÷ (anos de vida útil × 12)
```

---

## 10. Valuation

> **Ainda não está na planilha** — item do `BACKLOG.md`.

```
Valor presente = Valor futuro ÷ (1 + r)^n

VPL = −Investimento + Σ [ FC_n ÷ (1+r)^n ]

TIR = a taxa r que faz VPL = 0        (resolvida por aproximação numérica)

Payback simples    = Investimento ÷ geração de caixa anual
Payback descontado = período em que o VP acumulado cruza zero

Valor terminal (perpetuidade)  = FC ÷ r
Valor terminal (Gordon)        = FC × (1+g) ÷ (r − g)
```

⚠️ **Cuidados:**
- **VPL usa fluxo de caixa livre, não lucro contábil.**
- **TIR ignora tamanho** — 80% sobre R$ 1.000 rende menos, em dinheiro, que 20% sobre R$ 500.000.
  Na dúvida entre TIR e VPL, decida pelo VPL: ele está em reais.
- **`g` tem teto lógico** — nada cresce para sempre acima da economia em que vive.
- **Pró-labore deve estar descontado** antes de avaliar. Senão o "lucro" é salário disfarçado.
