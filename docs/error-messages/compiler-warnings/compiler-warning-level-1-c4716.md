---
title: Compilerwarnung (Stufe 1) C4716 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4716
dev_langs:
- C++
helpviewer_keywords:
- C4716
ms.assetid: d95ecfe5-870f-461f-a746-7913af98414b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4f7a6fd31ecae4643e947cb4a56897e80010e350
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46093401"
---
# <a name="compiler-warning-level-1-c4716"></a>Compilerwarnung (Stufe 1) C4716

"Funktion" muss einen Wert zurückgeben

Die angegebene Funktion keinen Wert zurückgibt.

Funktioniert nur mit einem Rückgabetyp "void" können verwenden Sie die return-Befehl ohne begleitwert zurück.

Ein nicht definierter Wert wird zurückgegeben, wenn diese Funktion aufgerufen wird.

Diese Warnung wird automatisch zu einem Fehler heraufgestuft. Wenn Sie dieses Verhalten ändern möchten, verwenden Sie [#pragma-Warnung](../../preprocessor/warning.md).

Im folgende Beispiel wird die C4716 generiert:

```
// C4716.cpp
// compile with: /c /W1
// C4716 expected
#pragma warning(default:4716)
int test() {
   // uncomment the following line to resolve
   // return 0;
}
```