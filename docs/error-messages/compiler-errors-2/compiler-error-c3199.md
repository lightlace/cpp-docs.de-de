---
title: Compilerfehler C3199
ms.date: 11/04/2016
f1_keywords:
- C3199
helpviewer_keywords:
- C3199
ms.assetid: e7a478d3-115a-40a3-991b-c7454fd2e28e
ms.openlocfilehash: 934e980149ad893e6799b0ab119a148fc5652fdc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402787"
---
# <a name="compiler-error-c3199"></a>Compilerfehler C3199

Ungültige Verwendung von Gleitkommapragmas: Ausnahmen werden in nicht dem precise-Modus nicht unterstützt

Die [Float_control](../../preprocessor/float-control.md) Pragma wurde verwendet, um das Modell für Gleitkommaausnahmen unter Geben Sie eine [/fp](../../build/reference/fp-specify-floating-point-behavior.md) andere Einstellung als **/fp: präzise**.

Im folgende Beispiel wird die C3199 generiert:

```
// C3199.cpp
// compile with: /fp:fast
#pragma float_control(except, on)   // C3199
```