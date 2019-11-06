---
title: Compilerwarnung (Stufe 1) C4237
ms.date: 11/04/2016
f1_keywords:
- C4237
helpviewer_keywords:
- C4237
ms.assetid: f2e86c4b-80d8-460e-9429-83c5f3f5d7ca
ms.openlocfilehash: e53c4632f8bfc9764f6ab1e124582bda273d945e
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2019
ms.locfileid: "73624902"
---
# <a name="compiler-warning-level-1-c4237"></a>Compilerwarnung (Stufe 1) C4237

Das Schlüsselwort "Keyword" wird noch nicht unterstützt, ist aber für die zukünftige Verwendung reserviert.

Ein Schlüsselwort in C++ der Spezifikation ist im Microsoft C++ -Compiler nicht implementiert, aber das Schlüsselwort ist nicht als benutzerdefiniertes Symbol verfügbar.

Im folgenden Beispiel wird C4237 generiert:

```cpp
// C4237.cpp
// compile with: /W1 /c
int export;   // C4237
```