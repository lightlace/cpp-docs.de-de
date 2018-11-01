---
title: Compilerfehler C2274
ms.date: 11/04/2016
f1_keywords:
- C2274
helpviewer_keywords:
- C2274
ms.assetid: 8e874903-f499-45ef-8291-f821eee4cc1c
ms.openlocfilehash: f2fcb75098f18ad113ba68959035b37d9cddd6e9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50667024"
---
# <a name="compiler-error-c2274"></a>Compilerfehler C2274

"Type": unzulässig auf der rechten Seite des '.' Operator

Ein Typ wird als der Rechte Operand des einen Memberzugriffsoperator (.) angezeigt.

Dieser Fehler kann verursacht werden, indem Sie versuchen, eine benutzerdefinierte typkonvertierung zugreifen. Verwenden Sie das Schlüsselwort `operator` zwischen dem Zeitraum und `type`.

Im folgenden Beispiel wird C2286 generiert:

```
// C2274.cpp
struct MyClass {
   operator int() {
      return 0;
   }
};

int main() {
   MyClass ClassName;
   int i = ClassName.int();   // C2274
   int j = ClassName.operator int();   // OK
}
```