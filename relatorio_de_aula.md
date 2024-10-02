# Projeto de Assistente de Delivery com AWS Step Functions e Claude 3

Este projeto foi desenvolvido para criar um assistente de delivery personalizado que utiliza a IA generativa Claude 3, integrado com AWS Step Functions, para orquestrar diferentes serviços AWS. O assistente dessenvolvido permite que os usuários que 
façam pedidos recebam sugestões da IA para complementar o seu pedido. Por exemplo, uma  pessoa pede macarrão para um jantar romântico, e, com base nisso, a IA sugere três itens que combinam com a experiência gastronômica desejada, como vinhos se harmonizam com determinado tipo de massa,
molhos que combinam melhor com aquela determinada massa, etc. As respostas geradas são armazenadas em um histórico de conversação para referência
 futura e melhorias na personalização.


# AWS Step Functions

O foco principal do curso foi explorar as AWS Step Functions, um serviço que me permite coordenar vários serviços AWS em fluxos de trabalho visuais em um projeto prático. O Step Function é ideal para automatizar e orquestrar processos complexos, onde diferentes serviços precisam interagir de forma sequencial ou paralela.

## Workflow Studio

O Workflow Studio foi uma das ferramentas mais exploradas no projeto. É um ambiente visual intuitivo oferecido pelo Step Functions, que facilita a criação de fluxos de trabalho. No Workflow Studio, podemos arrastar e soltava os estados (steps) e serviços da AWS, organizando a lógica do Assistente de forma simples e clara. A interface visual ajuda a estruturar o fluxo de trabalho sem a necessidade de programar manualmente cada estado, o que agiliza o desenvolvimento.

## AWS State Language (ASL)

Além da interface visual do Workflow Studio, o curso abordou a AWS State Language (ASL), que é a linguagem baseada em JSON usada para descrever fluxos de trabalho no Step Functions. Mesmo que o Workflow Studio ofereça uma forma visual de construir fluxos, no backend é o ASL que define a lógica de execução. Durante o projeto, entendi a importância de compreender o ASL para depurar fluxos de trabalho e criar implementações mais avançadas e customizadas.

O ASL permite, por exemplo:

- Descrever estados e transições entre eles, como a execução de uma função Lambda, a espera por um evento ou a escolha de um caminho condicional (choice states).
- Definir falhas e como tratá-las dentro do fluxo de trabalho (retry e catch mechanisms), garantindo que o sistema seja resiliente a falhas.
- Integrar o fluxo com modelos de IA gerenciados no Bedrock para automação inteligente.

## Integração com AWS Bedrock

Outra parte essencial do projeto foi a integração com o AWS Bedrock, uma plataforma de IA generativa oferecida pela AWS, que permite a criação de modelos de linguagem customizados. Utilizou-se o Bedrock para gerar respostas personalizadas e lidar com interações conversacionais dentro do assistente de delivery. Aprendi como:

- Configurar um modelo de IA generativa para processar dados e gerar respostas inteligentes que podem ser usadas em chatbots ou assistentes, como no caso do delivery.
- Conectar o Bedrock ao fluxo de trabalho usando o Step Functions, para que a IA pudesse ser chamada automaticamente em determinados pontos do processo (por exemplo, quando o cliente fazia uma pergunta sobre o status do pedido).
- Manipular o output do modelo de IA dentro do fluxo, utilizando o ASL para transformar e direcionar os dados de volta ao cliente ou a outro serviço, dependendo da etapa do processo.
