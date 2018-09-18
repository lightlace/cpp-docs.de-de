---
title: Compilerfehler C2273 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2273
dev_langs:
- C++
helpviewer_keywords:
- C2273
ms.assetid: 3c682c66-97bf-4a23-a22c-d9a26a92bf95
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 995f75487820976d045e5db05fe2b170260240cc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46066217"
---
# <a name="compiler-error-c2273"></a>Compilerfehler C2273

"Type": unzulässig auf der rechten Seite des Operators "->"

Ein Typ wird als der Rechte Operand des eine `->` Operator.

Dieser Fehler kann verursacht werden, indem Sie versuchen, eine benutzerdefinierte typkonvertierung zugreifen. Verwenden Sie das Schlüsselwort `operator` zwischen -> und `type`.

Im folgende Beispiel wird die C2273 generiert:

```
// C2273.cpp
struct MyClass {
   operator int() {
      return 0;
   }
};
int main() {
   MyClass * ClassPtr = new MyClass;
   int i = ClassPtr->int();   // C2273
   int j = ClassPtr-> operator int();   // OK
}
```