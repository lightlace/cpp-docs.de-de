---
title: Compilerfehler C2687 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2687
dev_langs:
- C++
helpviewer_keywords:
- C2687
ms.assetid: 1d24b24a-cd0f-41cc-975c-b08dcfb7f402
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1333d26a7733ffeb0876a9b563377e5ead010261
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46042675"
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