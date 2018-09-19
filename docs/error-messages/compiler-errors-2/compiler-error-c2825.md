---
title: Compilerfehler C2825 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2825
dev_langs:
- C++
helpviewer_keywords:
- C2825
ms.assetid: c832f1c1-5184-4fc2-9356-12b21daa7af3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1bd0e9f8f2f5444b8835abc9f6802919f0e6c941
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46117581"
---
# <a name="compiler-error-c2825"></a>Compilerfehler C2825

Var: muss eine Klasse oder Namespace verwenden, wenn gefolgt von "::"

Nicht erfolgreiche es wurde versucht, um einen qualifizierten Namen zu bilden.

Beispielsweise stellen Sie sicher, dass Ihr Code keine Deklaration einer Funktion enthält, deren Namen der Funktion, die mit beginnt::.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C2825 generiert:

```
// C2825.cpp
typedef int i;
int main() {
   int* p = new int;
   p->i::i();   // C2825
   // try the following line instead
   // p->i::~i();
}
```