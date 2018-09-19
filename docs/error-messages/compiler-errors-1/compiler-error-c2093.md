---
title: Compilerfehler C2093 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2093
dev_langs:
- C++
helpviewer_keywords:
- C2093
ms.assetid: 17529a70-9169-46b5-9fc6-57a5ce224e6a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 952391b1fbe0820175566cecd74156b9a55ef4b8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46055844"
---
# <a name="compiler-error-c2093"></a>Compilerfehler C2093

'variable1': kann nicht mit der Adresse der automatischen Variablen 'variable2' initialisiert werden

Beim Kompilieren mit [/Za](../../build/reference/za-ze-disable-language-extensions.md), das Programm versucht, die Adresse einer automatischen Variablen als Initialisierer zu verwenden.

Im folgende Beispiel wird die C2093 generiert:

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