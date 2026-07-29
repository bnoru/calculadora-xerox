# Calculadora Xerox do Victor

Para utilizar: https://bnoru.github.io/calculadora-xerox/

Calculadora de orçamentos para gráfica/xerox, com geração de recibo e ordem de serviço. Arquivo HTML único, sem dependências externas (todo o CSS está embutido, sem necessidade de internet para funcionar).

## Categorias de serviço

- **Color** — papel comum, cartão/couchê (180/170g e 250g), adesivo, vegetal (A0 a A4), com preços em faixas por quantidade.
- **P/B** — mesma estrutura da Color, com sua própria tabela de preços.
- **Adesivos** — Leitoso corte simples e corte contorno (preço por m², com faixas de desconto por metragem) e Vinílico A3 (Branco/Transparente, preço fixo por unidade).
- **Revelação Fotográfica** — 10x15 e 15x21, preço fixo por unidade.
- **Outros serviços** — itens de descrição livre, com valor unitário e quantidade (para serviços avulsos, como estampas ou personalizações).

## Cálculo de preços

- Itens com **faixas de preço por quantidade**: a faixa aplicada é destacada em **negrito** na lista de preços, atualizando conforme a quantidade digitada.
- Itens de **adesivo** (corte simples/contorno): o preço por m² já soma 2mm de sangria em cada dimensão (largura e altura) antes de calcular a área, conforme a tabela oficial da empresa.
- Itens com **opção de corte**: um toggle adiciona uma taxa extra por unidade (R$1 por padrão, configurável por item — ex: R$10 no Vinílico A3).
- **Itens múltiplos do mesmo tipo**: um botão "+" ao lado de itens com corte (e dos dois tipos de adesivo) permite adicionar mais linhas do mesmo item — por exemplo, dimensões diferentes de adesivo, ou folhas com e sem corte do mesmo papel. Nos adesivos, a metragem de todas as linhas do mesmo tipo é somada para aplicar corretamente o desconto por quantidade, distribuindo o valor proporcionalmente entre as linhas.
- **Total Geral** fixo no topo da página, sempre visível ao rolar.

## Cliente / Designer

- Campo para nome do **cliente**, usado no recibo.
- Nome do **designer** salvo no navegador (persiste entre sessões), exibido como um "badge" fixo no canto do cabeçalho — clique no ícone de lápis para alterar.

## Recibo

- Botão que abre uma prévia do recibo (modal na própria página, sem pop-up) com logo, cliente, data/hora, lista de itens com **preço unitário** e subtotal, e total a pagar.
- Layout otimizado para impressão (fundo branco, para economizar tinta).

## Ordem de Serviço

- Documento interno para o setor de adesivos/vinil, com botão próprio de geração e impressão.
- Campos do pedido: número da nota, cliente, designer, data do pedido (automática), data/hora de entrega.
- Suporta **múltiplos itens** por ordem (arquivo, largura, altura, quantidade, material, acabamento, observações), cada um com botão de adicionar/remover.
- Se houver itens de adesivo já preenchidos na calculadora, eles são **importados automaticamente** como itens separados na ordem de serviço.
- Listas de **Material** (14 opções) e **Acabamento** (11 opções) configuráveis via menu dropdown.
- Campo de **cor** aparece automaticamente quando o material selecionado é "Recorte vinil" ou "Recorte emborrachado".

## Outras funcionalidades

- Botão **"Limpar tudo"** — zera todos os campos da calculadora (com confirmação), sem apagar o nome do designer salvo.
- Interface adaptada para impressão: tanto o recibo quanto a ordem de serviço imprimem apenas o conteúdo relevante (sem os botões da página).

## Estrutura técnica

- HTML/CSS/JS em um único arquivo, sem dependência de internet.
- CSS escrito à mão (subconjunto mínimo baseado em utilitários), organizado em seções comentadas para facilitar edições manuais.
- Nome do designer salvo via `localStorage` do navegador.
