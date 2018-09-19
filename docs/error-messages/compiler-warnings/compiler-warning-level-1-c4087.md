---
title: Compilerwarnung (Stufe 1) C4087 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4087
dev_langs:
- C++
helpviewer_keywords:
- C4087
ms.assetid: 546e4d57-5c8e-422c-8ef1-92657336dad5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4be252163d9c45d2404629bcf9e2d82e3225a84a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46086290"
---
# <a name="compiler-warning-level-1-c4087"></a>Compilerwarnung (Stufe 1) C4087

"Funktion": Mit "void"-Parameterliste deklariert

Die Funktionsdeklaration hat keine formalen Parameter, aber der Funktionsaufruf hat tatsächlich Parameter. Zusätzliche Parameter werden entsprechend der Aufrufkonvention der Funktion übergeben.

Diese Warnung gilt für den C-Compiler.

## <a name="example"></a>Beispiel

```
// C4087.c
// compile with: /W1
int f1( void ) {
}

int main() {
   f1( 10 );   // C4087
}
```