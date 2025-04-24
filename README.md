#  Mapeamento Associativa em Python

Este projeto simula o comportamento de uma **memória cache associativa** com três políticas de substituição: **LRU**, **FIFO** e **LFU**. A simulação permite observar o comportamento de **cache hit** e **cache miss**, além das substituições automáticas conforme a política definida.

---

## 🚀 Funcionalidades

- Simulação de uma RAM com dados aleatórios.
- Implementação de três políticas de substituição:
  - 🔁 **LRU (Least Recently Used)**
  - 📥 **FIFO (First-In First-Out)**
  - 📊 **LFU (Least Frequently Used)**
- Atualização de valores em RAM e Cache.
- Relatórios visuais no terminal.
- Identificação clara de:
  - 🟩 **Cache Hit**
  - 🟥 **Cache Miss**
  - 🧹 **Substituição de endereço**

---

## 🧰 Estrutura do Código

### Classe `CacheAssociativa`

| Método | Descrição |
|--------|-----------|
| `__init__` | Inicializa a RAM e configura a cache com política escolhida |
| `printRam()` | Exibe o conteúdo da RAM |
| `printCache()` | Exibe o conteúdo atual da Cache |
| `buscarEndereço(endereco, valor=None)` | Busca um endereço na cache, tratando hits e misses com possível sobrescrita |
| `aplicarPolitica(endereco)` | Atualiza os dados de controle da política em uso |
| `atualizarValor(endereco)` | Realiza a substituição de um valor na cache conforme a política ativa |

---

## 💡 Como Usar

```python
cache = CacheAssociativa(tamanhoCache=3, tamanhoRam=10, politica='LFU')

cache.printRam()          # Visualizar RAM inicial
cache.printCache()        # Visualizar Cache inicial

cache.buscarEndereço(1)   # Buscar endereço 1
cache.buscarEndereço(2)
cache.buscarEndereço(3)
cache.buscarEndereço(1)   # Aumenta frequência do 1
cache.buscarEndereço(4)   # Substituição acontece
cache.buscarEndereço(2)
