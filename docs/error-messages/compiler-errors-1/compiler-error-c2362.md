---
title: Compilerfehler C2362 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2362
dev_langs:
- C++
helpviewer_keywords:
- C2362
ms.assetid: 7aafecbc-b3cf-45a6-9ec3-a17e3f222511
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f78b850f95614255fed372570742a0f88a9e30e2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46035980"
---
# <a name="compiler-error-c2362"></a>Compilerfehler C2362

Initialisierung von "Bezeichner" durch "Goto Label" übersprungen

Beim Kompilieren mit [/Za](../../build/reference/za-ze-disable-language-extensions.md), Springen zur Bezeichnung verhindert, dass den Bezeichner initialisiert wird.

Sie können nicht hinter einer Deklaration mit einem Initialisierer springen, es sei denn, die Deklaration in einem Block eingeschlossen ist, die nicht eingegeben wird, oder die Variable wurde bereits initialisiert.

Im folgenden Beispiel wird C2326 generiert:

```
// C2362.cpp
// compile with: /Za
int main() {
   goto label1;
   int i = 1;      // C2362, initialization skipped
label1:;
}
```

Mögliche Lösung:

```
// C2362b.cpp
// compile with: /Za
int main() {
   goto label1;
   {
      int j = 1;   // OK, this block is never entered
   }
label1:;
}
```