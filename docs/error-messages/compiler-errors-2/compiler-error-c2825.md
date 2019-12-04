---
title: Compilerfehler C2825
ms.date: 11/04/2016
f1_keywords:
- C2825
helpviewer_keywords:
- C2825
ms.assetid: c832f1c1-5184-4fc2-9356-12b21daa7af3
ms.openlocfilehash: 6a51901477958056356a96d71adde4241d60a2ac
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74750584"
---
# <a name="compiler-error-c2825"></a>Compilerfehler C2825

var: muss eine Klasse oder ein Namespace sein, wenn gefolgt von "::"

Es wurde ein nicht erfolgreicher Versuch unternommen, einen qualifizierten Namen zu bilden.

Stellen Sie z. b. sicher, dass der Code keine Funktionsdeklaration enthält, bei der der Funktionsname mit:: beginnt.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2825 generiert:

```cpp
// C2825.cpp
typedef int i;
int main() {
   int* p = new int;
   p->i::i();   // C2825
   // try the following line instead
   // p->i::~i();
}
```
