# Orçamento Online DT Locações

Versão do site da DT Locações em que o cliente monta o pedido sozinho: escolhe os itens, calcula o frete pelo CEP, aplica cupom e envia o pedido pronto pelo WhatsApp.

Criei para testar, com tráfego pago (Google Ads e Meta Ads), se um orçamento online completo gera mais contatos do que um site de vitrine simples.

## O que ele faz

- Catálogo com carrinho (quantidades por item, jogos de mesa com cadeiras, avulsos e forros).
- **Frete por CEP:** calcula a distância entre a loja e o endereço do cliente com a API Distance Matrix do Google Maps e aplica uma tabela por faixa de distância (até 10 km, até 20 km e acima). Para entregas longas com pedido pequeno, aplica uma taxa adicional.
- Preços promocionais por quantidade de jogos e de forros.
- Cupom de desconto.
- Formulário final (data do evento, cores dos forros, nome, endereço e forma de pagamento) que monta a mensagem e abre o WhatsApp com o pedido pronto.

## Resultado do teste

Depois de rodar a campanha, o volume de chamadas no WhatsApp **diminuiu** em relação à versão simples. Voltei para a versão simples, que converte melhor. Aprendi que mais funcionalidade nem sempre melhora a conversão, e que a decisão deve vir dos dados.

## Tecnologias

HTML, CSS e JavaScript · Google Maps JavaScript API (Distance Matrix) · Integração com WhatsApp (`wa.me`)

## Como foi feito

Desenvolvi com apoio de IA e vou estudar o código para entender cada parte, principalmente o cálculo de frete e o fluxo do carrinho.

## Como rodar

1. Crie uma chave de API no Google Cloud com a Maps JavaScript API ativada e **restrinja a chave ao seu domínio**.
2. No `index.html`, coloque a sua chave no lugar de `SUA_CHAVE_AQUI`.
3. Troque o endereço de origem e o número de WhatsApp pelos seus.
4. Os cupons do código (`CUPOM10` e `CUPOM5`) são de exemplo.
5. Os nomes das imagens precisam ser **idênticos** aos do código, inclusive maiúsculas e minúsculas, porque o GitHub Pages as diferencia.

> A chave de API real foi removida deste repositório.

## Limitações conhecidas e próximos passos

- [ ] O campo de validade dos cupons existe no código, mas **não é verificado**.
- [ ] A tabela de frete por faixas tem saltos de preço nos limites de 10 km e de 20 km. Avaliar uma fórmula contínua.
- [ ] Os cupons ficam visíveis no código da página. Para uso real, validar em um servidor.
- [ ] Trocar as imagens de cores (placeholders) por fotos reais dos forros.

## Plano de estudo deste projeto

Metas de aprendizado. Vou marcar cada item quando eu conseguir explicá-lo sem ajuda da IA.

- [ ] Como funciona uma chamada assíncrona à API do Google Maps
- [ ] Como o carrinho guarda e recalcula o total a cada mudança
- [ ] Como a mensagem do WhatsApp é montada e codificada para a URL
