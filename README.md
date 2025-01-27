# lambda-fallback-calculadora-complexa

Esta função Lambda faz parte de um **circuit breaker serverless** implementado na AWS. Ela atua como fallback para a função principal [`lambda-calculadora-complexa`](https://github.com/CarlosGRSchneider/lambda-calculadora-complexa), fornecendo uma resposta simples em caso de falhas ou latência excessiva na função principal.

## Descrição

A função retorna uma mensagem estática para informar que o serviço não está disponível no momento. Esta abordagem garante que o sistema forneça um feedback amigável ao invés de erros técnicos.

## Exemplo de Retorno

A resposta é fixa e segue o seguinte formato:

```
"Desculpe estamos em obras no momento, por favor tente mais tarde."
```

## Estrutura do Projeto

### Classe Principal

1. **`FallbackCalculadora`**
   - Contém a lógica para retornar a mensagem estática.

## Relação com a Função Principal

Esta função é o fallback para a [função principal](https://github.com/CarlosGRSchneider/lambda-calculadora-complexa), que realiza cálculos com simulação de alta latência. Quando a função principal apresenta desempenho insatisfatório, o circuito redireciona as requisições para esta função.


