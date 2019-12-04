---
title: Compilerfehler C3198
ms.date: 11/04/2016
f1_keywords:
- C3198
helpviewer_keywords:
- C3198
ms.assetid: ec4ecf61-0067-4aa4-b443-a91013a1e59d
ms.openlocfilehash: b9e0ce4a84b312e3a9277898b3fc264ea3ae22bb
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74739154"
---
# <a name="compiler-error-c3198"></a>Compilerfehler C3198

Ungültige Verwendung von Gleit Komma-Pragmas: fenv_access Pragma nur im präzisen Modus arbeitet.

[fenv_access](../../preprocessor/fenv-access.md) Pragma wurde unter einer [/FP](../../build/reference/fp-specify-floating-point-behavior.md) -Einstellung verwendet, die nicht **/fp: präzise**ist.

Im folgenden Beispiel wird C3198 generiert:

```cpp
// C3198.cpp
// compile with: /fp:fast
#pragma fenv_access(on)   // C3198
```
