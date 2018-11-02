---
title: Compilerfehler C2687
ms.date: 11/04/2016
f1_keywords:
- C2687
helpviewer_keywords:
- C2687
ms.assetid: 1d24b24a-cd0f-41cc-975c-b08dcfb7f402
ms.openlocfilehash: a30efa264a4e7be387c3c2363940bd5ceca1bcc4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50540945"
---
# <a name="compiler-error-c2687"></a>Compilerfehler C2687

"Type": Exception-Deklaration kann nicht "void" sein oder einen unvollständigen Typ oder Zeiger oder Verweis auf einen unvollständigen Typ zu kennzeichnen

Für einen Typ einer Ausnahmedeklaration angehören muss er definiert und nicht "void" sein.

Im folgende Beispiel wird die C2687 generiert:

```
// C2687.cpp
class C;

int main() {
   try {}
   catch (C) {}   // C2687 error
}
```

Mögliche Lösung:

```
// C2687b.cpp
// compile with: /EHsc
class C {};

int main() {
   try {}
   catch (C) {}
}
```