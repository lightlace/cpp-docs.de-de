---
title: Compilerfehler C3698 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3698
dev_langs:
- C++
helpviewer_keywords:
- C3698
ms.assetid: 3c02fb08-7ba4-4637-a06f-19926cb2b5f1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e9ca53e5b614b5e1d85832a7ad437a39ac1c5d87
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46107898"
---
# <a name="compiler-error-c3698"></a>Compilerfehler C3698

'Typ': Verwenden Sie diesen Typ kann nicht als Argument von 'Operator'

Ein verwaltetes Objekt wurde falsch deklariert.

Im folgende Beispiel wird die C3698 generiert:

```
// C3698.cpp
// compile with: /clr

int main() {
   array<int>^a = new array<int>^(20);   // C3698
   array<int>^a2 = gcnew array<int>(20);   // OK
}
```