---
title: Compilerwarnung (Stufe 1) C4716
ms.date: 11/04/2016
f1_keywords:
- C4716
helpviewer_keywords:
- C4716
ms.assetid: d95ecfe5-870f-461f-a746-7913af98414b
ms.openlocfilehash: 5215e8fd0bdd44c9bdfc731d2b74499d38853e80
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052459"
---
# <a name="compiler-warning-level-1-c4716"></a>Compilerwarnung (Stufe 1) C4716

"Funktion" muss einen Wert zurückgeben

Die angegebene Funktion hat keinen Wert zurückgegeben.

Nur Funktionen mit dem Rückgabetyp "void" können den Return-Befehl ohne einen zugehörigen Rückgabewert verwenden.

Wenn diese Funktion aufgerufen wird, wird ein nicht definierter Wert zurückgegeben.

Diese Warnung wird automatisch zu einem Fehler heraufgestuft. Wenn Sie dieses Verhalten ändern möchten, verwenden Sie [#pragma Warnung](../../preprocessor/warning.md).

Im folgenden Beispiel wird C4716 generiert:

```cpp
// C4716.cpp
// compile with: /c /W1
// C4716 expected
#pragma warning(default:4716)
int test() {
   // uncomment the following line to resolve
   // return 0;
}
```