---
title: Compilerwarnung (Stufe 3) C4534 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- c4534
dev_langs:
- C++
helpviewer_keywords:
- C4534
ms.assetid: ec2adf3b-d7a1-4005-bb0c-5d219df78dc8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ad85a6b9dff1715cbdce9738608f26c8680319d0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46099810"
---
# <a name="compiler-warning-level-3-c4534"></a>Compilerwarnung (Stufe 3) C4534

'Konstruktor' werden nicht auf einen Standardkonstruktor für Klasse 'Klasse' aufgrund von das Standardargument

Eine nicht verwaltete Klasse kann einen Konstruktor mit Parametern, die Standardwerte festgelegt wurden und der Compiler wird dies als den Standardkonstruktor verwenden. Eine Klasse mit markiert die `value` Schlüsselwort nicht verwendet einen Konstruktor mit standardmäßigen Werten für die Parameter als einen standardmäßigen Konstruktor.

Weitere Informationen finden Sie unter [Klassen und Strukturen](../../windows/classes-and-structs-cpp-component-extensions.md).

Im folgende Beispiel wird die C4534 generiert:

```
// C4534.cpp
// compile with: /W3 /clr /WX
value class MyClass {
public:
   int ii;
   MyClass(int i = 9) {   // C4534, will not be the default constructor
      i++;
   }
};

int main() {
   MyClass ^ xx = gcnew MyClass;
   xx->ii = 0;
}
```