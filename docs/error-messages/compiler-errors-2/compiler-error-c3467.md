---
title: Compilerfehler C3467
ms.date: 11/04/2016
f1_keywords:
- C3467
helpviewer_keywords:
- C3467
ms.assetid: e2b844d0-4920-412f-99fd-cd8051c4aa41
ms.openlocfilehash: 73e646c386d5c9b8b43d86ab743989b2525f76a4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50460930"
---
# <a name="compiler-error-c3467"></a>Compilerfehler C3467

'typ': Dieser Typ wurde bereits weitergeleitet.

Der Compiler hat mehr als eine Vorwärts-Typdeklaration für den gleichen Typ gefunden. Es ist nur eine Deklaration pro Typ zulässig.

Weitere Informationen finden Sie unter [Typweiterleitung (C++ / CLI)](../../windows/type-forwarding-cpp-cli.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird eine Komponente erstellt:

```
// C3467.cpp
// compile with: /LD /clr
public ref class R {};
```

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3467 generiert:

```
// C3467_b.cpp
// compile with: /clr /c
#using "C3467.dll"
[ assembly:TypeForwardedTo(R::typeid) ];
[ assembly:TypeForwardedTo(R::typeid) ];   // C3467
```