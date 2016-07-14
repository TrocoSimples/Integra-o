#Troco Simples Integração
Este projeto tempo por objetivo demonstrar como realizar as integrações com a API Troco Simples.

##Entidades
A sessão abaixo apresenta as diferentes entidades encontradas no sistema.

###Usuário
Os Usuário são todas as pessoas físicas cadastradas no sistema.

###Empresa
Empresa são as pessoas jurídicas cadastradas no sistema.
Toda empresa deve estar vinculada a um usuário, o qual será o administrador da empresa.

##Códigos de retorno
A API se utiliza dos códigos de retorno do protocolo http para informar o resultado das funções.
 
 200: Sucesso
 A função solicitada foi realizada com sucesso.
 Obs: Nem todas as funções retornam dados, no caso de sucesso.
 
 404: Não encontrado
 Para funções que retornam listas como "extrato" e "solicitações de pagamento", será retornado 404 para indicar que nenhuma informação foi encontrada.

400: Erro
Indica que a função não foi executada com sucesso.
Retorna a mensagem indicando o erro encontrado.

##Funções de integração para empresa

###Logar
O login é realizada por meio do e-mail e senha de usuário.
Como resposta será disponibilizado um token que deverá ser enviado no header da solicitação http de todas as demais funções.

###Listar empresas
Retorna a lista das empresas vinculadas ao usuário logado.
Dentre as informações das empresas está o enterpriseId, o qual deverá ser informado para realizar as demais funções da empresa.

###Obter saldo
Retorna o saldo atual da empresa.

###Obter extrato
Retorna a lista com as operações realizadas pela empresa.

###Obter solicitações de pagamento
Retorna a lista com as solicitações de pagamento realizadas pela empresa.

###Entregar troco
Realiza uma entrega de troca para o CPF informado.
Este CPF pode não ter usuário, nesse caso quando o usuário se cadastrar o valor será automaticamente creditado na sua conta.

###Solicitar pagamento
Realiza uma solicitação de pagamento para o CPF informado. Este CPF deve ter um usuário cadastrado no sistema.
Esta solicitação só irá aparecer no extrato mediante a confirmação por parte do usuário.

###Fechamento
Retorna o fechamento diário, mensal ou semanal em relação a data informada
