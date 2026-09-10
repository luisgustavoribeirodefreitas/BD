## Cardinalidade


Indica quantos objetos (instância) de uma entidade podem se relacionar com outras entidades através do relacionamento.

Devem ser considerados mínimos e máximos.

---

**Mínimo:** número **mínimo de instâncias** de uma entidade que devem se relacionar com uma instância de outra entidade. **É representado pelo primeiro valor** dentro dos parênteses da cardinalidade.

É utilizado para indicar o **tipo de participação** da entidade em um relacionamento:

* **0 → participação parcial ou opcional**
* **1 → participação total ou obrigatória**

---

**Máximo:** número **máximo de instâncias** de uma entidade que podem se relacionar com uma instância de outra entidade. **É representado pelo segundo valor** dentro dos parênteses da cardinalidade.

* **1 → no máximo uma instância**
* **N → várias instâncias**

---

**Exemplos:**
```
- (1,N)
- (1,1)
- (0,1)
- (0,N)
- (N,N)

Esses valores não são fixos e podem mudar de acordo com as regras de negócio.
```

**Parcial ou Opcional:** quando uma ocorrência de entidade **pode ou não participar** de determinado relacionamento. **Mínimo = 0.**

**Total ou Obrigatório:** quando uma ocorrência de entidade **deve obrigatoriamente participar** de determinado relacionamento. **Mínimo = 1.**

---

### Relacionamento N:N

Quando uma relação possui **(1,N) dos dois lados**, temos um relacionamento **muitos-para-muitos (N:N)**.

Nesse caso, é necessário criar uma **tabela associativa** para fazer a ligação entre as duas entidades.

**Exemplo:** `Pedidos`, `ItensPedido` e `Produtos`.

* `Pedidos` → `ItensPedido` = **(1,N)**
* `Produtos` → `ItensPedido` = **(1,N)**

A tabela `ItensPedido` funciona como uma **ponte** entre `Pedidos` e `Produtos`.

Mesmo existindo um `id` próprio em `ItensPedido`, para analisar o relacionamento **N:N**, devemos observar principalmente os **IDs das duas entidades que a tabela associativa conecta**: `idPedido` e `idProduto`.


* **Pedido (1,N) → (1,N) ItemPedido (1,N) ← (1,N) Produto**