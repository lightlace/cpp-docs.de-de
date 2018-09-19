---
title: Compilerwarnung (Stufe 3) C4390 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4390
dev_langs:
- C++
helpviewer_keywords:
- C4390
ms.assetid: c95c2f1b-9bce-4b1f-a80c-565d4cde0b1e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 83131119e360bcf8193c2d6c8ca5a3cd09341516
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46054186"
---
# <a name="compiler-warning-level-3-c4390"></a>Compilerwarnung (Stufe 3) C4390

";": leere kontrollierte Anweisung aufgetreten; ist dies beabsichtigt?

Ein Semikolon wurde nach einer Control-Anweisung gefunden, die keine Anweisungen enthält.

Wenn Sie wegen eines Makros C4390 erhalten, verwenden Sie die [Warnung](../../preprocessor/warning.md) Pragma, um das Modul mit dem Makro C4390 deaktivieren.

Im folgende Beispiel wird die C4390 generiert:

```
// C4390.cpp
// compile with: /W3
int main() {
   int i = 0;
   if (i);   // C4390
      i++;
}
```