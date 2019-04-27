---
title: Compilerfehler C3198
ms.date: 11/04/2016
f1_keywords:
- C3198
helpviewer_keywords:
- C3198
ms.assetid: ec4ecf61-0067-4aa4-b443-a91013a1e59d
ms.openlocfilehash: 61a3d14f9ad47edaa1e9b9f2b25d38b8dae7165c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62243220"
---
# <a name="compiler-error-c3198"></a>Compilerfehler C3198

Ungültige Verwendung von Gleitkommapragmas: Fenv_access-Pragma wird nur im precise-Modus ausgeführt.

[Fenv_access](../../preprocessor/fenv-access.md) Pragma wurde verwendet, unter einer [/fp](../../build/reference/fp-specify-floating-point-behavior.md) andere Einstellung als **/fp: präzise**.

Im folgende Beispiel wird die C3198 generiert:

```
// C3198.cpp
// compile with: /fp:fast
#pragma fenv_access(on)   // C3198
```