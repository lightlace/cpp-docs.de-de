---
title: Compilerwarnung (Stufe 1) C4674
ms.date: 11/04/2016
f1_keywords:
- C4674
helpviewer_keywords:
- C4674
ms.assetid: 638dae0b-b82c-4865-9599-72630827ca09
ms.openlocfilehash: b9428a593ff59cbdfa6d8eb369413a560b4a5ad2
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052542"
---
# <a name="compiler-warning-level-1-c4674"></a>Compilerwarnung (Stufe 1) C4674

"Methode" sollte als "static" deklariert werden und nur einen Parameter haben

Die Signatur eines Konvertierungsoperators war falsch. Die Methode wird nicht als benutzerdefinierte Konvertierung angesehen. Weitere Informationen zum Definieren von Operatoren finden Sie unter [benutzerdefinierte Operatoren (C++/CLI)](../../dotnet/user-defined-operators-cpp-cli.md) und [benutzerdefinierte Konvertierungen (C++/CLI)](../../dotnet/user-defined-conversions-cpp-cli.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4674 generiert.

```cpp
// C4674.cpp
// compile with: /clr /WX /W1 /LD
ref class G {
   int op_Implicit(int i) {   // C4674
      return 0;
   }
};
```
