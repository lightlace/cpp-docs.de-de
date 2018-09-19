---
title: Compilerfehler C2261 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2261
dev_langs:
- C++
helpviewer_keywords:
- C2261
ms.assetid: 60969482-9e83-49b5-9631-a04bc844da12
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2ed43dc43fb6ceaf514a8e7452b06eb7bdaf7362
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46051645"
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