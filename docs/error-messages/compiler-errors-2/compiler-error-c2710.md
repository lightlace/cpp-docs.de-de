---
title: Compilerfehler C2710
ms.date: 11/04/2016
f1_keywords:
- C2710
helpviewer_keywords:
- C2710
ms.assetid: a2a6bb5b-86ad-4a6c-acd0-e2bef8464e0e
ms.openlocfilehash: 54d501d43652bb8e54092d44042a9525ef6f708f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160912"
---
# <a name="compiler-error-c2710"></a>Compilerfehler C2710

'construct': '__declspec(Modifizierer)' kann nur auf eine Funktion, die Rückgabe eines Zeigers angewendet werden

Eine Funktion, deren Rückgabewert ein Zeiger ist, ist das einzige Konstrukt, `modifier` angewendet werden können.

Im folgende Beispiel wird die C2710 generiert:

```
// C2710.cpp
__declspec(restrict) void f();   // C2710
// try the following line instead
__declspec(restrict) int * g();
```