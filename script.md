## Nome das Chaves

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

exists hello
type

"Falar sobre JSON"
"Falar sobre o clear"


```

## Padronizar

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