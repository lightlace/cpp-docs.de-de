---
title: Compilerfehler C2790 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2790
dev_langs:
- C++
helpviewer_keywords:
- C2790
ms.assetid: 38d4fce1-ba00-413d-8bc1-e8aa43d7bc1f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dc2c6b238fab7e42c0754e613b62756a86a5bb31
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46069572"
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