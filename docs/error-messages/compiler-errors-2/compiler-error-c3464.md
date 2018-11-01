---
title: Compilerfehler C3464
ms.date: 11/04/2016
f1_keywords:
- C3464
helpviewer_keywords:
- C3464
ms.assetid: 0ede05dc-4486-4921-8e8c-78ab5a2e09c5
ms.openlocfilehash: d1645571ce3102687d5054e066ec1dc7d633b3aa
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50503125"
---
# <a name="compiler-error-c3464"></a>Compilerfehler C3464

"Typ" Ein geschachtelter Typ kann nicht weitergeleitet werden.

Weiterleiten von Typen funktioniert nicht bei geschachtelten Typen.

Weitere Informationen finden Sie unter [Typweiterleitung (C++ / CLI)](../../windows/type-forwarding-cpp-cli.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird eine Komponente erstellt:

```
// C3464.cpp
// compile with: /LD /clr
public ref class R {
public:
   ref class N {};
};
```

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3464 generiert:

```
// C3464_b.cpp
// compile with: /clr /c
#using "C3464.dll"
[assembly:TypeForwardedTo(R::N::typeid)];   // C3464
[assembly:TypeForwardedTo(R::typeid)];   // OK
```