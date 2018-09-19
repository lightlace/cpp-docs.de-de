---
title: Compilerwarnung (Stufe 1) C4674 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4674
dev_langs:
- C++
helpviewer_keywords:
- C4674
ms.assetid: 638dae0b-b82c-4865-9599-72630827ca09
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9b2f945982e80b49403387241f29a50876274e66
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46024878"
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
