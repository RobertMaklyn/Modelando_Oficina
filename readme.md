
# Oficina Mecânica - Modelagem de Banco de Dados
Este projeto apresenta um esquema de banco de dados para gerenciar as operações de uma oficina mecânica. O modelo foi criado para organizar e controlar informações sobre clientes, veículos, ordens de serviço (OS), equipes, mecânicos, serviços e peças.

## Objetivo do Banco de Dados
Gerenciar de forma eficiente:

- Clientes e seus veículos.
- Ordens de serviço (OS), incluindo serviços e peças utilizados.
- Equipes e mecânicos responsáveis pela execução dos serviços.
- Custos associados à mão de obra e peças.
## Principais Tabelas e Relacionamentos
- Cliente

Armazena informações sobre os clientes, como nome, endereço e telefone.
Relacionamento: 1:N
com Veículo (um cliente pode ter vários veículos).
- Veículo

Representa os veículos trazidos pelos clientes.
Relacionamento: 1:N
com Ordem de Serviço (OS) (um veículo pode ter várias OS).
- Ordem de Serviço (OS)

Contém informações das ordens de serviço, como data de emissão, status, valor total e data de conclusão.
Relacionamentos:1:N
com Serviços da OS (uma OS pode ter vários serviços).
com Peças da OS (uma OS pode utilizar várias peças).
N:1 com Equipe (uma OS é designada a uma equipe).
- Equipe

Gerencia as equipes de mecânicos responsáveis pelas ordens de serviço.
Relacionamento: 1:N
com Mecânico (uma equipe pode ter vários mecânicos).
- Mecânico

Representa os mecânicos com informações como especialidade e endereço.
Relacionamento: N:1 com Equipe (um mecânico pertence a uma única equipe).
- Serviços da OS

Representa os serviços executados em uma OS.
Relacionamento: N:1 com Tabela de Referência de Mão de Obra (vários serviços na OS podem referenciar o mesmo tipo de serviço).
- Peça

Armazena informações sobre as peças disponíveis para uso nas OS.
Relacionamento: 1:N
com Peças da OS (uma peça pode ser utilizada em várias OS).
- Peças da OS

Gerencia as peças utilizadas em uma OS.
Relacionamento: N:1 com OS (várias peças podem ser utilizadas em uma OS).
- Tabela de Referência de Mão de Obra

Contém os serviços disponíveis, com descrição e valor.
Relacionamento: 1:N
com Serviços da OS (um serviço pode ser usado em várias OS).
## Fluxo de Funcionamento
O cliente registra seus veículos na oficina.
Uma ordem de serviço (OS) é criada para cada atendimento, com data de emissão, status e equipe designada.
Os serviços executados são registrados com base na tabela de referência de mão de obra.
Peças utilizadas na OS são associadas à tabela de peças.
O valor total da OS é calculado com base nos serviços e peças utilizados.

Contribuições e sugestões são bem-vindas!