---
title: Compilerwarnung (Stufe 4) C4343
ms.date: 11/04/2016
f1_keywords:
- C4343
helpviewer_keywords:
- C4343
ms.assetid: a721b710-e04f-4d15-b678-e4a2c8fd0181
ms.openlocfilehash: 59803440966b8396ba231dc5a7265620c37f9cc1
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991200"
---
# <a name="compiler-warning-level-4-c4343"></a>Compilerwarnung (Stufe 4) C4343

\#Pragma-Optimierung ("g", Off) überschreibt/og-Option

Diese Warnung, die nur im Compiler der Itanium-Prozessorfamilie (IPF) gültig ist, meldet, dass ein „pragma [optimize](../../preprocessor/optimize.md) “ eine [/Og](../../build/reference/og-global-optimizations.md) -Compileroption außer Kraft gesetzt hat.

Im folgenden Beispiel wird C4343 generiert.

```cpp
// C4343.cpp
// compile with: /Og /W4 /LD
// processor: IPF
#pragma optimize ("g", off)   // C4343
```
