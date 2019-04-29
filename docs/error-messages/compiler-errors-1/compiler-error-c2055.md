---
title: Compilerfehler C2055
ms.date: 11/04/2016
f1_keywords:
- C2055
helpviewer_keywords:
- C2055
ms.assetid: 6cec79cc-6bec-443f-9897-fbf5452718c7
ms.openlocfilehash: 3c198168b4445e619148e5611621fa3ddba95d6b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408786"
---
# <a name="compiler-error-c2055"></a>Compilerfehler C2055

Liste der formalen Parameter erwartet, keiner Liste

Eine Funktionsdefinition enthält eine Liste der Parameter anstelle einer formellen Parameterliste. ANSI C erfordert, dass formale Parameter benannt werden, sofern sie Sie nicht "void" oder ein Auslassungszeichen (`...`).

Im folgende Beispiel wird die C2055 generiert:

```
// C2055.c
// compile with: /c
void func(int, char) {}  // C2055
void func (int i, char c) {}   // OK
```