---
layout: post
title:  "Meu teste com Jekyll"
date:   2022-12-30 14:00:31 -0300
categories: teste
tags: desafio conceito
---

# zanfranceschi

## teste de página

lorem ipsum

```clojure

(defn my-function [a b]
    (str "–> " a b))    
```

```python
def my_function(a, b):
    pass
```

```csharp
string teste = "teste";
```

{% mermaid %}
sequenceDiagram
    participant A as Alice
    participant B as Bob
    
    A->>B: Hello John, how are you?
    Note right of A: Teste, 1, 2, 3...
    B-->>A: Great!
    Note over A, B: Teste, 1, 2, 3..
    loop para cada item
        A->>B: POST /items
        B-->>A: HTTP Created/201
        opt se houver erro
            A->>B: retry posting item
        end
    end
{% endmermaid %}