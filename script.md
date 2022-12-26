## Nome das Chaves

string -> Texto

list -> Uma chave com vária strings

hash -> bom para dados complexos

Fila -> Sim ele funciona até mesmo como fila

Podemos guardar dados espaciais(geo), imagens...



## String

```bash
set hello world
get hello
del hello
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