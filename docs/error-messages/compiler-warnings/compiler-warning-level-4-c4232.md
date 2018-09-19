---
title: Compilerwarnung (Stufe 4) C4232 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4232
dev_langs:
- C++
helpviewer_keywords:
- C4232
ms.assetid: f92028a5-4ddd-43c1-97f5-4f724e5e14af
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 450c764cfc130acf28e3edfb40fcd17c8ac3b664
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118283"
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