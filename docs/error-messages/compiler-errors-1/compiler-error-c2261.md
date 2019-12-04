---
title: Compilerfehler C2261
ms.date: 11/04/2016
f1_keywords:
- C2261
helpviewer_keywords:
- C2261
ms.assetid: 60969482-9e83-49b5-9631-a04bc844da12
ms.openlocfilehash: f23c2a38f8e4d6781af73fb70a25cf4737e2c4e8
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758774"
---
# <a name="compiler-error-c2261"></a>Compilerfehler C2261

"String": der Assemblyverweis ist ungültig und kann nicht aufgelöst werden.

Ein Wert war ungültig.

<xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> wird zum Angeben einer Friend-Assembly verwendet. Wenn eine DLL-Datei z. b. b. dll als Friend-Assembly angeben möchte, würden Sie (in einer DLL-Datei): InternalsVisibleTo ("b") angeben. Die Laufzeit ermöglicht es b. dll, auf alles in einer DLL-Datei (außer private Typen) zuzugreifen.

Weitere Informationen zur korrekten Syntax beim Angeben von Friend-Assemblys finden Sie unter Friend-Assemblys [(C++)](../../dotnet/friend-assemblies-cpp.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2261 generiert.

```cpp
// C2261.cpp
// compile with: /clr /c
using namespace System::Runtime::CompilerServices;
[assembly: InternalsVisibleTo("a,a,a")];   // C2261
[assembly: InternalsVisibleTo("a.a")];   // OK
[assembly: InternalsVisibleTo("a")];   // OK
```
