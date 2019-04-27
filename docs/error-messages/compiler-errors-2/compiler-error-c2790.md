---
title: Compilerfehler C2790
ms.date: 11/04/2016
f1_keywords:
- C2790
helpviewer_keywords:
- C2790
ms.assetid: 38d4fce1-ba00-413d-8bc1-e8aa43d7bc1f
ms.openlocfilehash: e377c18b5c0774a466dc535f2a1fba3411bd15b8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62257126"
---
# <a name="compiler-error-c2790"></a>Compilerfehler C2790

"super": Dieses Schlüsselwort kann nur innerhalb des Texts der Klassenmemberfunktion verwendet werden

Diese Fehlermeldung wird angezeigt, wenn der Benutzer versucht, verwendet das Schlüsselwort [super](../../cpp/super.md) außerhalb des Kontexts einer Memberfunktion.

Im folgende Beispiel wird die C2790 generiert:

```
// C2790.cpp
void f() {
   __super::g();   // C2790
}
```