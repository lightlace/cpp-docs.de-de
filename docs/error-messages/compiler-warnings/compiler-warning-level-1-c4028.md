---
title: Compilerwarnung (Stufe 1) C4028
ms.date: 11/04/2016
f1_keywords:
- C4028
helpviewer_keywords:
- C4028
ms.assetid: c3e8b70b-e870-416c-a285-bba5f71dbfc6
ms.openlocfilehash: 19bfd2659ee9017d3a304dee2d647da091515876
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2019
ms.locfileid: "73623850"
---
# <a name="compiler-warning-level-1-c4028"></a>Compilerwarnung (Stufe 1) C4028

formaler Parameter ' Number ' unterscheidet sich von der Deklaration

Der Typ des formalen Parameters stimmt nicht mit dem entsprechenden Parameter in der Deklaration überein. Der Typ in der ursprünglichen Deklaration wird verwendet.

Diese Warnung gilt nur für C-Quellcode.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4028 generiert.

```c
// C4028.c
// compile with: /W1 /Za
void f(int , ...);
void f(int i, int j) {}   // C4028

void g(int , int);
void g(int i, int j) {}   // OK

int main() {}
```