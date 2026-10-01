# Entrega 1 — Modelo Conceitual (DER)
### Modelagem de um sistema de gestão de informações para uma organização de pequeno porte
---

## Metadados

- Otavio 48763390
- Lucas 048587885

## 1. Caracterização da Organização

- **Nome e natureza da organização:** NexaStore Comércio Digital Ltda., conhecida comercialmente como NexaStore.
- **Contexto e porte:** A NexaStore é uma empresa de pequeno a médio porte, com uma operação voltada principalmente para vendas online.
Atualmente, a empresa possui aproximadamente 9 funcionários, distribuídos entre diferentes setores da operação:
- **Problemas e necessidades identificados:** Durante a análise da organização, foi identificada uma dificuldade principalmente relacionada à falta de integração entre as informações utilizadas na operação.

Atualmente, parte dos dados é controlada utilizando diferentes planilhas, registros manuais e informações presentes nas próprias plataformas de venda.
Esse modelo de funcionamento pode causar diversos problemas durante a rotina da empresa.
Entre os principais problemas identificados estão:
planilhas diferentes utilizadas para controlar estoque, vendas e fornecedores;
dificuldade para manter o estoque atualizado;
possibilidade de vender produtos que já estão sem estoque;
demora para localizar informações sobre determinados pedidos;
dificuldade para acompanhar pedidos vendidos em diferentes plataformas;
ausência de um histórico centralizado de clientes;
dificuldade para identificar rapidamente os produtos mais vendidos;
erros na separação de produtos semelhantes;
dificuldade no controle de cores, modelos e outras variações dos produtos;
dificuldade para acompanhar fornecedores;
informações duplicadas em diferentes planilhas;
necessidade de conferir informações manualmente;
possibilidade de erros durante a atualização do estoque.
- **Justificativa da escolha:** A NexaStore foi escolhida por possuir diversos processos que podem ser melhorados com a implementação de um sistema de informação.
Por comercializar mais de 70 produtos diariamente, a empresa precisa lidar constantemente com informações relacionadas a clientes, produtos, estoque, pagamentos, fornecedores e entregas.
A utilização de planilhas e controles separados começa a dificultar o gerenciamento da operação conforme o número de vendas aumenta.
A empresa também representa um bom caso para o desenvolvimento do projeto porque possui processos que estão diretamente relacionados entre si.
- **Evidências da organização:** https://loja.nexapaybrasil.com.br/
---

# 2. Processos de Negócio

A partir da análise da NexaStore Comércio Digital Ltda., foram identificados os principais processos relacionados à operação de comércio eletrônico da empresa. Esses processos estão diretamente relacionados ao cadastro e gerenciamento de clientes, produtos, fornecedores, estoque, vendas, pagamentos e entregas.

## 2.1 Principais processos mapeados

### 1. Cadastro e gerenciamento de clientes

Processo responsável pelo registro e manutenção dos dados dos clientes da NexaStore.

**Fluxo principal:**

Cliente → Cadastro → Registro dos dados → Cadastro de endereço → Atualização das informações

O sistema deve permitir armazenar dados como nome, CPF, e-mail, telefone, data de nascimento e status do cliente. Um cliente também pode possuir mais de um endereço cadastrado.

---

### 2. Cadastro e gerenciamento de produtos

Processo responsável pelo cadastro dos produtos comercializados pela empresa.

**Fluxo principal:**

Categoria → Cadastro do produto → Cadastro das variações → Definição de preços → Produto disponível para venda

Os produtos podem possuir diferentes variações, como cor e tamanho. Cada variação deve ser identificada individualmente para permitir um controle de estoque mais preciso.

---

### 3. Controle de estoque

Processo responsável pelo acompanhamento das quantidades disponíveis dos produtos.

**Fluxo principal:**

Entrada de produtos → Atualização do estoque → Venda/reserva → Saída do estoque → Registro da movimentação

Cada variação de produto possui seu próprio controle de estoque. As movimentações podem representar entradas, saídas, reservas ou ajustes.

Esse processo é importante para reduzir problemas como venda de produtos que já estão indisponíveis.

---

### 4. Gerenciamento de fornecedores

Processo responsável pelo cadastro dos fornecedores e pelo relacionamento deles com os produtos comercializados.

**Fluxo principal:**

Cadastro do fornecedor → Associação aos produtos → Registro do custo de compra → Atualização das informações

Um mesmo fornecedor pode fornecer diversos produtos e um mesmo produto pode ser fornecido por diferentes fornecedores.

---

### 5. Realização e gerenciamento de pedidos

Processo responsável pelo registro das vendas realizadas pela loja virtual e pelos marketplaces.

**Fluxo principal:**

Cliente → Pedido → Itens do pedido → Verificação de estoque → Pagamento → Separação → Expedição → Entrega

Um pedido pode possuir diversos itens, sendo que cada item está relacionado a uma determinada variação de produto.

---

### 6. Processamento de pagamentos

Processo responsável pelo registro e acompanhamento dos pagamentos realizados pelos clientes.

**Fluxo principal:**

Pedido → Seleção da forma de pagamento → Processamento → Aprovação/recusa → Atualização do status do pedido

O sistema deve registrar a forma de pagamento, valor, quantidade de parcelas, status e código da transação.

---

### 7. Expedição e entrega

Processo responsável pelo envio dos pedidos aos clientes.

**Fluxo principal:**

Pedido pago → Separação → Embalagem → Expedição → Transportadora → Rastreamento → Entrega

As informações de transportadora, código de rastreio e datas de envio e entrega devem ser armazenadas para permitir o acompanhamento do pedido.

---

### 8. Histórico dos pedidos

Processo responsável pelo registro das alterações realizadas nos pedidos.

**Fluxo principal:**

Alteração do pedido → Registro do status anterior → Novo status → Data da alteração → Histórico armazenado

Esse processo permite acompanhar a evolução do pedido desde sua criação até a conclusão ou cancelamento.

---

## 2.2 Integração entre os processos

Os processos identificados não funcionam de maneira isolada. Uma venda, por exemplo, envolve diferentes etapas da operação:

**Cliente → Pedido → Item do Pedido → Estoque → Pagamento → Expedição → Entrega**

Ao mesmo tempo, o pedido pode gerar movimentações no estoque e alterações no histórico.

Dessa forma, o sistema proposto deverá centralizar as informações e permitir que os processos compartilhem os mesmos dados.

---

# 3. Requisitos do Sistema

## 3.1 Requisitos Funcionais

Os requisitos funcionais representam as funcionalidades que o sistema deverá oferecer.

| Código | Requisito                                                                                       |
| ------ | ----------------------------------------------------------------------------------------------- |
| RF01   | O sistema deve permitir cadastrar clientes.                                                     |
| RF02   | O sistema deve permitir alterar e consultar os dados dos clientes.                              |
| RF03   | O sistema deve permitir cadastrar diferentes endereços para um cliente.                         |
| RF04   | O sistema deve permitir cadastrar categorias de produtos.                                       |
| RF05   | O sistema deve permitir cadastrar produtos e suas informações.                                  |
| RF06   | O sistema deve permitir cadastrar diferentes variações para um produto.                         |
| RF07   | O sistema deve permitir consultar a quantidade disponível de cada variação no estoque.          |
| RF08   | O sistema deve permitir registrar entradas, saídas, reservas e ajustes de estoque.              |
| RF09   | O sistema deve permitir cadastrar fornecedores.                                                 |
| RF10   | O sistema deve permitir associar produtos aos seus fornecedores.                                |
| RF11   | O sistema deve permitir registrar pedidos realizados pelos clientes.                            |
| RF12   | O sistema deve permitir adicionar vários itens a um pedido.                                     |
| RF13   | O sistema deve permitir registrar e acompanhar pagamentos.                                      |
| RF14   | O sistema deve permitir registrar informações de entrega e rastreamento.                        |
| RF15   | O sistema deve permitir consultar o histórico de alterações dos pedidos.                        |
| RF16   | O sistema deve atualizar o estoque de acordo com as movimentações realizadas.                   |
| RF17   | O sistema deve permitir consultar pedidos por cliente e número do pedido.                       |
| RF18   | O sistema deve permitir consultar produtos por categoria, nome ou SKU.                          |
| RF19   | O sistema deve permitir controlar o status de clientes, produtos, fornecedores e pedidos.       |
| RF20   | O sistema deve manter o relacionamento entre pedidos, produtos, pagamentos, estoque e entregas. |

---

## 3.2 Requisitos Não Funcionais

Os requisitos não funcionais representam características de qualidade e funcionamento esperadas para o sistema.

| Código | Requisito                                                                                                                                         |
| ------ | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| RNF01  | O sistema deve apresentar uma interface simples e de fácil utilização.                                                                            |
| RNF02  | O sistema deve apresentar tempo de resposta adequado para consultas e operações comuns.                                                           |
| RNF03  | O sistema deve possuir mecanismos de autenticação e controle de acesso.                                                                           |
| RNF04  | Os dados dos clientes devem ser armazenados de forma segura.                                                                                      |
| RNF05  | O sistema deve possuir disponibilidade adequada para permitir o gerenciamento da operação durante o horário de funcionamento da empresa.          |
| RNF06  | O banco de dados deve permitir o crescimento da quantidade de clientes, produtos e pedidos sem necessidade de reformulação completa da estrutura. |
| RNF07  | O sistema deve evitar duplicidade de informações utilizando identificadores e restrições de unicidade quando necessário.                          |
| RNF08  | O sistema deve manter a integridade dos relacionamentos entre as entidades.                                                                       |
| RNF09  | O sistema deve permitir futuras integrações com plataformas de venda e marketplaces.                                                              |
| RNF10  | O sistema deve permitir a realização de backups periódicos dos dados.                                                                             |

---

# 4. Regras de Negócio

## 4.1 Regras operacionais

**RN01 — Cadastro de clientes:**
Cada cliente deve possuir um identificador único.

**RN02 — CPF:**
O CPF de um cliente deve ser válido e não deve ser cadastrado mais de uma vez.

**RN03 — Endereços:**
Um cliente pode possuir um ou mais endereços cadastrados.

**RN04 — Produtos:**
Todo produto deve estar associado a uma categoria.

**RN05 — Variações:**
Um produto pode possuir várias variações, sendo que cada variação deve ser controlada individualmente.

**RN06 — SKU:**
Cada produto e cada variação deve possuir um código de identificação único.

**RN07 — Estoque:**
Cada variação de produto deve possuir um controle de estoque próprio.

**RN08 — Estoque negativo:**
A quantidade disponível em estoque não pode assumir valores negativos.

**RN09 — Venda:**
Um pedido não deve ser concluído quando a quantidade solicitada de uma variação não estiver disponível.

**RN10 — Itens do pedido:**
Um pedido deve possuir pelo menos um item para ser considerado uma venda válida.

**RN11 — Quantidade:**
A quantidade de um item do pedido deve ser maior que zero.

**RN12 — Pagamento:**
O pedido deve possuir um registro de pagamento para que possa avançar para as etapas posteriores definidas pela empresa.

**RN13 — Entrega:**
Um pedido pode possuir informações de entrega associadas após sua preparação para envio.

**RN14 — Rastreamento:**
Quando disponível, o código de rastreio deve estar associado ao pedido de entrega correspondente.

**RN15 — Histórico:**
Alterações relevantes no status do pedido devem ser registradas no histórico.

**RN16 — Fornecedores:**
Um produto pode possuir mais de um fornecedor e um fornecedor pode fornecer diversos produtos.

**RN17 — Movimentação de estoque:**
Toda alteração relevante na quantidade de estoque deve gerar uma movimentação correspondente.

**RN18 — Reserva:**
Produtos reservados para pedidos não devem ser considerados como livremente disponíveis para novas vendas.

---

## 4.2 Restrições organizacionais

A NexaStore trabalha com vendas realizadas por diferentes canais, principalmente loja virtual e marketplaces. Dessa forma, o sistema deve permitir centralizar os pedidos e evitar que informações de estoque sejam controladas de maneira independente em cada plataforma.

A quantidade de produtos vendidos diariamente também exige que o controle de estoque seja atualizado de forma consistente.

Além disso, produtos com diferentes modelos, cores e características precisam ser tratados como variações independentes. Isso evita que o sistema considere, por exemplo, uma capinha preta do Modelo A como equivalente a uma capinha azul do Modelo B.

Outra restrição importante está relacionada à proteção dos dados dos clientes. Informações pessoais devem ser armazenadas de maneira adequada e utilizadas somente para as finalidades necessárias à operação da empresa.

O modelo também deve permitir expansão futura, considerando o crescimento da quantidade de produtos, clientes, pedidos e fornecedores.

---

# 5. Dicionário de Dados Conceitual (Preliminar)

## 5.1 CLIENTE

| Atributo        | Descrição                | Regra de negócio associada                 |
| --------------- | ------------------------ | ------------------------------------------ |
| id_cliente      | Identificador do cliente | PK, obrigatório e único                    |
| nome            | Nome completo do cliente | Obrigatório                                |
| cpf             | CPF do cliente           | Obrigatório e único                        |
| email           | E-mail do cliente        | Deve possuir formato válido                |
| telefone        | Telefone de contato      | Opcional                                   |
| data_nascimento | Data de nascimento       | Deve ser uma data válida                   |
| data_cadastro   | Data do cadastro         | Obrigatório                                |
| status          | Situação do cliente      | Pode assumir valores como ATIVO ou INATIVO |

## 5.2 ENDERECO

| Atributo      | Descrição                        | Regra de negócio associada    |
| ------------- | -------------------------------- | ----------------------------- |
| id_endereco   | Identificador do endereço        | PK, obrigatório e único       |
| id_cliente    | Cliente proprietário do endereço | FK, obrigatório               |
| cep           | CEP do endereço                  | Deve possuir formato válido   |
| rua           | Nome da rua                      | Obrigatório                   |
| numero        | Número do imóvel                 | Obrigatório                   |
| complemento   | Complemento do endereço          | Opcional                      |
| bairro        | Bairro                           | Obrigatório                   |
| cidade        | Cidade                           | Obrigatório                   |
| estado        | Estado                           | Deve utilizar UF válida       |
| tipo_endereco | Tipo do endereço                 | Ex.: residencial ou comercial |

## 5.3 CATEGORIA

| Atributo     | Descrição                  | Regra de negócio associada |
| ------------ | -------------------------- | -------------------------- |
| id_categoria | Identificador da categoria | PK, obrigatório e único    |
| nome         | Nome da categoria          | Obrigatório                |
| descricao    | Descrição da categoria     | Opcional                   |
| status       | Situação da categoria      | ATIVO ou INATIVO           |

## 5.4 PRODUTO

| Atributo      | Descrição                 | Regra de negócio associada |
| ------------- | ------------------------- | -------------------------- |
| id_produto    | Identificador do produto  | PK, obrigatório e único    |
| id_categoria  | Categoria do produto      | FK, obrigatório            |
| sku           | Código interno do produto | Obrigatório e único        |
| nome          | Nome do produto           | Obrigatório                |
| descricao     | Descrição do produto      | Opcional                   |
| preco         | Preço de venda            | Deve ser maior que zero    |
| custo         | Custo de aquisição        | Maior ou igual a zero      |
| peso          | Peso do produto           | Maior que zero             |
| marca         | Marca do produto          | Opcional                   |
| status        | Situação do produto       | ATIVO ou INATIVO           |
| data_cadastro | Data de cadastro          | Obrigatório                |

## 5.5 VARIACAO_PRODUTO

| Atributo      | Descrição                 | Regra de negócio associada |
| ------------- | ------------------------- | -------------------------- |
| id_variacao   | Identificador da variação | PK, obrigatório e único    |
| id_produto    | Produto relacionado       | FK, obrigatório            |
| sku           | Código da variação        | Obrigatório e único        |
| cor           | Cor da variação           | Opcional                   |
| tamanho       | Tamanho da variação       | Opcional                   |
| preco         | Preço da variação         | Maior que zero             |
| codigo_barras | Código de barras          | Pode ser único             |
| status        | Situação da variação      | ATIVO ou INATIVO           |

## 5.6 ESTOQUE

| Atributo          | Descrição                  | Regra de negócio associada           |
| ----------------- | -------------------------- | ------------------------------------ |
| id_estoque        | Identificador do estoque   | PK, obrigatório                      |
| id_variacao       | Variação controlada        | FK, obrigatório e único              |
| quantidade        | Quantidade disponível      | Não pode ser negativa                |
| estoque_minimo    | Quantidade mínima desejada | Maior ou igual a zero                |
| estoque_reservado | Quantidade reservada       | Não pode ser negativa                |
| atualizado_em     | Data da última atualização | Atualizado nas alterações do estoque |

## 5.7 FORNECEDOR

| Atributo      | Descrição                   | Regra de negócio associada  |
| ------------- | --------------------------- | --------------------------- |
| id_fornecedor | Identificador do fornecedor | PK, obrigatório e único     |
| razao_social  | Razão social                | Obrigatório                 |
| nome_fantasia | Nome comercial              | Opcional                    |
| cnpj          | CNPJ                        | Obrigatório e único         |
| telefone      | Telefone de contato         | Opcional                    |
| email         | E-mail                      | Deve possuir formato válido |
| status        | Situação do fornecedor      | ATIVO ou INATIVO            |

## 5.8 PRODUTO_FORNECEDOR

| Atributo          | Descrição                        | Regra de negócio associada |
| ----------------- | -------------------------------- | -------------------------- |
| id_produto        | Produto fornecido                | FK, obrigatório            |
| id_fornecedor     | Fornecedor do produto            | FK, obrigatório            |
| custo_compra      | Custo de compra                  | Maior ou igual a zero      |
| codigo_fornecedor | Código utilizado pelo fornecedor | Opcional                   |

`id_produto` e `id_fornecedor` formam uma chave composta para identificar cada associação entre produto e fornecedor.

## 5.9 PEDIDO

| Atributo      | Descrição                         | Regra de negócio associada                 |
| ------------- | --------------------------------- | ------------------------------------------ |
| id_pedido     | Identificador do pedido           | PK, obrigatório e único                    |
| id_cliente    | Cliente responsável pelo pedido   | FK, obrigatório                            |
| id_endereco   | Endereço utilizado na entrega     | FK, obrigatório                            |
| numero_pedido | Número de identificação do pedido | Obrigatório e único                        |
| status        | Situação do pedido                | Deve possuir valores previamente definidos |
| subtotal      | Soma dos itens                    | Calculado                                  |
| desconto      | Desconto aplicado                 | Maior ou igual a zero                      |
| frete         | Valor do frete                    | Maior ou igual a zero                      |
| valor_total   | Valor final do pedido             | Calculado                                  |
| data_pedido   | Data e hora do pedido             | Obrigatório                                |
| atualizado_em | Última atualização                | Atualizado quando houver alterações        |

## 5.10 ITEM_PEDIDO

| Atributo       | Descrição             | Regra de negócio associada |
| -------------- | --------------------- | -------------------------- |
| id_item        | Identificador do item | PK, obrigatório e único    |
| id_pedido      | Pedido relacionado    | FK, obrigatório            |
| id_variacao    | Variação comprada     | FK, obrigatório            |
| quantidade     | Quantidade comprada   | Maior que zero             |
| preco_unitario | Preço de uma unidade  | Maior que zero             |
| desconto       | Desconto aplicado     | Maior ou igual a zero      |
| subtotal       | Valor total do item   | Calculado                  |

## 5.11 PAGAMENTO

| Atributo         | Descrição                    | Regra de negócio associada                |
| ---------------- | ---------------------------- | ----------------------------------------- |
| id_pagamento     | Identificador do pagamento   | PK, obrigatório e único                   |
| id_pedido        | Pedido relacionado           | FK, obrigatório                           |
| forma_pagamento  | Forma utilizada no pagamento | Ex.: PIX, cartão ou boleto                |
| valor            | Valor pago                   | Maior que zero                            |
| parcelas         | Quantidade de parcelas       | Maior ou igual a 1                        |
| status           | Situação do pagamento        | PENDENTE, APROVADO, RECUSADO ou ESTORNADO |
| codigo_transacao | Código da transação          | Pode ser único                            |
| data_pagamento   | Data do pagamento            | Pode ser nula enquanto pendente           |

## 5.12 ENTREGA

| Atributo         | Descrição                           | Regra de negócio associada         |
| ---------------- | ----------------------------------- | ---------------------------------- |
| id_entrega       | Identificador da entrega            | PK, obrigatório e único            |
| id_pedido        | Pedido relacionado                  | FK, obrigatório                    |
| transportadora   | Empresa responsável pelo transporte | Obrigatória quando houver envio    |
| codigo_rastreio  | Código de rastreamento              | Obrigatório quando disponibilizado |
| status           | Situação da entrega                 | Deve possuir valores definidos     |
| data_envio       | Data do envio                       | Pode ser nula antes do envio       |
| previsao_entrega | Data prevista para entrega          | Data válida                        |
| data_entrega     | Data efetiva da entrega             | Pode ser nula até a entrega        |

## 5.13 HISTORICO_PEDIDO

| Atributo        | Descrição                  | Regra de negócio associada         |
| --------------- | -------------------------- | ---------------------------------- |
| id_historico    | Identificador do histórico | PK, obrigatório e único            |
| id_pedido       | Pedido relacionado         | FK, obrigatório                    |
| status_anterior | Status anterior            | Pode ser nulo no primeiro registro |
| status_novo     | Novo status                | Obrigatório                        |
| descricao       | Descrição da alteração     | Opcional                           |
| data_alteracao  | Data e hora da alteração   | Obrigatório                        |

## 5.14 MOVIMENTACAO_ESTOQUE

| Atributo          | Descrição                     | Regra de negócio associada              |
| ----------------- | ----------------------------- | --------------------------------------- |
| id_movimentacao   | Identificador da movimentação | PK, obrigatório e único                 |
| id_variacao       | Variação movimentada          | FK, obrigatório                         |
| id_pedido         | Pedido relacionado            | FK, opcional                            |
| tipo              | Tipo de movimentação          | ENTRADA, SAIDA, AJUSTE ou RESERVA       |
| quantidade        | Quantidade movimentada        | Maior que zero                          |
| motivo            | Motivo da movimentação        | Pode ser obrigatório dependendo do tipo |
| data_movimentacao | Data e hora da movimentação   | Obrigatório                             |

---

# 6. Modelagem Conceitual

## 6.1 Entidades reconhecidas

Foram identificadas as seguintes entidades:

* **CLIENTE:** representa as pessoas que realizam compras na NexaStore.
* **ENDERECO:** armazena os endereços associados aos clientes.
* **CATEGORIA:** organiza os produtos comercializados.
* **PRODUTO:** representa os produtos disponíveis para venda.
* **VARIACAO_PRODUTO:** representa características específicas de um produto, como cor ou tamanho.
* **ESTOQUE:** controla as quantidades disponíveis de cada variação.
* **FORNECEDOR:** representa as empresas responsáveis pelo fornecimento dos produtos.
* **PRODUTO_FORNECEDOR:** registra a relação entre produtos e fornecedores.
* **PEDIDO:** representa uma compra realizada por um cliente.
* **ITEM_PEDIDO:** representa cada produto ou variação presente em um pedido.
* **PAGAMENTO:** registra as informações financeiras relacionadas aos pedidos.
* **ENTREGA:** representa o processo de envio do pedido ao cliente.
* **HISTORICO_PEDIDO:** registra as alterações realizadas no status dos pedidos.
* **MOVIMENTACAO_ESTOQUE:** registra alterações nas quantidades dos produtos em estoque.

## 6.2 Atributos e classificações

Os atributos foram classificados principalmente em:

* **Chaves primárias (PK):** identificam exclusivamente cada registro.
* **Chaves estrangeiras (FK):** estabelecem os relacionamentos entre as entidades.
* **Atributos descritivos:** armazenam características das entidades, como nome, descrição, telefone e endereço.
* **Atributos de controle:** representam status, datas e informações de acompanhamento.
* **Atributos calculados:** como subtotal e valor total do pedido, que podem ser obtidos a partir de outros dados.

## 6.3 Relacionamentos

Os principais relacionamentos definidos no modelo são:

| Relacionamento                          | Cardinalidade                         |
| --------------------------------------- | ------------------------------------- |
| CLIENTE — ENDERECO                      | 1:N                                   |
| CLIENTE — PEDIDO                        | 1:N                                   |
| CATEGORIA — PRODUTO                     | 1:N                                   |
| PRODUTO — VARIACAO_PRODUTO              | 1:N                                   |
| VARIACAO_PRODUTO — ESTOQUE              | 1:1                                   |
| PRODUTO — FORNECEDOR                    | N:N através de PRODUTO_FORNECEDOR     |
| PEDIDO — ITEM_PEDIDO                    | 1:N                                   |
| VARIACAO_PRODUTO — ITEM_PEDIDO          | 1:N                                   |
| PEDIDO — PAGAMENTO                      | 1:N                                   |
| PEDIDO — ENTREGA                        | 1:1                                   |
| PEDIDO — HISTORICO_PEDIDO               | 1:N                                   |
| VARIACAO_PRODUTO — MOVIMENTACAO_ESTOQUE | 1:N                                   |
| PEDIDO — MOVIMENTACAO_ESTOQUE           | 1:N, quando houver pedido relacionado |

## 6.4 Restrições e políticas aplicadas

O modelo considera que uma variação de produto deve possuir controle individual de estoque. Também considera que pedidos estão relacionados a clientes, itens, pagamentos e entregas.

A relação N:N entre produtos e fornecedores foi resolvida por meio da entidade associativa `PRODUTO_FORNECEDOR`, permitindo armazenar informações específicas dessa relação, como custo de compra e código utilizado pelo fornecedor.

---

# 7. Diagrama Entidade-Relacionamento (DER)

O DER foi elaborado considerando as entidades, atributos, relacionamentos e cardinalidades identificados durante o levantamento dos requisitos.

O modelo contempla:

* 14 entidades;
* chaves primárias;
* chaves estrangeiras;
* relacionamentos 1:N, 1:1 e N:N;
* entidade associativa para relacionamento entre produtos e fornecedores;
* controle individual das variações dos produtos;
* controle de estoque;
* pedidos e seus respectivos itens;
* pagamentos;
* entregas;
* histórico dos pedidos;
* movimentações de estoque.

**Anexar nesta seção a imagem do DER desenvolvido.**

O modelo foi estruturado de forma que possa receber novos clientes, produtos, pedidos e fornecedores sem que seja necessário alterar sua estrutura principal, permitindo sua evolução conforme o crescimento da NexaStore.

---

# 8. Justificativa Técnica

A modelagem foi desenvolvida considerando os principais processos realizados pela NexaStore e os problemas identificados durante a análise da organização.

A entidade **CLIENTE** foi criada para centralizar os dados dos consumidores e evitar que suas informações sejam armazenadas de forma duplicada em diferentes processos. A entidade **ENDERECO** foi separada de CLIENTE porque um cliente pode possuir mais de um endereço.

A entidade **CATEGORIA** permite organizar os produtos comercializados pela empresa. Já **PRODUTO** representa o item comercial de forma geral, enquanto **VARIACAO_PRODUTO** foi criada para representar características específicas, como cor, tamanho ou modelo.

Essa separação é importante para a NexaStore porque um mesmo produto pode possuir várias versões. Por exemplo, uma capinha pode existir para diferentes modelos de celular e em diferentes cores. Cada combinação pode possuir uma quantidade de estoque diferente.

O **ESTOQUE** foi relacionado diretamente à variação do produto para que o controle de quantidade seja realizado individualmente. Dessa forma, a venda de uma determinada variação não interfere incorretamente no estoque de outra.

A entidade **FORNECEDOR** representa as empresas que fornecem os produtos. Como um fornecedor pode fornecer vários produtos e um produto pode ser adquirido de diferentes fornecedores, foi utilizada a entidade associativa **PRODUTO_FORNECEDOR** para representar o relacionamento N:N.

Para representar as vendas, foram utilizadas as entidades **PEDIDO** e **ITEM_PEDIDO**. Essa separação é necessária porque um pedido pode conter vários produtos. O ITEM_PEDIDO permite registrar a quantidade e o preço específico de cada produto comprado.

A entidade **PAGAMENTO** foi criada para separar as informações financeiras dos demais dados do pedido, enquanto **ENTREGA** permite controlar o processo de envio e rastreamento.

A entidade **HISTORICO_PEDIDO** foi incluída para registrar alterações de status e manter um histórico da evolução dos pedidos.

Por fim, **MOVIMENTACAO_ESTOQUE** permite registrar as alterações ocorridas no estoque, tornando possível identificar entradas, saídas, reservas e ajustes.

A estrutura escolhida busca reduzir redundância, melhorar a integridade dos dados e facilitar futuras integrações com plataformas de venda e marketplaces utilizados pela NexaStore.

---

# 9. Uso de Inteligência Artificial

Durante o desenvolvimento do projeto foi utilizada a ferramenta **ChatGPT**, da OpenAI, como ferramenta de apoio à organização das informações, elaboração de requisitos, estruturação do dicionário de dados e desenvolvimento da modelagem conceitual.

A IA foi utilizada como apoio e não como substituição da análise realizada pelo grupo. As informações específicas sobre a NexaStore foram fornecidas a partir dos dados utilizados no projeto.

## 9.1 Registro dos usos da IA

| Item                                 | Registro                                                                                                                                                                                                        |
| ------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Item**               | **Registro**                                                                                                                                                                                                    |
| **Ferramenta e etapa** | ChatGPT — organização e formatação do dicionário de dados.                                                                                                                                                      |
| **Motivação**          | Utilizar a IA como apoio para organizar e padronizar as informações do dicionário de dados.                                                                                                                     |
| **Prompt utilizado**   | "Me ajude a organizar a formatação do dicionário."                                                                                                                                                              |
| **Resposta recebida**  | A IA auxiliou na organização e formatação do dicionário de dados.                                                                                                                                               |
| **Reflexão crítica**   | A IA pode sugerir estruturas genéricas que não necessariamente representam exatamente a realidade da organização. Por isso, as informações precisam ser verificadas e adaptadas aos processos reais da empresa. |


## 9.2 Uso da IA na documentação

Também foi utilizado o ChatGPT para auxiliar na elaboração e organização do dicionário de dados e das regras de negócio.

**Prompt utilizado:**

> "Para cada entidade identificada, liste: Atributo, Descrição e Regra de negócio associada."

A resposta foi utilizada como base para estruturar as tabelas do dicionário de dados. As regras foram adaptadas para representar o contexto da NexaStore, principalmente em relação ao controle de produtos, variações, estoque, pedidos e fornecedores.

A utilização da IA teve como objetivo auxiliar na organização e documentação do projeto, sendo necessária a análise humana para verificar se as informações propostas estavam de acordo com os processos da organização.


## Resumo dos Pesos

| Dimensão | Peso total |
|----------|-----------|
| Conceitual (contexto, requisitos/regras, modelagem, justificativa técnica) | 30% |
| Procedimental (requisitos, fluxogramas, dicionário de dados, DER) | 50% |
| Atitudinal (participação, comprometimento, colaboração, autonomia) | 20% |

**Entrega final:** README.md completo + DER + Dicionário de Dados em HTML (com exceção dos cursos GTI) anexado no repositório GitHub do grupo.
