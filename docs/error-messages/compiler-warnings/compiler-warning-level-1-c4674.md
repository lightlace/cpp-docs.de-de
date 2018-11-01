---
title: Compilerwarnung (Stufe 1) C4674
ms.date: 11/04/2016
f1_keywords:
- C4674
helpviewer_keywords:
- C4674
ms.assetid: 638dae0b-b82c-4865-9599-72630827ca09
ms.openlocfilehash: f7db2f37224a8defffb545b0cfaf018fd4654227
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50614824"
---
# <a name="compiler-warning-level-1-c4674"></a>Compilerwarnung (Stufe 1) C4674

"Methode" sollte als "static" deklariert werden und nur einen Parameter haben

Die Signatur eines Konvertierungsoperators war falsch. Die Methode wird nicht als benutzerdefinierte Konvertierung angesehen. Weitere Informationen zum Definieren von Operatoren finden Sie unter [User-Defined Operators (C++ / CLI)](../../dotnet/user-defined-operators-cpp-cli.md) und [User-Defined Conversions (C++ / CLI)](../../dotnet/user-defined-conversions-cpp-cli.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4674 generiert.

```
// C4674.cpp
// compile with: /clr /WX /W1 /LD
ref class G {
   int op_Implicit(int i) {   // C4674
      return 0;
   }
};
```
