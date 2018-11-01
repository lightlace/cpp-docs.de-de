---
title: Compilerfehler C3461
ms.date: 11/04/2016
f1_keywords:
- C3461
helpviewer_keywords:
- C3461
ms.assetid: bd66833a-545d-445a-bdfe-dee771a450a4
ms.openlocfilehash: 81372c7a2468becf6dba3b30b62ee266eed272ab
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50562915"
---
# <a name="compiler-error-c3461"></a>Compilerfehler C3461

'Typ': Nur ein verwalteter Typ kann weitergeleitet werden.

Die Typweiterleitung ist nur bei CLR-Typen möglich.  Finden Sie unter [Klassen und Strukturen](../../windows/classes-and-structs-cpp-component-extensions.md) für Weitere Informationen.

Weitere Informationen finden Sie unter [Typweiterleitung (C++ / CLI)](../../windows/type-forwarding-cpp-cli.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird eine Komponente erstellt:

```
// C3461.cpp
// compile with: /clr /LD
public ref class R {};
```

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3461 generiert:

```
// C3461b.cpp
// compile with: /clr /c
#using "C3461.dll"
class N {};
[assembly:TypeForwardedTo(N::typeid)];   // C3461
[assembly:TypeForwardedTo(R::typeid)];   // OK
```