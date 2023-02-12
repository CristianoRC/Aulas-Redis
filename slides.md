---
theme: "night"
transition: "slide"
title: "Cache Distribuído"
enableMenu: false
enableSearch: false
enableChalkboard: false
---

![Cache](https://upload.wikimedia.org/wikipedia/en/thumb/6/6b/Redis_Logo.svg/1200px-Redis_Logo.svg.png){width=80%}

---

## Qual é a forma mais rápida e barata de processar algo❓ 🤔

---

## É não processar❗️

---

### Cache

![Cache](./images/cache.png)

---

### Escala horizontal

![escala](./images/escala.png)

---

### Como fica o cache?

Principalmente em sistema de fazem login pro session

---

### Ainda não conseguimos compartilhar memória entre servidores

---

### Cache Distribuído

![escala](./images/cache-distribuido.png){width=60%}

---

### E o tal do Redis?

![Redis](https://cdn.iconscout.com/icon/free/png-512/redis-83994.png){width=30%}

REmote DIctionary Server

---

### Redis

- Banco de dados Open Sourse
- In-memory
- Single Thread
- NoSQL
- Chave valor

---

### Chave valor

---

### Estruturas de dados

Temos algumas formas de organizar nossas iformações

---

### String

![string](./images/string.png)

---

### Nome das chaves

`objeto:identificador:campo`

---

### Nome das chaves

![string](./images/string-key.png)

---

### Invalidar Cache

---

#### Verificação de cache de atualização

![string](./images/rotina-validacao.png)

---

#### Aplicação Invalidando o Cache

![string](./images/rotina-invalida.png)

---

#### Expiração por tempo

![ttl](./images/ttl.png){width=40%}

---

#### TTL - Tempo de Vida

![ttl](./images/ttl.png){width=50%}

---

![ttl](./images/sem-ttl.png)

---

![ttl](./images/com-ttl.png)

---

### Parâmetros do expire

```
NX -- Set expiry only when the key has no expiry
XX -- Set expiry only when the key has an existing expiry
GT -- Set expiry only when the new expiry is greater than current one
LT -- Set expiry only when the new expiry is less than current one
```

---

### Lista

![list](./images/lista.png){width=100%}

---

### Sets

![set](./images/sets.png){width=100%}

---

### Sorted Sets

![set](./images/SortedSets.png){width=100%}

---

### Hash

![hash](./images/hash-values.png){width=100%}
