---
title: Compilerfehler C3264
ms.date: 11/04/2016
f1_keywords:
- C3264
helpviewer_keywords:
- C3264
ms.assetid: 94ece687-2364-4f7a-8ebb-7afd3ae9d63d
ms.openlocfilehash: 2f5a58335a36affc73deb490c9423284852ecbab
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50537523"
---
# <a name="compiler-error-c3264"></a>Compilerfehler C3264

'Klasse': Ein Klassenkonstruktor kann keinen Rückgabetyp haben

Klassenkonstruktoren können keine Rückgabetypen aufweisen.

Im folgenden Beispiel wird C3264 generiert:

```
// C3264_2.cpp
// compile with: /clr

ref class X {
   public:
      static int X()   { // C3264
      }

      /* use the code below to resolve the error
      static X() {
      }
      */
};
int main() {
}
```
