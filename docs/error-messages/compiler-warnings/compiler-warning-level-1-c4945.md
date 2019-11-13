---
title: Compilerwarnung (Stufe 1) C4945
ms.date: 11/04/2016
f1_keywords:
- C4945
helpviewer_keywords:
- C4945
ms.assetid: 6d2079ea-dc59-4611-bc68-9a22c06f7587
ms.openlocfilehash: 6a20effcebe1a36fa1356fffefa3a23a0056a0f0
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052261"
---
# <a name="compiler-warning-level-1-c4945"></a>Compilerwarnung (Stufe 1) C4945

' Symbol ': das Symbol kann nicht aus ' Assembly2 ' importiert werden: da ' Symbol ' bereits aus einer anderen Assembly ' Assembly1 ' importiert wurde.

Ein Symbol wurde aus einer referenzierten Assembly importiert, aber dieses Symbol wurde bereits aus einer anderen Assembly importiert, auf die verwiesen wird. Verweisen Sie entweder nicht auf eine der Assemblys, oder lassen Sie den Symbolnamen in einer der Assemblys geändert.

In den folgenden Beispielen wird C4945 generiert.

```csharp
// C4945a.cs
// compile with: /target:library
// C# source code to create a dll
public class ClassA {
   public int i;
}
```

Und dann

```csharp
// C4945b.cs
// compile with: /target:library
// C# source code to create a dll
public class ClassA {
   public int i;
}
```

Und dann

```cpp
// C4945c.cpp
// compile with: /clr /LD /W1
#using "C4945a.dll"
#using "C4945b.dll"   // C4945
```