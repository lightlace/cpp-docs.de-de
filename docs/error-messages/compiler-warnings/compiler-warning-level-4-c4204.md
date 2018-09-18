---
title: Compilerwarnung (Stufe 4) C4204 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4204
dev_langs:
- C++
helpviewer_keywords:
- C4204
ms.assetid: 298d2880-6737-448e-b711-15572d540200
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 61194e28081c42a71847eca3f97e4d1f46771d16
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46037540"
---
# <a name="compiler-warning-level-4-c4204"></a>Compilerwarnung (Stufe 4) C4204

nicht dem Standard entsprechende Erweiterung: nicht konstanter aggregierter Initialisierer

Mit Microsoft-Erweiterungen (/ Ze) können Sie aggregierte Datentypen (Arrays, Strukturen, Unions und Klassen) mit den Werten initialisieren, die sich nicht um Konstanten handelt.

## <a name="example"></a>Beispiel

```
// C4204.c
// compile with: /W4
int func1()
{
   return 0;
}
struct S1
{
   int i;
};

int main()
{
   struct S1 s1 = { func1() };   // C4204
   return s1.i;
}
```

Diese Initialisierungen sind ungültig, ANSI-Kompatibilität ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).