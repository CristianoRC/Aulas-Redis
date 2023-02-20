## Tipos das Chaves

string -> Texto

list -> Uma chave com vária strings

hash -> bom para dados complexos

Fila -> Sim ele funciona até mesmo como fila

Podemos guardar dados espaciais(geo), imagens...

## String

```bash
set hello world
set exemplo '{ 	"color": "red", "value": "#f00" }'
//sobescrever!

get hello
del hello
FLUSHALL

keys
keys hel*

exists hello
type

"Falar sobre JSON"
"Falar sobre o clear"

```

## Padronizar

- Padronizar para não ter duplicidade, e ser fácil de encontrar
- Dica para padrão: Entidade:identificador:campo/subIndentificador

```
SET report:1234:pdf http://teste.com/8a5e5a4f-805a
SET report:1234:csv http://teste.com/12b661e2-9d98
```

- Mostrar que a interface segmenta
- Facilita até mesmo a busca por todas as chaves de um tipo específico
- Fazer exemplo de busca por tipo específico

```
keys report:*:*
keys report:*:csv
keys report:1234:*
```

### Ações para renomear / Random Key

```
RENAME key newkey
//Exemplo de renomear um renatório de um user para o outro
RENAME report:1234:csv report:98:csv

RANDOMKEY
//Pegar uma random para testar, e nao precisar listar toda, ou verificar se existe alguma
//FLUSHALL
//Se não tiver nenhum retorna null

```

## TTL

Fazer uma breve revisada sobre o assunto, e relembrar que já falamos desses conceitos no início

```
TTL hello
EXPIRE hello 10   == 10s

The EXPIRE command supports a set of options:

NX -- Set expiry only when the key has no expiry
XX -- Set expiry only when the key has an existing expiry
GT -- Set expiry only when the new expiry is greater than current one
LT -- Set expiry only when the new expiry is less than current one

```

- -1 = eterno
- -2 key não existe
- **PERSIST** volta ao normal

- SETEX / SETNX

```
SET report:98:csv exemplo1 EX 30

SET report:98:csv exemplo2 EX 20 //Com tempo de expiração

SETNX report:98:csv exemplo3 //Se nao existir
```

## Strings

- INCR / INCRBY / DECR / DECRBY
  Falar sobre poder ser atualziando entre você buscar somar e setar
  Se não existir, ele cria!

```
//INCR / INCRBY

SET pages:123:views 0
INCR pages:123:views
INCRBY pages:123:views 50

//DECR / DECRBY
DECR pages:123:views
DECRBY pages:123:views 50

```

- APPEND / SETRANGE / GETRANGE

```
APPEND example "Ola"
APPEND example " Mundo!"
//Retorna quantidade de characters

SETRANGE example 5 "World!"
//E se não tiver, como saber o tamanho final?f
STRLEN example
GETRANGE example 5 11	

```

## List

Muito bom quando você só precisa fazer operações simpels, como adicionar ao remover das pontas
Serve muito para imitar pilhas e filas, decks...

```bash
	rpush compras:123:carrinho item
	rpush compras:123:carrinho item2
	rpush compras:123:carrinho item //falar que da para ter duplicação

	lpush compras:123:carrinho letft-item

	//Adicionando mais de um
	rpush compras:123:carrinho item1 item2 item3

	//ver todos 
	lrange compras:123:carrinho 0 -1

	//Se não quiser tem um fim, só colcoar -1 no lugar do 3
	lrange compras:123:carrinho 0 3

	lpop compras:123:carrinho //remove o primeiro da lista
	rpop compras:123:carrinho //remove o ultimo da lista
	rpop compras:123:carrinho "N" //remove n onjetos da esquerda ou direita


	llen compras:123:carrinho

	LINDEX compras:123:carrinho 0
	LINDEX compras:123:carrinho -1 / -2 //Ultimo, penultimo...

	ltrim compras:123:carrinho start stop //mantem apenas o que você colocar na lista o -1 serve aqui também
```


## Sets

```bash
sadd set-key item
sadd set-key item2
sadd set-key item3
sadd set-key item

smembers set-key -- deleta tudo

```

### Sorted set

 ```

```
## Hash

```bash
hset hash-key sub-key1 value1
hset hash-key sub-key2 value2
hset hash-key sub-key1 value1

hgetall hash-key
hdel hash-key sub-key2
```
