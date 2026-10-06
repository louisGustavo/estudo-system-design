# Repositório de Estudos de System Design

Esse repositório va ser dedicado a estudo de system design, a ideia é aprender os conceitos na prática com pequenos desafios que não consumam muito tempo mas que serão feitos diariamente.

## A ideia

1. Gerar um pequeno desafio de system design onde o usuário deverá descrever a solução que será implementada 

Ex: "Um site de vendas de ingressos precisa controlar os assentos reservados por seus usuários de forma que mais de um usuário não consiga reservar a mesma cadeira. Quais recursos devemos implementar para que isso ocorra?"

2. O usuário descreve as ferramentas necessárias, os trade offs e quais ações tomar para certos pontos negativos

Ex: "Implementar um camada de cache na aplicação onde, quando o usuário for tentar reservar a cadeira, primeiro é verificado na camada de cache se o assento já não foi reservado nesse momento, em caso negativo faz a reserva ao cliente"

3. É feito uma primeira revisão da solução informada pelo usuário, onde deve dar dicas de possíveis melhorias ou pontos de atenção não observados na primeira solução

Ex: "Na solução acima, caso o usuário cancele a compra do assento, como voce irá controlar que o assento está disponível para uma próxima compra? E se o cliente simplesmente abandonar o site nesse meio tempo?

4. O usuário, com base nos pontos levantados, faz os ajustes na possível solução e pode passar novamente por uma etapa de revisão

5. Após satisfeito com a solução, o usuário pode pedir a revisão final da solução. Nessa etapa a solução deve ser analisada, salientar onde o usuário foi muito bem e apontar onde errou ou existem possíveis melhorias. Deve-se sugerir temas para estudar para aprender como utilizar ou reforçar temas com pouca profundidade de entendimento

6. O ciclo se repete, o usuário pode pedir um novo desafio, porém deve-se analisar os desafios concluídos anteriormente para entender onde o usuário precisa melhorar, reforçar ou aprender um conceito novo

## Pontos Importantes

- Os desafios podem conter desde um conceito como:
    - Uso de filas
    - Comunicação Sincrona
    - Padrão de Cache
    - CDN
    - Blob Storage
    - Webhooks
    - Escolha de um banco de dados
    - Teorma CAP/PACELC
    - ACID
    - Read Replicas, sharding
    - Protocolos web
    - API Rest/GraphQL
    - Estimativa back-of-the-envelope estimation
    - Conceitos de disponibilidade, latência, escalabilidade
    - Load balancers
    - API Gateway Rate Limiting
    - Idempotência

- Importante que os termos aparecem em português e também em ingles para reforçar o vocabulário no idioma
- Os desafios devem ser curtos para que o usuário consiga fazer um todo dia com pouco tempo, mas não simples que não permita que o usuário aprenda novos conceitos
- Separe os desafios em pastas ou outra forma que fique fa?il de navegar por eles, mas também facilita as skills que serão criadas descritas no próximo tópico
- Importante que exiga do usuário os porques de cada escolha, apontando sempre os pontos positivos e negativos de cada escolha

## O que criar

A ideia seria criar 3 skills específicas deste repositório sendo:

1. /criar-desafio-system-design: responsável por analisar os desafios anteriores, e criar um novo sob demanda para atender os conceitos descritos anteriormente

2. /revisar-system-design: responsável por fazer uma revisão preliminar da solução do desafio proposto e propor melhorias e possíveis dúvidas para instigar o usuário a melhorar a solução

3. /avaliar-system-design: responsável por pontuar o desafio, dar um parecer final da entrega e incluir observações para auxiliar a primeira skill para criar um novo desafio mais personalizado

