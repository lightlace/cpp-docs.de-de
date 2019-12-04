---
title: Compilerfehler C2562
ms.date: 11/04/2016
f1_keywords:
- C2562
helpviewer_keywords:
- C2562
ms.assetid: 2c41e511-9952-4b98-9976-6b1523613e1b
ms.openlocfilehash: 78536fdc0c2a6a6e9c4842fdea6423037496b30b
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755550"
---
# <a name="compiler-error-c2562"></a>Compilerfehler C2562

"Identifier": "void"-Funktion gibt einen Wert zurück

Die-Funktion wird als `void` deklariert, gibt jedoch einen-Wert zurück.

Dieser Fehler kann durch einen fehlerhaften Funktionsprototyp verursacht werden.

Dieser Fehler kann korrigiert werden, wenn Sie den Rückgabetyp in der Funktionsdeklaration angeben.

Im folgenden Beispiel wird C2562 generiert:

```cpp
// C2562.cpp
// compile with: /c
void testfunc() {
   int i;
   return i;   // C2562 delete the return to resolve
}
```
