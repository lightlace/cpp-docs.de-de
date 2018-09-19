---
title: Compilerfehler C2640 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2640
dev_langs:
- C++
helpviewer_keywords:
- C2640
ms.assetid: e4d137ab-ed1d-457c-9eec-b70d97f1b0b4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ad39b2a9e3397f97ddc4a900bc45d1983ebbf574
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46085280"
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