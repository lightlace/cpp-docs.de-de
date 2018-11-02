---
title: Compilerfehler C2249
ms.date: 11/04/2016
f1_keywords:
- C2249
helpviewer_keywords:
- C2249
ms.assetid: bdd6697c-e04b-49b9-8e40-d9eb6d74f2b6
ms.openlocfilehash: f3f82549cf5d9230adfee7e83248e92f8e93e769
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50555628"
---
# <a name="compiler-error-c2249"></a>Compilerfehler C2249

'Member': kein Zugriff auf den Pfad Zugriff auf Element deklariert wird, in der virtuellen Basisklasse "Klasse"

Die `member` wird von einem Nonpublic geerbt `virtual` Klasse oder Struktur.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C2249 generiert.

```
// C2249.cpp
class A {
private:
   void privFunc( void ) {};
public:
   void pubFunc( void ) {};
};

class B : virtual public A {} b;

int main() {
   b.privFunc();    // C2249, private member of A
   b.pubFunc();    // OK
}
```

## <a name="example"></a>Beispiel

C2249 kann auch auftreten, wenn Sie versuchen, einen Stream aus der C++-Standardbibliothek in einen anderen Stream zuzuweisen.  Im folgende Beispiel wird die C2249 generiert.

```
// C2249_2.cpp
#include <iostream>
using namespace std;
int main() {
   cout = cerr;   // C2249
   #define cout cerr;   // OK
}
```