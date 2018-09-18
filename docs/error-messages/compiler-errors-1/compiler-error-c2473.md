---
title: Compilerfehler C2473 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2473
dev_langs:
- C++
helpviewer_keywords:
- C2473
ms.assetid: 6bb7dbf5-b198-490f-860e-fd64d0c2a284
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0eeecedd3ad2cee551b6003912d9b7af32883588
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46026074"
---
# <a name="compiler-error-c2473"></a>Compilerfehler C2473

"Bezeichner": Hat die Form einer Funktionsdefinition, aber es gibt keine Parameterliste.

Der Compiler hat einen Codeabschnitt entdeckt, der wie eine Funktion aussieht, aber keine Parameterliste aufweist.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2473 generiert.

```
// C2473.cpp
// compile with: /clr /c
class A {
   int i {}   // C2473
};

class B {
   int i() {}   // OK
};
```