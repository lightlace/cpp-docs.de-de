---
title: Compilerfehler C2675 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2675
dev_langs:
- C++
helpviewer_keywords:
- C2675
ms.assetid: 4b92a12b-bff8-4dd5-a109-620065fc146c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1772f6e88516e7c8c1498f84d180ab6c4e0e05ab
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46102400"
---
# <a name="compiler-error-c2675"></a>Compilerfehler C2675

unärer 'Operator Operator': 'Typ' definiert nicht diesen Operator oder eine Konvertierung in einen geeigneten Typ für den vordefinierten Operator

C2675 kann auch auftreten, wenn einen unäroperator, und der Typ definiert nicht den Operator oder eine Konvertierung in einen geeigneten Typ für den vordefinierten Operator. Um den Operator zu verwenden, müssen Sie ihn für den angegebenen Typ überladen oder eine Konvertierung in einen Typ definieren, für den der Operator definiert ist.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C2675 generiert.

```
// C2675.cpp
struct C {
   C(){}
} c;

struct D {
   D(){}
   void operator-(){}
} d;

int main() {
   -c;   // C2675
   -d;   // OK
}
```