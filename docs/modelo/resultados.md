# Resultados Vigentes do Modelo

> **O que é este arquivo:** o que o modelo produz **hoje**, com as premissas atuais.
>
> ⚠️ **Todos os números abaixo são `DERIVADO` de premissas `INVENTADO`.** A aritmética foi
> conferida; as entradas são ficção autorizada. Ler `docs/modelo/premissas.md` antes de usar
> qualquer coisa daqui em decisão.
>
> Fonte executável: `modelo/plano_conveniencia_cuparaque.xlsx`.

---

## 1. O resultado principal

| Indicador | Valor |
|---|---|
| Retirada total dos sócios | R$ 10.500/mês |
| Custo fixo total | R$ 3.091/mês |
| Resultado que a operação precisa gerar | R$ 13.591/mês |
| **Margem de contribuição** | **R$ 10,09/pedido (18,4% do ticket)** |
| **Pedidos necessários** | **1.347/mês** |
| **Faturamento necessário** | **R$ 74.058/mês** |
| Pedidos/dia | ~45 |
| Pedidos/hora (9h/dia) | ~5 |
| **Ponto de equilíbrio** | **~306 pedidos/mês (~10,2/dia)** |

> ⚠️ **[CORREÇÃO 31/07/2026]** Esta linha dizia **~302 pedidos/mês**. O valor certo é **~306**
> (`3.091 ÷ 10,0936 = 306,2`). Confirmado por duas vias independentes: o recálculo à mão e a
> **própria planilha**, cuja célula `Cascata!B29` traz **10,2 pedidos/dia** — que × 30 dias dá 306,
> não 302. Diferença sem efeito em nenhuma conclusão, mas o número errado estava replicado em
> `CLAUDE.md` §6 e no CHANGELOG de 29/07.

**Leitura da folga:** o equilíbrio exige ~10 pedidos/dia e a meta exige ~45. É uma **folga de
segurança grande** — um mês ruim não quebra a empresa, só reduz a retirada. Essa é a melhor
notícia do modelo.

### 1.1 Mapa de células — onde cada resultado vive na planilha

> Levantado em 31/07/2026 por uma sessão que abriu o `.xlsx` diretamente. **Útil para não ter que
> reabrir a planilha só para localizar um número.**

| Célula | O que é |
|---|---|
| `Premissas!C22` | Custo fixo total (R$ 3.091/mês) |
| `Cascata!B22` | Pedidos/dia na meta plena (~44,9) |
| `Cascata!B29` | Pedidos/dia no ponto de equilíbrio (~10,2) |
| `Mix!A6:B13` | As 7 categorias e suas participações |
| `Demanda!C10` | Domicílios endereçáveis |
| `Ofertas!A6:A11` | Os combos |
| `Leia-me!A28` | Aviso "NÃO VERIFICADO" — cobre custos, CMV, entrega, embalagem, perdas, cartão |
| `Leia-me!A40` | Registro do conflito populacional (3.958 × "~8 mil") |

---

## 2. Teste de realidade (aba `Demanda`)

| Indicador | Valor |
|---|---|
| Domicílios endereçáveis | ~1.021 |
| Compras por domicílio/mês exigidas | 1,32 |
| Gasto por domicílio/mês | ~R$ 72 |
| % do PIB per capita do domicílio | 1,3% |
| Veredito automático da planilha | **PLAUSÍVEL** |

⚠️ **Duas ressalvas graves sobre esse veredito, e ambas o tornam otimista:**

1. **R3 — o denominador.** Usa PIB per capita como proxy de renda familiar. **PIB per capita não é
   renda disponível** — 40,7% do PIB de Cuparaque é administração pública. Se a renda real for
   metade, o indicador vai para ~2,7%.
2. **R4 — a participação.** O cálculo assume **100% de participação de mercado**, sem declarar.

**Sensibilidade à participação de mercado** (`DERIVADO`, conferido em 30/07/2026):

| Participação | Domicílios | Compras/dom./mês | Gasto/dom. | % do PIB per capita |
|---|---|---|---|---|
| **100%** | 1.021 | 1,32 | R$ 72 | 1,3% |
| 70% | 715 | 1,88 | R$ 104 | 1,9% |
| **50%** | 511 | **2,64** | **R$ 145** | **2,7%** |
| 33% | 337 | **4,00** | **R$ 220** | **4,1%** |

**O veredito "PLAUSÍVEL" só sobrevive perto de 100% de participação.** Com um único concorrente
dividindo o mercado, a exigência por domicílio dobra. E aplicando também a ressalva de renda
(dobrar a última coluna): **5,3% com um concorrente, 8,1% com dois.**

> Nota de divergência: a planilha traz R$ 71,54 de gasto/domicílio; minha conta dá ~R$ 72,50.
> Arredondamento no número de domicílios. Não afeta conclusão.

---

## 3. Sensibilidade ao ticket médio (aba `Cenarios`)

| Ticket | MC/pedido | Pedidos/dia | Faturamento/mês |
|---|---|---|---|
| R$ 35 | R$ 5,85 | 77,4 | R$ 81.307 |
| R$ 45 | R$ 7,97 | 56,8 | R$ 76.718 |
| **R$ 55** | **R$ 10,09** | **44,9** | **R$ 74.058** |
| R$ 65 | R$ 12,22 | 37,1 | R$ 72.321 |
| R$ 75 | R$ 14,34 | 31,6 | R$ 71.099 |
| R$ 90 | R$ 17,52 | 25,9 | R$ 69.821 |
| R$ 110 | R$ 21,76 | 20,8 | R$ 68.698 |

**O ticket é a alavanca mais barata do modelo:** subir de R$ 55 para R$ 75 reduz o esforço
operacional em ~30% sem nenhum cliente novo.

---

## 4. Achados de 30/07/2026 — o que o modelo original não mostrava

> Os três produzidos ao escrever os cursos de fluxo de caixa, DRE e concorrência. Aritmética
> conferida. **Nenhum deles está na planilha ainda** — ver `docs/BACKLOG.md`.

### 4.1 O capital da rampagem: ~R$ 32.500

Com rampagem de 40% no mês 1 subindo a 100% no mês 11, e os sócios retirando os R$ 10.500 **desde
o mês 1**, o saldo acumulado afunda até **−R$ 32.564** no mês 10.

| Mês | % maduro | MC | Fixo+retirada | Resultado | Acumulado |
|---|---|---|---|---|---|
| 1 | 40% | 5.446 | 13.591 | −8.145 | **−8.145** |
| 3 | 60% | 8.170 | 13.591 | −5.421 | **−20.349** |
| 6 | 85% | 11.574 | 13.591 | −2.017 | **−29.124** |
| 10 | 97% | 13.208 | 13.591 | −383 | **−32.564** |
| 12 | 100% | 13.616 | 13.591 | +25 | **−32.514** |

**Esse dinheiro não é o freezer, nem a reforma, nem o estoque inicial.** É o custo de existir
enquanto as vendas sobem — e não aparecia em nenhum lugar de um modelo que só olha o mês maduro.

**Com retirada escalonada** (nada nos meses 1–4, metade nos 5–8, cheia a partir do 9), **o
acumulado nunca fica negativo** — fecha o ano em +R$ 30.486. **Diferença de ~R$ 63 mil na
necessidade de capital**, mesma loja, mesmas vendas. A única variável é *quando* os sócios começam
a tirar dinheiro.

⚠️ Essas tabelas são **resultado mensal em competência**, não fluxo de caixa completo. Falta
estoque comprado antes de vender, DAS do mês seguinte e investimento inicial. **O buraco real é
maior que R$ 32.500, não menor.**

### 4.2 Em DRE, o mês maduro dá prejuízo

| Linha | R$/mês |
|---|---|
| Receita bruta | 74.085 |
| (−) Imposto sobre venda | (6.023) |
| (−) CMV | (49.896) |
| **= Lucro bruto** | **18.166** |
| (−) Cartão, perdas, embalagem, entrega | (4.566) |
| *= Margem de contribuição* | *13.599* |
| (−) Custos fixos | (3.091) |
| (−) Pró-labore | (10.500) |
| **= EBITDA** | **8** |
| (−) Depreciação | (667) |
| **= LUCRO LÍQUIDO** | **(659)** |

O EBITDA é praticamente zero **por construção** — o planejamento reverso dimensionou as vendas
para cobrir exatamente custo fixo mais retirada, e acerta com precisão de R$ 8.

**O prejuízo sai inteiro da depreciação.** Tradução: o modelo paga o fornecedor, o aluguel, o
imposto e os três sócios — **mas não paga a reposição do freezer.**

⚠️ O sinal negativo é robusto (qualquer depreciação acima de R$ 8/mês produz prejuízo); **o
tamanho depende inteiramente** do investimento fixo de R$ 40.000, que é inventado.

### 4.3 A economia da margem baixa (18,4%)

| Movimento no preço | Efeito |
|---|---|
| Desconto de 5% | exige **+31,8%** de volume para empatar |
| Desconto de 10% | exige **+93,2%** — quase dobrar os pedidos |
| **Desconto de 20,7%** | **margem zero** — a partir dali, vender mais aumenta o prejuízo |
| Aumento de 10% | pode **perder 32,5%** dos clientes e ficar igual |

**A assimetria é a conclusão prática:** o preço tem muito mais espaço para cima que para baixo, e
o instinto do lojista aponta para o lado errado. Também significa que **posicionamento por preço é
aritmeticamente inviável** neste negócio.

⚠️ **Consequência sobre o ticket mínimo:** pela fórmula `MC(P) = 0,8857P − 38,62`, um pedido de
R$ 25 rende **−R$ 16,48**. A perda real é menor (pedido menor leva menos mercadoria, logo CMV
menor), **mas o sinal continua negativo** — entrega e embalagem não encolhem com o pedido. **O
ticket mínimo de R$ 25 precisa ser recalculado.**

---

## 5. O que o modelo ainda não responde

| Pergunta | Status |
|---|---|
| Vale a pena como investimento? | **VPL negativo** — não há linha de retorno ao capital. É compra de emprego, não investimento |
| Quanto é o investimento inicial? | Sem orçamento. Nenhum item cotado. **Confirmado em 31/07:** a planilha **não tem nenhuma aba ou seção de investimento inicial** — não existe célula de "orçamento mínimo para iniciar" |
| Qual o capital de giro? | Estimável (~R$ 24.920 com 15 dias de cobertura), mas depende do lead time real do distribuidor |
| Existe concorrência? | **Não mapeada.** Pode invalidar a projeção de demanda inteira |
| A alíquota está certa? | Provavelmente superestimada (ST não implementada) |
| A curva de rampagem é essa? | Inventada. Sem benchmark |

⚠️ **Sobre a regra "reservar 3 a 6 meses de custo fixo" como colchão de caixa.** Ela circulou numa
sessão de 31/07 e daria R$ 9,3 mil–R$ 18,5 mil. **Não use.** Dois problemas:

1. **É regra de bolso sem fonte** — cai na R5 exatamente como o "3 a 5% do orçamento familiar"
   já registrado em `premissas.md` §8.
2. **Ela ignora o termo que domina a conta.** O buraco da rampagem não é o custo fixo de
   R$ 3.091 — é a **retirada dos sócios de R$ 10.500/mês**, que é 3,4× maior. Por isso o número
   real é **R$ 32.500** (§4.1), não R$ 9–18 mil. A regra de bolso subestima o colchão em **2 a 3
   vezes**, e erra justamente para o lado que quebra a empresa.
