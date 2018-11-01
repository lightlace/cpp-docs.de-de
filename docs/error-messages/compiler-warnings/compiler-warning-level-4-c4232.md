---
title: Compilerwarnung (Stufe 4) C4232
ms.date: 11/04/2016
f1_keywords:
- C4232
helpviewer_keywords:
- C4232
ms.assetid: f92028a5-4ddd-43c1-97f5-4f724e5e14af
ms.openlocfilehash: dee087b73bf032a68daf0527ea584efcc7579361
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50552632"
---
# <a name="compiler-warning-level-4-c4232"></a>Compilerwarnung (Stufe 4) C4232

nicht dem Standard entsprechende Erweiterung: "Bezeichner": Adresse von Dllimport 'Dllimport' ist nicht statisch, Identität nicht garantiert.

Sie können Microsoft-Erweiterungen (/ Ze), einen nicht statischen Wert geben, wie Sie mit der Adresse einer Funktion deklariert die **Dllimport** Modifizierer. ANSI-Kompatibilität ([/Za](../../build/reference/za-ze-disable-language-extensions.md)), dies verursacht einen Fehler.

Im folgende Beispiel wird die C4232 generiert:

```
// C4232.c
// compile with: /W4 /Ze /c
int __declspec(dllimport) f();
int (*pfunc)() = &f;   // C4232
```