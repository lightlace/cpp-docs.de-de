---
title: Compilerwarnung (Stufe 3) C4522 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4522
dev_langs:
- C++
helpviewer_keywords:
- C4522
ms.assetid: 7065dc27-0b6c-4e68-a345-c51cdb99a20b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 65662d3e62abbeb06127c7b5a49479a23fb20a7a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46070937"
---
# <a name="compiler-warning-level-3-c4522"></a>Compilerwarnung (Stufe 3) C4522

'Klasse': Mehrere Zuweisungsoperatoren angegeben

Die Klasse verfügt über mehrere Zuweisungsoperatoren eines einzelnen Typs. Diese Warnung dient nur zu Informationszwecken; die Konstruktoren, die in Ihrem Programm können aufgerufen werden.

Verwenden der [Warnung](../../preprocessor/warning.md) Pragma, um diese Warnung unterdrücken.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4522 generiert.

```
// C4522.cpp
// compile with: /EHsc /W3
#include <iostream>

using namespace std;
class A {
public:
   A& operator=( A & o ) { cout << "A&" << endl; return *this; }
   A& operator=( const A &co ) { cout << "const A&" << endl; return *this; }   // C4522
};

int main() {
   A o1, o2;
   o2 = o1;
   const A o3;
   o1 = o3;
}
```