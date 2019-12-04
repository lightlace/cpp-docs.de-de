---
title: Compilerfehler C3075
ms.date: 11/04/2016
f1_keywords:
- C3075
helpviewer_keywords:
- C3075
ms.assetid: f431daa9-e0fa-48f0-a5c3-f99be96b55e3
ms.openlocfilehash: 345cdd17b9da0be8f8d6e9f7b5f48624ade412bd
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761581"
---
# <a name="compiler-error-c3075"></a>Compilerfehler C3075

'Instanz': Eine Instanz eines Verweistyps 'Typ' kann nicht in einen Werttyp eingebettet werden.

Ein Werttyp kann keine Instanz eines Verweistyps enthalten.

Weitere Informationen finden [ C++ Sie unter Stapel Semantik für Verweis Typen](../../dotnet/cpp-stack-semantics-for-reference-types.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3075 generiert:

```cpp
// C3075.cpp
// compile with: /clr /c
ref struct U {};
value struct X {
   U y;   // C3075
};

ref struct Y {
   U y;   // OK
};
```
