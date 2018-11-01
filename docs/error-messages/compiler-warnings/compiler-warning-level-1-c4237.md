---
title: Compilerwarnung (Stufe 1) C4237
ms.date: 11/04/2016
f1_keywords:
- C4237
helpviewer_keywords:
- C4237
ms.assetid: f2e86c4b-80d8-460e-9429-83c5f3f5d7ca
ms.openlocfilehash: 04fcb99e1dd1e348716e25affb22b54079d53aa9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50472682"
---
# <a name="compiler-warning-level-1-c4237"></a>Compilerwarnung (Stufe 1) C4237

' Schlüsselwort ' wird noch nicht unterstützt, aber für zukünftige Verwendung reserviert

Ein Schlüsselwort in der C++-Spezifikation ist nicht in Visual C++-Compiler implementiert, aber das Schlüsselwort ist nicht als ein benutzerdefiniertes Symbol zur Verfügung.

Im folgende Beispiel wird die C4237 generiert:

```
// C4237.cpp
// compile with: /W1 /c
int export;   // C4237
```