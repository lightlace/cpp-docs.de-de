---
title: Compilerwarnung (Stufe 4) C4343
ms.date: 11/04/2016
f1_keywords:
- C4343
helpviewer_keywords:
- C4343
ms.assetid: a721b710-e04f-4d15-b678-e4a2c8fd0181
ms.openlocfilehash: c8f0bb514a3da932500f986e50a20af0947827c5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403986"
---
# <a name="compiler-warning-level-4-c4343"></a>Compilerwarnung (Stufe 4) C4343

\#Pragma-optimize("g",Off)"überschreibt Option für" / Og "

Diese Warnung, die nur im Compiler der Itanium-Prozessorfamilie (IPF) gültig ist, meldet, dass ein „pragma [optimize](../../preprocessor/optimize.md) “ eine [/Og](../../build/reference/og-global-optimizations.md) -Compileroption außer Kraft gesetzt hat.

Im folgenden Beispiel wird C4343 generiert.

```
// C4343.cpp
// compile with: /Og /W4 /LD
// processor: IPF
#pragma optimize ("g", off)   // C4343
```