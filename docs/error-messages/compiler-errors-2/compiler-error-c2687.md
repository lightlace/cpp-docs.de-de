---
title: Compilerfehler C2687
ms.date: 11/04/2016
f1_keywords:
- C2687
helpviewer_keywords:
- C2687
ms.assetid: 1d24b24a-cd0f-41cc-975c-b08dcfb7f402
ms.openlocfilehash: f3e728033a3230d628242aab341377be2f6670ca
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760256"
---
# <a name="compiler-error-c2687"></a>Compilerfehler C2687

"Type": Exception-Deklaration darf nicht "void" sein oder einen unvollständigen Typ, Zeiger oder Verweis auf einen unvollständigen Typ bezeichnen

Damit ein Typ Teil einer Ausnahme Deklaration ist, muss er definiert und nicht leer sein.

Im folgenden Beispiel wird C2687 generiert:

```cpp
// C2687.cpp
class C;

int main() {
   try {}
   catch (C) {}   // C2687 error
}
```

Mögliche Lösung:

```cpp
// C2687b.cpp
// compile with: /EHsc
class C {};

int main() {
   try {}
   catch (C) {}
}
```
