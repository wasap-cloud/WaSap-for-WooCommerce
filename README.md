# WaSap for WooCommerce

Versão: 3.9.5

Plugin para WordPress/WooCommerce que envia notificações de WhatsApp para clientes e administradores usando a API WaSap.

## Requisitos

- WordPress 6.0 ou superior.
- WooCommerce 7.1 ou superior.
- WooCommerce ativo na loja.
- PHP/ionCube Loader, quando estiver usando o pacote protegido por ionCube:
  - ✅ PHP 8.2 - 8.4 + Loader 15.
- Necessário ter um plano [WaSap](https://wasap.com.br) ativo com pelo menos uma conexão de WhatsApp habilitada;

## Compatibilidade

- WordPress testado até a versão 7.0.2.
- WooCommerce testado até a versão 10.9.4.
- Compatibilidade com o High-Performance Order Storage (HPOS) do WooCommerce.

## Configurações do lojista

- Ativar ou desativar as notificações WaSap.
- Configurar a URL da API WaSap, o token, a conexão, o atendente e a fila.
- Definir o país padrão usado na normalização dos telefones.
- Informar um telefone de teste para validar a integração.
- Escolher se o bot deve ser desativado durante o atendimento e se o envio deve abrir um ticket.
- Definir quais status de pedido enviam mensagens aos clientes.
- Informar os telefones administrativos que receberão alertas da loja.
- Ativar ou desativar os campos de notificação no checkout, as campanhas promocionais e os logs ou o histórico de envios.
- Restaurar as configurações padrão quando necessário.

Os telefones de clientes e administradores devem estar no formato internacional, preferencialmente contendo apenas números. Antes de ativar os envios em produção, teste a integração e revise os textos das mensagens.

## Eventos automáticos

### Mensagens para clientes

- Pedido recebido, aguardando pagamento, em espera, em processamento, concluído, cancelado, reembolsado ou com falha.
- Criação, atualização ou mudança de status do pedido.

### Alertas para administradores e atendentes

- Novo pedido na loja.
- Novo usuário cadastrado.
- Pagamento aprovado.
- Pedido cancelado ou com falha.
- Falha no envio de uma notificação WaSap relacionada a um pedido.

## Personalização das mensagens

- Edite os modelos enviados aos clientes e os alertas enviados aos administradores.
- Personalize os modelos de novo usuário cadastrado e de mensagem manual.
- Restaure individualmente o texto padrão de cada modelo quando necessário.
- Use variáveis como nome do cliente, número do pedido, total, produtos, métodos de pagamento e entrega, links do pedido e nome da loja.

## Checkout, consentimentos e perfil do cliente

- Exiba no checkout o campo de telefone de WhatsApp e os consentimentos para notificações transacionais e comunicações promocionais.
- Mantenha o campo de telefone sem placeholder e preserve sua descrição auxiliar.
- Salve no pedido as preferências escolhidas e, quando aplicável, atualize também o cadastro do cliente.
- Permita que o cliente atualize o telefone e os consentimentos na área **Minha Conta**.
- Use o bloco de preferências em páginas de checkout personalizadas.

## Shortcodes

- `[wasap_profile]`: exibe o formulário para o cliente gerenciar o telefone e as preferências de notificação.
- `[wasap_checkout_notifications]`: exibe o bloco de telefone e preferências em páginas de checkout personalizadas.
- `[wasap_notification]`: oferece uma alternativa para exibir o bloco de notificações do checkout.

## Campanhas promocionais

- Crie campanhas para clientes que autorizaram comunicações promocionais e selecione manualmente os destinatários.
- Escreva a mensagem, adicione uma imagem opcional e agende a data e o horário do envio.
- Visualize campanhas recentes, seus status, destinatários e resumos de envio.
- Consulte os detalhes e cancele campanhas enquanto o cancelamento estiver disponível.
- Inclua uma opção para o cliente alterar suas preferências ou deixar de receber comunicações promocionais.

## Histórico e acompanhamento

- Consulte os envios recentes no painel administrativo e limpe o histórico quando necessário.
- Veja se cada mensagem está pendente, foi aceita, foi enviada ou falhou.
- Identifique o pedido ou evento relacionado e confira o resumo da resposta ou do erro.

## Elementor e páginas personalizadas

- Use os widgets WaSap do Elementor para o formulário de perfil e preferências ou para o bloco de notificações do checkout.
- Insira os shortcodes em páginas do Gutenberg, páginas da loja ou no widget **Shortcode** do Elementor.

## Responsabilidades do lojista

- Obter o consentimento dos contatos para cada finalidade aplicável e enviar campanhas somente a clientes com consentimento promocional.
- Manter as credenciais da WaSap protegidas.
- Conferir se os telefones cadastrados estão corretos.
- Testar a integração antes de ativar envios reais.
- Revisar as mensagens para evitar informações incorretas ou conteúdo indesejado.

## Instalação

1. Envie o arquivo `.zip` do plugin pelo painel do WordPress em **Plugins > Adicionar novo > Enviar plugin**.
2. Ative o plugin **WaSap for WooCommerce**.
3. Acesse **WaSap** no menu administrativo.
4. Informe a URL da API, token e demais credenciais fornecidas pela WaSap.
5. Configure os eventos de pedido e modelos de mensagem.
6. Use a aba **Ferramentas** para enviar uma mensagem de teste.

## Atualizações

O plugin possui atualizador próprio. Quando uma nova versão estiver disponível, ela aparecerá em **Painel > Atualizações** e na lista de plugins do WordPress.

Não é necessário instalar plugin adicional para receber atualizações.

## Observações

- As mensagens são enfileiradas e enviadas em segundo plano pelo WP-Cron.
- Envios com falha podem ser submetidos a novas tentativas pela fila assíncrona.
- A confirmação de sucesso indica que a solicitação foi aceita pela API WaSap.
- Entrega, leitura e demais eventos dependem do processamento da API WaSap.
- Para pacotes protegidos por ionCube, confirme que o servidor possui ionCube Loader compatível antes de ativar o plugin.
