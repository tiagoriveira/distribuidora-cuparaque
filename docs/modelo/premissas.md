# Premissas do Modelo — status de confiabilidade

> **Este arquivo existe para uma coisa só: impedir que ficção autorizada vire base de decisão.**
>
> Regra R1 (`CLAUDE.md` §2): todo número carrega status. Os status usados aqui:
>
> | Status | Significa |
> |---|---|
> | `COTADO` | Preço/valor real, levantado com fornecedor, contrato ou fonte oficial |
> | `INFORMADO` | Fornecido pelo founder, **não verificado de forma independente** |
> | `DERIVADO` | Consequência aritmética de outros números, com a conta conferida |
> | `INVENTADO` | Escolhido por uma IA **a pedido explícito**, sem nenhuma cotação |
> | `A CONFERIR` | Depende de terceiro (contador, legislação) para ser confirmado |
>
> **Contagem atual: `COTADO` = 0 itens.** Nenhum número deste modelo foi cotado.
>
> A fonte executável é `modelo/plano_conveniencia_cuparaque.xlsx`, aba `Premissas`. Este arquivo
> documenta a **procedência**; a planilha carrega os **valores vigentes**. Se divergirem, a
> planilha manda — e este arquivo precisa ser corrigido.

---

## 1. Meta dos sócios

| Premissa | Valor | Status | Nota |
|---|---|---|---|
| Retirada por sócio | R$ 3.500/mês | `INFORMADO` | Confirmado pelo founder em 30/07/2026. Havia ambiguidade ("3,5k / 3 sócios") — resolvida: é **por sócio** |
| Nº de sócios | 3 | `INFORMADO` | |
| Retirada total | R$ 10.500/mês | `DERIVADO` | 3.500 × 3 |
| Lucro-alvo sobre o capital | **ausente** | — | ⚠️ O modelo **não tem** essa linha. Todo o resultado foi alocado como pró-labore. Ver `docs/BACKLOG.md` |

---

## 2. Dados de Cuparaque/MG

> Todos `INFORMADO` — fornecidos pelo founder, **não verificados de forma independente**.
> Nenhuma consulta a fonte oficial (IBGE, prefeitura) foi feita em nenhum momento deste projeto.

| Premissa | Valor | Nota |
|---|---|---|
| População | 3.958 hab. (projeção 2026) | ⚠️ Conflito não resolvido: o founder citou "~8 mil" antes. Ver `docs/em-aberto.md` |
| PIB per capita | R$ 20.995,06/ano | ⚠️ **R3** — não é renda disponível |
| PIB total municipal | R$ 83,6 milhões/ano | |
| Composição do PIB | Adm. pública 40,7% · Serviços e comércio 35,8% · Agropecuária 18,2% · Indústria 5,3% | A fatia pública é o motivo da R3 |
| Variação populacional | −14,89% no último Censo | Mercado encolhendo |
| Emprego formal 2026 | 37 admissões, 42 desligamentos (saldo −5) | |
| Densidade | 17,6 hab./km², concentrada no núcleo urbano e no distrito de Aldeia | |
| Eventos | AgroCupira (feira agropecuária, 1º semestre) + fluxo esportivo regional sazonal | Receita sazonal — nunca diluir na base |
| Obras públicas 2026 | Pavimentação + reforma do CEMEI (PLs 13, 14 e 16/2026) | |

---

## 3. Custos fixos — `INVENTADO`

> ⚠️ **Nenhuma cotação. Todos escolhidos por IA a pedido explícito do founder** ("invente um
> plausível"), porque os dados ainda não existiam. **Devem ser substituídos antes de qualquer
> decisão de investimento (R2).**

| Item | R$/mês |
|---|---|
| Aluguel de ponto pequeno | 900 |
| Energia elétrica (refrigeração 24h) | 700 |
| Água | 80 |
| Internet + telefone | 130 |
| Contador | 400 |
| Marketing local | 300 |
| Manutenção e diversos | 200 |
| Alvará e licenças (rateio) | 100 |
| Funcionário fixo | 0 — premissa: os 3 sócios operam |
| Contingência | 10% |
| **Total** | **R$ 3.091** (`DERIVADO` da soma + contingência) |

---

## 4. Mix de produtos — `INVENTADO`

> Participações e CMV escolhidos por IA. **O CMV ponderado de 67,35% que sai daqui alimenta o
> modelo inteiro** — é a premissa de maior impacto isolado.

| Categoria | Participação | CMV | Margem bruta | Papel |
|---|---|---|---|---|
| Cerveja gelada | 40% | 72% | 28% | Isca — traz o pedido, não dá lucro |
| Refrigerante / água / energético | 15% | 65% | 35% | Complemento |
| Destilados / vinho / ice | 10% | 58% | 42% | Puxa ticket |
| Snacks / doces | 12% | 62% | 38% | Impulso, alvo de upsell |
| Gelo / carvão / descartáveis | 8% | 40% | **60%** | **Maior margem da loja** |
| Cigarro / tabacaria | 8% | 88% | 12% | Isca de tráfego, não promover |
| Mercearia emergencial | 7% | 76% | 24% | Compra de urgência |
| **CMV ponderado** | | **67,35%** | **32,65%** | `DERIVADO` — conferido: Σ(part. × CMV) |

**Achado de 30/07/2026 (`DERIVADO`, conferido):** ordenado por **contribuição à margem** em vez de
faturamento, o ranking muda — **gelo/carvão sobe de 5º para 3º (14,7% da margem com 8% da
receita)** e **cigarro cai para último (2,9% da margem)**. A soma das contribuições fecha em
0,3265, idêntica a `1 − 67,35%`, o que valida a decomposição.

---

## 5. Custos variáveis e operação — `INVENTADO`

| Premissa | Valor | Nota |
|---|---|---|
| Taxa de cartão/Pix | 1,8% da receita | Proporcional à receita |
| Perdas e quebras | 1,5% da receita | Proporcional. **É a premissa que o operador mais controla** |
| Custo pago por entrega | R$ 3,50/pedido | Fixo em reais |
| Taxa de entrega cobrada | R$ 3,00/pedido | Fixo em reais — subsídio de R$ 0,50 |
| % de pedidos delivery | 75% (resto retirada) | |
| Embalagem | R$ 1,20/pedido | Fixo em reais |
| Dias de operação | 30/mês | |
| Horas de operação | 9h/dia (15h–00h) | → 270h/mês por sócio, se não houver revezamento |
| Ticket mínimo delivery | R$ 25 | ⚠️ **Provavelmente errado** — ver `docs/BACKLOG.md` |
| **Ticket médio planejado** | **R$ 55** | ⚠️ **Alavanca principal do modelo** |
| Moradores por domicílio | 3,1 | |
| % domicílios no raio de entrega | 80% | |
| RBT12 estimado (Simples) | R$ 877.000 | Usado para achar a faixa |

---

## 6. Tributário — `A CONFERIR COM CONTADOR`

**Faixas do Simples Nacional Anexo I (LC 123/2006) usadas no modelo — vigência NÃO confirmada:**

| Limite inferior | Alíquota nominal | Parcela a deduzir |
|---|---|---|
| R$ 0 | 4,00% | R$ 0 |
| R$ 180.000,01 | 7,30% | R$ 5.940 |
| R$ 360.000,01 | 9,50% | R$ 13.860 |
| R$ 720.000,01 | 10,70% | R$ 22.500 |
| R$ 1.800.000,01 | 14,30% | R$ 87.300 |
| R$ 3.600.000,01 | 19,00% | R$ 378.000 |

**Alíquota efetiva resultante no modelo: 8,13%** (`DERIVADO`).

⚠️ **Substituição Tributária NÃO implementada.** Bebidas e cigarros são tipicamente ICMS-ST — o
ICMS já foi recolhido pelo fabricante, e o varejista pode **segregar** essa receita e não pagar de
novo dentro do Simples. Como o modelo não faz isso, **o imposto está provavelmente
superestimado**. Numa loja majoritariamente de bebida, o efeito pode ser relevante.

**Isso é pergunta obrigatória para contador, não para IA.**

---

## 7. Premissas adicionadas em 30/07/2026 — `INVENTADO`

> Introduzidas ao produzir as análises de fluxo de caixa, valuation e estoque. **Mesma natureza:
> escolhidas para a demonstração funcionar, sem nenhuma base.**

| Premissa | Valor usado | Onde entra | Nota |
|---|---|---|---|
| Curva de rampagem | 40% no mês 1 → 100% no mês 11 | Fluxo de caixa | **Sem benchmark, sem fonte.** Determina o capital de giro da abertura |
| Investimento fixo | R$ 40.000 | DRE (depreciação), payback | Freezers, balcão, reforma, moto |
| Vida útil / depreciação | 5 anos, linear → R$ 667/mês | DRE | Critério gerencial, não fiscal |
| Taxa de desconto | 12% ao ano | Valuation, custo de carregar estoque | **Escolhida como número redondo.** Não é referência de mercado |
| Cobertura de estoque | 15 dias | Estoque, capital de giro | |
| Lead time do fornecedor | 3 dias | Ponto de pedido | ⚠️ **Desconhecido de verdade** — pode ser semanal, o que muda tudo |
| Prazo do fornecedor (PMP) | 0 dias (à vista) | Ciclo financeiro | Premissa pessimista: CNPJ novo sem histórico |

---

## 8. O que NÃO é premissa e não deve ser tratado como dado

| Item | O que é de fato |
|---|---|
| "3 a 5% do orçamento familiar como teto de conveniência" | **Regra de bolso de IA.** Não é pesquisa, não tem fonte. Usada no veredito de plausibilidade |
| "Elasticidade acima de 3 já é alta" | Julgamento de IA, sem fonte |
| Magnitudes de efeitos psicológicos de preço | **Deliberadamente ausentes.** Os conceitos são estabelecidos, mas nenhuma magnitude foi citada por falta de referência verificável (R5) |
| Múltiplos de mercado para venda do negócio | **Deliberadamente ausentes** por falta de fonte |
| Taxa livre de risco vigente | **Deliberadamente ausente** — é dado de mercado, muda toda hora. Consultar na fonte no dia da decisão |
