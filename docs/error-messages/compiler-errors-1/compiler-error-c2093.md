---
title: Compilerfehler C2093
ms.date: 11/04/2016
f1_keywords:
- C2093
helpviewer_keywords:
- C2093
ms.assetid: 17529a70-9169-46b5-9fc6-57a5ce224e6a
ms.openlocfilehash: d57b452e63f7bf76051ef6a23c5f8f6ba81aed1e
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70741155"
---
# <a name="compiler-error-c2093"></a>Compilerfehler C2093

"variable1": kann nicht mit der Adresse der automatischen Variablen "variable2" initialisiert werden.

Beim Kompilieren mit [/Za](../../build/reference/za-ze-disable-language-extensions.md)hat das Programm versucht, die Adresse einer automatischen Variablen als Initialisierer zu verwenden.

Im folgenden Beispiel wird C2093 generiert:

```
// C2093.c
// compile with: /Za /c
void func() {
   int li;   // an implicit auto variable
   int * s[]= { &li };   // C2093 address is not a constant

   // OK
   static int li2;
   int * s2[]= { &li2 };
}
```