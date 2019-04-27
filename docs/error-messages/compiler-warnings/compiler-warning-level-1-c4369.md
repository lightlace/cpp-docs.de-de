---
title: Compilerwarnung (Stufe 1) C4369
ms.date: 11/04/2016
f1_keywords:
- C4369
helpviewer_keywords:
- C4369
ms.assetid: ade87e84-36be-4e00-be99-2930af848feb
ms.openlocfilehash: b374b67fa3319be35490358d7664bcb45bc640db
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62207029"
---
# <a name="compiler-warning-level-1-c4369"></a>Compilerwarnung (Stufe 1) C4369

'Enumerator': ' Enumeratorwert ' kann nicht als 'Type' dargestellt werden, der Wert ist 'New_value'

Ein Enumerator wurde größer sein als der größte Wert für den angegebenen zugrunde liegenden Typ berechnet.  Dies hat einen Überlauf verursacht, und der Compiler eingeschlossen, den Enumeratorwert, der den niedrigsten Wert für den Typ.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4369 generiert.

```
// C4369.cpp
// compile with: /W1
int main() {
   enum Color: char { red = 0x7e, green, blue };   // C4369
   enum Color2: char { red2 = 0x7d, green2, blue2};   // OK
}
```