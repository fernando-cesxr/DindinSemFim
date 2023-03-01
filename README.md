# DindinSemFim

Uma API para web controle de gastos pessoais 


## Endpoint

- Despesas
    - Cadastrar 
    - Pagar 
    - Atualizar
    - Listar todas
    - Mostrar detalhes
- Contas
- Categorias


--- 


### Cadastrar despesas

`POST`/api/despesa

| campo | tipo | obrigatório | descrição
|------ |------|:-----------: |---------
|valor | decimal | sim | valor da despesa deve ser maior que zero
|data| data | sim | a data da despesa | 
|categoria_id| int | sim | código de uma categoria previamente cadastrada
|conta_id|int|int|o código de uma conta previamente cadastrada
|descricao|texto|nao|um texto sobre a despesa com no maximo de 255 caracteres   

**Exemplo de corpo de requisição** 

```js
{
    valor: 100.00,
    data: '2023-02-28',
    categoria_id: 1,
    conta_id: 1,
    descricao: 'cinema',
}
```


**Exemplo de corpo da respota**

**Cógigos de respota**

|código| descrição
| - | -
|201 | despesa cadastrada com sucesso
|400 | os campos enviados sao invalidos


---
...
### Detalhar Despesas
`GET`/api/desepas/{id}       
```js
{
    valor:100,0,
    data: '2023-02-28',
    categoria: {
        categoria_id: 1,
        nome: 'lazer',
    },
    conta: {
        conta_id: 1,
        conta_nome: 'itaú',
    },
    descricao: 'cinema'
}
```


**Cógigos de respota**

|código| descrição
| - | -
|200 | dados retornados com sucesso
|404 | não existe despesa com o id informado
