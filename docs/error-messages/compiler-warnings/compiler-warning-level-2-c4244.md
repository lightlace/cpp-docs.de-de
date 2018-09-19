---
title: Compilerwarnung (Stufe 2) C4244 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4244
dev_langs:
- C++
helpviewer_keywords:
- C4244
ms.assetid: 2c19d157-21d1-42c2-a6c0-3f30f2ce3813
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2c6dd4b15fe3bda6468f8d5bebcf7cb0926ba69e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46084795"
---
# <a name="compiler-warning-level-2-c4244"></a>Compilerwarnung (Stufe 2) C4244

'Argument': Konvertierung von 'type1' in 'type2', möglicher Datenverlust

Ein Gleitkommatyp in einen ganzzahligen Typ konvertiert wurde.  Möglicherweise ist ein Datenverlust aufgetreten.

Wenn C4244 angezeigt wird, sollten Sie das Programm für das Verwenden von kompatiblen Typen ändern Logik zu Ihrem Code hinzufügen, um sicherzustellen, dass der Bereich möglicher Werte immer mit den verwendeten Typen kompatibel sind.

C4244 kann auch auf Ebene 3 und 4 ausgelöst werden. finden Sie unter [Compilerwarnung (Ebenen 3 und 4) C4244](../../error-messages/compiler-warnings/compiler-warning-levels-3-and-4-c4244.md) für Weitere Informationen.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4244 generiert:

```
// C4244_level2.cpp
// compile with: /W2

int f(int x){ return 0; }
int main() {
   double x = 10.1;
   int i = 10;
   return (f(x));   // C4244
   // try the following line instead
   // return (f(i));
}
```