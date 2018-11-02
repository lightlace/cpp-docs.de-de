---
title: Compilerfehler C2979
ms.date: 11/04/2016
f1_keywords:
- C2979
helpviewer_keywords:
- C2979
ms.assetid: 98bd9043-ec44-451e-a482-3a8e35fc7464
ms.openlocfilehash: 5d9b8e025d96e448ec9494834eb1766cafd8b677
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50531031"
---
# <a name="compiler-error-c2979"></a>Compilerfehler C2979

Explizite Spezialisierungen werden für Generika nicht unterstützt.

Eine generische Klasse wurde falsch deklariert.  Finden Sie unter [Generika](../../windows/generics-cpp-component-extensions.md) für Weitere Informationen.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2979 generiert.

```
// C2979.cpp
// compile with: /clr /c
generic <>
ref class Utils {};   // C2979 error

generic <class T>
ref class Utils2 {};   // OK
```