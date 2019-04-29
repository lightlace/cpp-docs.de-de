---
title: Compilerfehler C3075
ms.date: 11/04/2016
f1_keywords:
- C3075
helpviewer_keywords:
- C3075
ms.assetid: f431daa9-e0fa-48f0-a5c3-f99be96b55e3
ms.openlocfilehash: 0494961b47e99ce1f3e559302aff56278098a912
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406716"
---
# <a name="compiler-error-c3075"></a>Compilerfehler C3075

'Instanz': Eine Instanz eines Verweistyps 'Typ' kann nicht in einen Werttyp eingebettet werden.

Ein Werttyp kann keine Instanz eines Verweistyps enthalten.

Weitere Informationen finden Sie unter [C++-Stapelsemantik für Referenztypen](../../dotnet/cpp-stack-semantics-for-reference-types.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3075 generiert:

```
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