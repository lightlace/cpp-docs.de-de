---
title: Compilerwarnung (Stufe 4) C4434
ms.date: 11/04/2016
f1_keywords:
- C4434
helpviewer_keywords:
- C4434
ms.assetid: 24b8785e-353a-4c37-8bed-ed61001a871d
ms.openlocfilehash: 97a010bef151e97914d131b3a1fe2437a244e9c4
ms.sourcegitcommit: d0504e2337bb671e78ec6dd1c7b05d89e7adf6a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2019
ms.locfileid: "74683217"
---
# <a name="compiler-warning-level-4-c4434"></a>Compilerwarnung (Stufe 4) C4434

Ein Klassenkonstruktor muss private Zugriffsmöglichkeiten aufweisen; wird in privaten Zugriff geändert

C4434 zeigt an, dass die Zugriffsmöglichkeiten eines statischen Konstruktors vom Compiler geändert wurden. Statische Konstruktoren müssen private Zugriffsmöglichkeiten aufweisen, da sie nur zum Aufrufen durch Common Language Runtime vorgesehen sind. Weitere Informationen finden Sie unter [statische Konstruktoren](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Static_constructors).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4434 generiert.

```cpp
// C4434.cpp
// compile with: /W4 /c /clr
public ref struct R {
   static R(){}   // C4434
};
```