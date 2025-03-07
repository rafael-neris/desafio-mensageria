📌 Desafio de Mentoria: Processamento Assíncrono com RabbitMQ e SOLID

🎯 Objetivo

Este desafio tem como foco o desenvolvimento de um sistema que implemente RabbitMQ para comunicação assíncrona e siga os princípios SOLID para garantir boas práticas de desenvolvimento. O objetivo é criar um fluxo eficiente para processar pagamentos de forma escalável e desacoplada.

📜 Contexto

Uma fintech está desenvolvendo um sistema de pagamentos recorrentes, onde milhares de pagamentos precisam ser processados diariamente. Para garantir escalabilidade e manutenção eficiente, a empresa deseja estruturar o sistema de forma assíncrona utilizando RabbitMQ e aplicar os princípios SOLID no design da solução.

Você foi contratado para desenvolver essa solução e garantir que ela siga as melhores práticas de arquitetura de software.

🔹 Parte 1: Requisitos Base

1️⃣ API de Recebimento de Pagamentos

Criar uma API REST para receber solicitações de pagamento. O endpoint deve:

Aceitar requisições POST /pagamentos com um payload JSON contendo:

```
{
  "user_id": "5eec725c-ad2d-4f7e-9582-6663c8f04761",
  "valor": 100.50,
  "moeda": "BRL",
  "metodoPagamento": "cartao_credito"
}
```

Validar os dados da requisição.

Publicar a solicitação de pagamento em uma fila do RabbitMQ.

Rejeite valores negativos

Retornar uma resposta de sucesso imediatamente após enfileirar a mensagem.

2️⃣ Processador de Pagamentos

Criar um consumidor que:

Leia mensagens da fila do RabbitMQ.

Salve o pagamento no banco de dados

Utilize um gateway de pagamento simulado para processar a transação.
