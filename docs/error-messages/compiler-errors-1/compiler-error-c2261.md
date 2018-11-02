---
title: Compilerfehler C2261
ms.date: 11/04/2016
f1_keywords:
- C2261
helpviewer_keywords:
- C2261
ms.assetid: 60969482-9e83-49b5-9631-a04bc844da12
ms.openlocfilehash: 2df788efd93fb531822d858ea5aee1722487db81
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50535745"
---
# <a name="compiler-error-c2261"></a>Compilerfehler C2261

"String": der Assemblyverweis ist ungültig und kann nicht aufgelöst werden

Ein Wert war ungültig.

<xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> Dient zum Angeben einer Friend-Assembly. Z. B. wenn a.dll b.dll als Friend-Assembly angeben möchte, würden Sie angeben (in a.dll): InternalsVisibleTo("b"). Die Laufzeit kann dann b.dll auf alle Elemente im a.dll (mit Ausnahme der private Typen).

Weitere Informationen über die richtige Syntax, wenn Sie Friend-Assemblys angeben, finden Sie [Friend-Assemblys (C++)](../../dotnet/friend-assemblies-cpp.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C2261 generiert.

```
// C2261.cpp
// compile with: /clr /c
using namespace System::Runtime::CompilerServices;
[assembly: InternalsVisibleTo("a,a,a")];   // C2261
[assembly: InternalsVisibleTo("a.a")];   // OK
[assembly: InternalsVisibleTo("a")];   // OK
```