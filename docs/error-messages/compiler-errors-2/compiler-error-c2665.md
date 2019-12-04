---
title: Compilerfehler C2665
ms.date: 11/04/2016
f1_keywords:
- C2665
helpviewer_keywords:
- C2665
ms.assetid: a7f99b61-2eae-4f2b-ba75-ea68fd1e8312
ms.openlocfilehash: 95ca5ea846f9cd45bdb1e9706ae377589d37a285
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756018"
---
# <a name="compiler-error-c2665"></a>Compilerfehler C2665

"Function": keine der Zahl1-über Ladungen kann Parameter Zahl2 von Typ "Typ" konvertieren.

Ein Parameter der überladenen Funktion kann nicht in den erforderlichen Typ konvertiert werden.  Mögliche Lösungen:

- Stellen Sie einen Konvertierungs Operator bereit.

- Verwenden Sie die explizite Konvertierung.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2665 generiert.

```cpp
// C2665.cpp
void func(short, char*){}
void func(char*, char*){}

int main() {
   func(0, 1);   // C2665
   func((short)0, (char*)1);   // OK
}
```
