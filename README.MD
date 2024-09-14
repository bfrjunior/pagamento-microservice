# 💳 Pagamento Service - Microsserviço
## 📄 Descrição
Este microsserviço é responsável pela validação de pagamentos dentro da aplicação de Loja Virtual. Ele realiza a verificação de cartões de crédito ou outros meios de pagamento através de um cliente de pagamento externo.

## 🔧 Funcionalidades
* 🔍 Verifica a validade do cartão de crédito fornecido no processo de compra.
* 💳 Integra-se com um cliente de pagamento externo para realizar a verificação.
## 🛠️ Estrutura de Código
Classe Principal: PagamentoService
Métodos:
* verificaPagamento(CartaoRequestDTO cartaoRequestDTO): Este método utiliza o cliente de pagamento para validar os dados de pagamento fornecidos, retornando um valor booleano que indica se o pagamento foi aprovado ou não.

Classe Controladora: PagamentoController
Rotas:
* POST /pagamento: Esta rota recebe um CartaoRequestDTO contendo os dados do cartão de crédito e retorna um valor Boolean indicando se o pagamento foi aceito ou não.
## 📦 Dependências
Este microsserviço depende dos seguintes componentes:

1. PagamentoClient 🧩: Um cliente externo que faz a verificação dos dados de pagamento.

2. CartaoRequestDTO 📋: Objeto de transferência de dados que encapsula as informações do cartão de crédito necessárias para a validação.

## 📜 Rota Disponível
1. Verificar Pagamento
* Método: POST
* Rota: /pagamento
* Descrição: Verifica a validade de um cartão de crédito ou outro meio de pagamento.
* Request Body:
```
    {
     "nome":"NOME",
     "numeroCartao":"5747859698080",
	 "mes":"01",
	 "ano":"2023",
	 "cvv":"5478",
    }
```
* Respostas:
   * 200 OK: Pagamento verificado com sucesso. Retorna true ou false dependendo da aprovação do cartão.
   * 500 Internal Server Error: Erro ao verificar o pagamento.

## 🔄 Fluxo de Processo
1. O microsserviço recebe uma requisição de pagamento.
2. Utiliza o PagamentoClient para verificar a validade dos dados do cartão de crédito.
3. Retorna um valor booleano indicando se o pagamento foi aprovado ou rejeitado.
## 🔄 Retornos
* ✅ true: Pagamento aprovado.
* ❌ false: Pagamento negado.