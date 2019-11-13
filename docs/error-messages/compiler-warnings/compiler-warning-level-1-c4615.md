---
title: Compilerwarnung (Stufe 1) C4615
ms.date: 11/04/2016
f1_keywords:
- C4615
helpviewer_keywords:
- C4615
ms.assetid: 7b107c01-0da2-4e01-8b40-93813e30b94c
ms.openlocfilehash: 8c682b309cbabbaf97346e37038806d331f949ac
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052605"
---
# <a name="compiler-warning-level-1-c4615"></a>Compilerwarnung (Stufe 1) C4615

\#pragma-Warnung: Unbekannter Benutzer Warnungstyp.

Ein ungültiger Warnungs Spezifizierer wurde mit der **pragma** - [Warnung](../../preprocessor/warning.md)verwendet. Um den Fehler zu beheben, verwenden Sie einen gültigen Warnungs Spezifizierer.

Im folgenden Beispiel wird C4615 generiert:

```cpp
// C4615.cpp
// compile with: /W1 /LD
#pragma warning(enable : 4401)   // C4615, 'enable' not valid specifier

// use the code below to resolve the error
// #pragma warning(default : 4401)
```