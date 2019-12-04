---
title: Compilerfehler C2274
ms.date: 11/04/2016
f1_keywords:
- C2274
helpviewer_keywords:
- C2274
ms.assetid: 8e874903-f499-45ef-8291-f821eee4cc1c
ms.openlocfilehash: fd807dedb6c300860611d07212b8fc8952a90a65
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758670"
---
# <a name="compiler-error-c2274"></a>Compilerfehler C2274

"Typ": unzulässig als Rechte Seite des Operators "."

Ein Typ wird als rechter Operand eines Members-Access-Operators (.) angezeigt.

Dieser Fehler kann verursacht werden, wenn versucht wird, auf eine benutzerdefinierte Typkonvertierung zuzugreifen. Verwenden Sie das Schlüsselwort `operator` zwischen dem Zeitraum und `type`.

Im folgenden Beispiel wird C2286 generiert:

```cpp
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
