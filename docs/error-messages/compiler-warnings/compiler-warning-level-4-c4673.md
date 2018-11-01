---
title: Compilerwarnung (Stufe 4) C4673
ms.date: 11/04/2016
f1_keywords:
- C4673
helpviewer_keywords:
- C4673
ms.assetid: 95626ec6-f05b-43c7-8b9a-a60a6f98dd30
ms.openlocfilehash: ceaa5cd647dfb527713613b9ce3b5cd81a780fd7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50657729"
---
# <a name="compiler-warning-level-4-c4673"></a>Compilerwarnung (Stufe 4) C4673

Auslösen von "Bezeichner" die folgenden Typen werden nicht an die Catch-Standort betrachtet werden

Ein Throw-Objekt kann nicht verarbeitet werden, der **catch** Block. Jeder Typ, der nicht behandelt werden kann, wird in der Fehlerausgabe, die unmittelbar nach der Zeile, die mit dieser Warnung aufgeführt. Jede nicht behandelte Typ verfügt über eine eigene Warnung. Lesen Sie die Warnung für den jeweiligen Informationen.

Im folgende Beispiel wird die C4673 generiert:

```
// C4673.cpp
// compile with: /EHsc /W4
class Base {
private:
   char * m_chr;
public:
   Base() {
      m_chr = 0;
   }

   ~Base() {
      if(m_chr)
         delete m_chr;
   }
};

class Derv : private Base {
public:
   Derv() {}
   ~Derv() {}
};

int main() {
   try {
      Derv D1;
      // delete previous line, uncomment the next line to resolve
      // Base D1;
      throw D1;   // C4673
   }

   catch(...) {}
}
```