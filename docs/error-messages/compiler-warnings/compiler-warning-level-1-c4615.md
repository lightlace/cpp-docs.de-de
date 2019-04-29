---
title: Compilerwarnung (Stufe 1) C4615
ms.date: 11/04/2016
f1_keywords:
- C4615
helpviewer_keywords:
- C4615
ms.assetid: 7b107c01-0da2-4e01-8b40-93813e30b94c
ms.openlocfilehash: 1032261c39e0a285ac686e09573161de3b46e0e5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62324544"
---
# <a name="compiler-warning-level-1-c4615"></a>Compilerwarnung (Stufe 1) C4615

\#Pragma-Warnung: Unbekannter Typ der benutzerwarnung

Wurde ein ungültiger Spezifizierer für die Warnung verwendet **Pragma** [Warnung](../../preprocessor/warning.md). Um den Fehler zu beheben, verwenden Sie einen gültigen Bezeichner ein.

Im folgende Beispiel wird die C4615 generiert:

```
// C4615.cpp
// compile with: /W1 /LD
#pragma warning(enable : 4401)   // C4615, 'enable' not valid specifier

// use the code below to resolve the error
// #pragma warning(default : 4401)
```