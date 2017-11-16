# Atividade
Desenvolva o diagrama de classes a seguir

![alt text](https://github.com/angelogluz/APII-TesteUnitario/blob/master/Mercadis.png "Diagrama de classes")


## Especificando requisitos
Alguns dos requisitos são:

**Produto**
- O nome de um produto deve possuir entre 5 e 20 caracteres
- Um produto não pode ter um estoque negativo
- O campo <code>preço</code> deverá ser maior do que 0
- O campo <code>preço</code> é obrigatório
- O campo <code>nome</code> é obrigatório

**Cliente**
- O <code>nome</code> do cliente deve possuir entre 3 e 40 caracteres
- O <code>CPF</code> deve ser composto por 14 dígitos, no formato xxx.xxx.xxx-xx
**Vendedor**
- O <code>nome</code> do cliente deve possuir entre 3 e 40 caracteres
- A <code>comissão</code> do vendedor deverá ser 10% da venda

**Venda**
- Não deverá ser possível realizar uma venda sem produto
- No deverá ser possvel realizar uma venda sem cliente
- No deverá ser possvel realizar uma venda sem vendedor
- O <code>totalVenda</code> deverá acumular as vendas do vendedor enquanto a aplicação estiver executando

**Novos requisitos podem ser identificados**

**Métodos podem e devem ser criados para a aplicação**
