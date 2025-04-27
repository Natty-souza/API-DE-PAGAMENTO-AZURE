# 🛡️ API de Pagamento Segurança com Azure Functions

## 📚 Sobre o Projeto

Projeto desenvolvido como parte do desafio da DIO, com o objetivo de criar uma **API de Pagamento Segura** utilizando **Azure Functions** com **gatilho HTTP**.  
O foco principal é demonstrar como criar, testar e publicar uma função serverless no **Microsoft Azure**.

---

## 🚀 Tecnologias Utilizadas

- Azure Functions
- Node.js (JavaScript)
- Azure Portal

---

## 🛠️ O que foi feito

- Criada uma **Function App** chamada `minhapagamentoapi` no Azure.
- Dentro dela, criada a função HTTP `HttpTrigger1`.
- Implementado um endpoint que:
  - Recebe valor e método de pagamento.
  - Retorna uma confirmação de pagamento em formato JSON.

---

## 📂 Estrutura do Projeto


api-pagamento-azure/
README.md
HttpTrigger1
index.js
imagens
function-app.png
httptrigger-config.png
teste-funcao.png
host.json

## 📄 Código Principal 

    const valor = (req.body && req.body.valor);
    const metodo = (req.body && req.body.metodo);

    if (valor && metodo) {
        context.res = {
            status: 200,
            body: { mensagem: `Pagamento de R$${valor} realizado com sucesso via ${metodo}!` }
        };
    } else {
        context.res = {
            status: 400,
            body: { mensagem: "Por favor, forneça o valor e o método de pagamento." }
        };
    }



## 🧪 Teste da Função
Testes realizados diretamente pelo Portal Azure:


## Entrada:
{
  "valor": 150,
  "metodo": "Cartão de Crédito"
}

## Resposta:

{
  "mensagem": "Pagamento de R$150 realizado com sucesso via Cartão de Crédito!"
}
Status HTTP: 200 OK


## 🖼️ Prints do Projeto

📸 Tela da Function App criada no Azure:
![Captura de tela 2025-04-26 184049](https://github.com/user-attachments/assets/c5dd5d12-1b83-4b7b-8bc3-fa4aa835140e)


📸 Tela da função HttpTrigger1 configurada:
![Captura de tela 2025-04-26 171631](https://github.com/user-attachments/assets/756ff0b2-2053-4688-837a-eeff4474302d)

📸 Teste da função sendo executado:
![Captura de tela 2025-04-27 001559](https://github.com/user-attachments/assets/167dd5ee-4c53-42e2-b787-ec0e0cce0c06)


## 🔍 Insights
- Aprendi a criar uma API simples usando Azure Functions.
- Entendi melhor como funciona o fluxo de requisição/resposta HTTP no Azure.
- Conheci o processo de teste direto pelo portal Azure.

## ✨ Possibilidades futuras
- Integrar autenticação via Azure API Management para maior segurança.
- Implementar controle de erros mais robusto.
- Considerar métodos de pagamento como PIX ou carteira digital.
- Criar uma aplicação frontend para consumir essa API, como em e-commerces ou apps financeiros.

## 🔗 Link do Projeto no Azure
Acessar Function App Publicada: https://minhapagamentoapi.azurewebsites.net/api/HttpTrigger1


## 🎓 Conclusão
Esse projeto foi uma experiência enriquecedora que me ajudou a entender melhor o funcionamento de APIs no Azure. Agora me sinto mais confiante para desenvolver aplicações na nuvem! ☁️🚀



