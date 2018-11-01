---
title: Compilerfehler C3813
ms.date: 11/04/2016
f1_keywords:
- C3813
helpviewer_keywords:
- C3813
ms.assetid: ffdbc489-71bf-4cd6-988c-f824c9ab3ceb
ms.openlocfilehash: 302b21d709424cda50abd0247f7b82048511cd73
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50470589"
---
# <a name="compiler-error-c3813"></a>Compilerfehler C3813

eine Eigenschaftendeklaration kann nur in der Definition eines verwalteten oder WinRT-Typs auftreten.

Ein [Eigenschaft](../../dotnet/how-to-use-properties-in-cpp-cli.md) kann nur deklariert werden, innerhalb eines verwalteten oder Windows-Runtime-Typ. Systemeigene Typen unterstützen das `property`-Schlüsselwort nicht.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3813 generiert und gezeigt, wie Sie diesen Fehler beheben:

```cpp
// C3813.cpp
// compile by using: cl /c /clr C3813.cpp
class A
{
   property int Int; // C3813
};

ref class B
{
   property int Int; // OK - declared within managed type
};
```