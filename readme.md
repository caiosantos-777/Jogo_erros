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



## quais foram os 3 erros de sintaxe/execução



## qual foi a falha de segurança



## como cada problema foi corrigido



## evidências dos testes realizados