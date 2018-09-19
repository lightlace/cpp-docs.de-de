---
title: Compilerfehler C2274 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2274
dev_langs:
- C++
helpviewer_keywords:
- C2274
ms.assetid: 8e874903-f499-45ef-8291-f821eee4cc1c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0fcc6b0afe78e089c268f69274be1cbfb6f3d32c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46093199"
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