# ROADMAP — Conveniência com Delivery (Cuparaque/MG)

> **O que é este arquivo:** features/melhorias **futuras e não-bloqueantes**. Nada aqui impede o
> trabalho atual de seguir.
>
> Diferença pro `BACKLOG.md`: lá é o que falta pra **agora**; aqui é o que ficou pra depois — com
> o **motivo** de estar esperando. Sem o motivo, ninguém sabe se já dá pra puxar o item.
>
> Ao promover um item daqui pro BACKLOG: **mova** a descrição, não copie.

---

## Ferramentas operacionais

- **App de operação diária** (registro de pedido do WhatsApp, baixa de estoque, ruptura, giro).
  Esperando porque: **só faz sentido depois que a loja existir.** É onde um app ganha do Excel com
  folga — uso diário, multiusuário, dados reais entrando. Enquanto for estudo de viabilidade, a
  planilha resolve melhor e custa dias a menos.

- **Caderno de ruptura.** Registrar o que o cliente pediu e não tinha. Esperando porque: depende da
  operação existir. ⚠️ Vale registrar aqui que **é a informação mais valiosa e mais facilmente
  perdida do varejo** — venda perdida não entra em sistema nenhum, e sem anotar desaparece para
  sempre. Um caderno na bancada resolve; nenhum sistema resolve sozinho.

- **Controle de estoque com curva ABC por margem.** Esperando porque: exige histórico de venda
  real. A análise conceitual já existe (curso de Estoque) e mostrou que a curva por faturamento
  classifica errado — gelo é 3º em margem e 5º em faturamento.

---

## Refinamentos do modelo

- **Projeção de caixa semanal** (em vez de mensal). Esperando porque: só importa quando a operação
  estiver apertada de verdade. O mês pode fechar positivo e o dia 8 fechar negativo, mas isso é
  problema de operação real, não de viabilidade.

- **Cenários pessimista / realista / otimista formalizados.** Esperando porque: com todas as
  premissas inventadas, três cenários de ficção não informam mais que um. **Faz sentido assim que
  as cotações reais existirem** — aí a incerteza vira faixa em vez de chute.

- **Sazonalidade modelada mês a mês** (AgroCupira, calendário do funcionalismo, calor/frio,
  eventos esportivos). Esperando porque: depende de conhecer o padrão local, que só o mapeamento
  de campo revela. ⚠️ Evento anual entra como **linha separada**, nunca diluído na base.

- **Curva de rampagem calibrada.** Esperando porque: depende do mapeamento de concorrência. A
  curva atual (40% → 100% em 11 meses) é invenção sem benchmark, e concorrência estabelecida a
  torna mais lenta.

---

## Expansão do negócio (só se o piloto funcionar)

- **Programa de recorrência / assinatura.** Esperando porque: exige base de clientes. ⚠️ Em cidade
  pequena o nº de clientes tem teto rígido — **frequência é a alavanca sem teto**, e é a mais
  subestimada. Vale mais que campanha de aquisição aqui.

- **Ampliação do raio de entrega** (distrito de Aldeia). Esperando porque: aumenta custo de
  entrega por pedido e exige que o núcleo urbano esteja saturado primeiro.

- **Posicionamento por horário** ("aberto quando ninguém está"). Esperando porque: depende do
  mapeamento revelar que essa brecha existe de fato. É o eixo mais barato de todos — custa decisão
  de escala de trabalho, não dinheiro.

---

## Materiais de apoio

- **Cursos restantes da série.** Sete já existem no Notion. Candidatos não escritos: precificação
  dinâmica, teste A/B de preço, previsão de demanda estatística, lote econômico de compra,
  modalidades de crédito para capital de giro. Esperando porque: os sete atuais cobrem o que o
  projeto precisa hoje, e curso sobre técnica que não será usada é peso morto.
