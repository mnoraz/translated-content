---
title: Node.isSameNode()
slug: Web/API/Node/isSameNode
translation_of: Web/API/Node/isSameNode
---

{{APIRef("DOM")}} {{Deprecated_Header}}
**`Node.isSameNode()`** comprueba si dos nodos son iguales, es decir si hacen referencia al mismo objecto.

> **Nota:** **Warning:** This method is no longer implemented in recent browsers.
>
> ```js
> // Instead of using
> node1.isSameNode(node2)
>
> // use
> node1 === node2 // or
> node1 == node2
> ```

## Sintaxis

```
var isSameNode = node.isSameNode(other);
```

- `other` El nodo contra el cual se realiza la comparación.

## Especificaciones

{{Specifications}}

## Compatibilidad entre navegadores

{{Compat("api.Node.isSameNode")}}

## Ver además

- {{domxref("Node.isEqualNode()")}}
