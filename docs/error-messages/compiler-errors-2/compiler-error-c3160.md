---
title: Compilerfehler C3160 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3160
dev_langs:
- C++
helpviewer_keywords:
- C3160
ms.assetid: a250c433-8adf-43b9-8dee-c3794e09b0a5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bf3ecc18e1afc9b13e47ad8b20bb92f7686d0cfc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46042272"
---
# <a name="compiler-error-c3160"></a>Compilerfehler C3160

„Zeiger“: Ein Datenmember einer verwalteten oder WinRT-Klasse kann nicht diesen Typ aufweisen.

Innere Garbage Collection-Zeiger können auf das Innere einer verwalteten oder WinRT-Klasse verweisen. Da diese langsamer als Zeiger auf gesamte Objekte sind und eine besondere Behandlung durch den Garbage Collector erfordern, können innere verwaltete Zeiger nicht als Member einer Klasse deklariert werden.

Im folgenden Beispiel wird C3160 generiert:

```
// C3160.cpp
// compile with: /clr
ref struct A {
   // cannot create interior pointers inside a class
   interior_ptr<int> pg;   // C3160
   int g;   // OK
   int* pg2;   // OK
};

int main() {
   interior_ptr<int> pg2;   // OK
}
```
