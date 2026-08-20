// CÓDIGO ERRADO 1

## descrição do problema encontrado
O fluxo de edição de usuários estava inacessível na interface e o código continha falhas de segurança.

## quais foram os 3 erros de sintaxe/execução
Ausência do link "Editar" na tabela, falta da consulta (SELECT) via GET para carregar os dados no formulário e ausência do campo oculto (<input type="hidden" name="id">) para enviar o ID no salvamento.

## qual foi a falha de segurança
Vulnerabilidade a XSS causada pela exibição direta dos dados do banco no HTML sem higienização.

## como cada problema foi corrigido
Implementação completa da interface e lógica de edição, além do uso de htmlspecialchars() para neutralizar scripts maliciosos.

## evidências dos testes realizados
O ciclo do CRUD (criar, ler, editar e deletar) passou a funcionar integralmente e as tentativas de injeção de código XSS foram bloqueadas com sucesso.


// CÓDIGO ERRADO 2

## descrição do problema encontrado
O código travava a execução por erros de sintaxe, o botão e a lógica de edição de usuários não funcionavam na tela e os dados ficavam vulneráveis a ataques.

## quais foram os 3 erros de sintaxe/execução
Faltou um ; na linha do die() da conexão.

Faltou um ; na linha do bind_param() da edição.

Faltou o campo oculto do ID (<input type="hidden">) no formulário para a instrução UPDATE saber quem alterar.

## qual foi a falha de segurança
Ataque de XSS (Cross-Site Scripting), causado por imprimir dados do banco direto no HTML sem filtrar o conteúdo.

## como cada problema foi corrigido
Adicionados os ; faltantes, criado o fluxo completo de edição (link na tabela, busca por GET e ID no formulário) e aplicada a função htmlspecialchars() para tratar os dados exibidos.

## evidências dos testes realizados
A página voltou a carregar sem erros de PHP, o formulário passou a atualizar os dados do usuário corretamente e as tentativas de enviar scripts maliciosos viraram texto comum.