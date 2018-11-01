---
title: Compilerwarnung (Stufe 1) C4183
ms.date: 11/04/2016
f1_keywords:
- C4183
helpviewer_keywords:
- C4183
ms.assetid: dc48312c-4b34-44dd-80ff-eb5f11d5ca47
ms.openlocfilehash: 0d947a0f6d777a5ed3191d6d232a604028be2003
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50477453"
---
# <a name="compiler-warning-level-1-c4183"></a>Compilerwarnung (Stufe 1) C4183

"Bezeichner": Rückgabetyp fehlt; davon ausgegangen, dass eine Memberfunktion, die "Int" zurückgibt

Die Inlinedefinition einer Memberfunktion in einer Klasse oder Struktur muss einen Rückgabetyp nicht. Diese Memberfunktion wird als ein Standardwert, der Rückgabetyp ist `int`.

Im folgende Beispiel wird die C4183 generiert:

```
// C4183.cpp
// compile with: /W1 /c
#pragma warning(disable : 4430)
class MyClass1;
class MyClass2 {
   MyClass1() {};   // C4183
};
```