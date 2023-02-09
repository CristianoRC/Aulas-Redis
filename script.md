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

### Ações para renomear
```
RENAME key newkey

RANDOMKEY
//Pegar uma random para testar, e nao precisar listar toda, ou verificar se existe alguma
//FLUSHALL
//Se não tiver nenhum retorna null

```


## TTL

```
TTL hello
EXPIRE hello 10  --10s

```

- -1 = eterno
- -2 key não existe
- **PERSIST** volta ao normal

## List

````bash
	rpush list-key item
	rpush list-key item2
	rpush list-key item
	
	lpop list-key --Remove item
````



## Sets

```bash
sadd set-key item
sadd set-key item2
sadd set-key item3
sadd set-key item

smembers set-key -- deleta tudo
```



## Hash

```bash
hset hash-key sub-key1 value1
hset hash-key sub-key2 value2
hset hash-key sub-key1 value1

hgetall hash-key
hdel hash-key sub-key2
```