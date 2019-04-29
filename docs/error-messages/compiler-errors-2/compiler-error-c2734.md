---
title: Compilerfehler C2734
ms.date: 11/04/2016
f1_keywords:
- C2734
helpviewer_keywords:
- C2734
ms.assetid: e53a77b7-825c-42d1-a655-90e1c93b833e
ms.openlocfilehash: c20fcc7673c00ea7cfad32bdc3feae042f1f9086
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62350766"
---
# <a name="compiler-error-c2734"></a>Compilerfehler C2734

'Bezeichner': Konstantes Objekt muss initialisiert werden, wenn es nicht Extern

Der Bezeichner wurde deklariert `const` , aber nicht initialisiert oder `extern`.

Im folgende Beispiel wird die C2734 generiert:

```
// C2734.cpp
const int j;   // C2734
extern const int i;   // OK, declared as extern
```