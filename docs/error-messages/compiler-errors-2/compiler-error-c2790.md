---
title: Compilerfehler C2790
ms.date: 11/04/2016
f1_keywords:
- C2790
helpviewer_keywords:
- C2790
ms.assetid: 38d4fce1-ba00-413d-8bc1-e8aa43d7bc1f
ms.openlocfilehash: c63fe7bb3686692818337e890de7fe4c80a18158
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74739557"
---
# <a name="compiler-error-c2790"></a>Compilerfehler C2790

"Super": dieses Schlüsselwort kann nur innerhalb des Texts der Klassenmember-Funktion verwendet werden.

Diese Fehlermeldung wird angezeigt, wenn der Benutzer versucht, das Schlüsselwort [Super](../../cpp/super.md) außerhalb des Kontexts einer Member-Funktion zu verwenden.

Im folgenden Beispiel wird C2790 generiert:

```cpp
// C2790.cpp
void f() {
   __super::g();   // C2790
}
```
