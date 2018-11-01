---
title: Compilerfehler C2665
ms.date: 11/04/2016
f1_keywords:
- C2665
helpviewer_keywords:
- C2665
ms.assetid: a7f99b61-2eae-4f2b-ba75-ea68fd1e8312
ms.openlocfilehash: 63817c4181edb942f43f41c24fb10278d14f397e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50474727"
---
# <a name="compiler-error-c2665"></a>Compilerfehler C2665

'Funktion': kann keine der Überladungen "number1" Parameter "number2" vom Typ 'Typ' konvertieren

Ein Parameter der überladenen Funktion kann nicht in den erforderlichen Typ konvertiert werden.  Mögliche Lösungen:

- Geben Sie einen Konvertierungsoperator.

- Verwenden Sie die explizite Konvertierung.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C2665 generiert.

```
// C2665.cpp
void func(short, char*){}
void func(char*, char*){}

int main() {
   func(0, 1);   // C2665
   func((short)0, (char*)1);   // OK
}
```