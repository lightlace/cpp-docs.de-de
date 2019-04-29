---
title: Compilerfehler C2825
ms.date: 11/04/2016
f1_keywords:
- C2825
helpviewer_keywords:
- C2825
ms.assetid: c832f1c1-5184-4fc2-9356-12b21daa7af3
ms.openlocfilehash: 1e2f8e8cd38b90a698994743609892896ef0d1a5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406898"
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