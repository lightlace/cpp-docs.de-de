---
title: Compilerfehler C2640
ms.date: 11/04/2016
f1_keywords:
- C2640
helpviewer_keywords:
- C2640
ms.assetid: e4d137ab-ed1d-457c-9eec-b70d97f1b0b4
ms.openlocfilehash: d0dc2dd514186a94811b816c5f3f470a057186f9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62182599"
---
# <a name="compiler-error-c2640"></a>Compilerfehler C2640

"Bezeichner": __based-Modifizierer auf Verweis unzulässig

Die `__based` Modifizierer kann nur für Zeiger verwendet werden.

Im folgende Beispiel wird die C2640 generiert:

```
// C2640.cpp
void f(int i) {
    void *vp;
    int _based(vp) &vr = I;  // C2640
}
```