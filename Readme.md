## Projeto Conceitual EER - E-commerce

--------

- ### Desafio:

  Refine o modelo apresentado acrescentando os seguintes pontos:

  Cliente PJ e PF – Uma conta pode ser PJ ou PF, mas não pode ter as duas informações;
  Pagamento – Pode ter cadastrado mais de uma forma de pagamento;
  Entrega – Possui status e código de rastreio;

- ##### Por não ter ainda aprendido no curso como aplicar as constraints. A melhor maneira que encontrei para restringir o pertencimento de apenas 1 CPF ou CNPJ por conta, foi especializando, criando uma subclasse PJ/PF em um relacionamento 1:1.

- ##### Ao pensar sobre os cartões, optei por criar uma entidade "Carteira" e adicionar as entidades "Cartão Débito/Credito" em um relacionamento 1..*, onde 1 carteira pode conter vários cartões. Tirando a necessidade de repetir campos com números de cartões, validade e etc em apenas uma entidade, especializando isso com subclasses, a entidade "Carteira" persistiria apenas os nomes dos cartões e o tipo "débito/crédito", puxando então as especificidades através do relacionamento.

- ##### Para não manter o controle das entregas, em um atributo dentro de pedidos, tendo que criar também outro atributos que compõe as entregas. Achei mais simples ter uma entidade própria para este controle. Criando um relacionamento onde um caminhão de "Entrega", pode entregar vários "Pedidos" 1..*.
