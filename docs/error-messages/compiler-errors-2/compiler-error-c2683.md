---
title: Compilerfehler C2683 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2683
dev_langs:
- C++
helpviewer_keywords:
- C2683
ms.assetid: db605e4f-601b-4d05-92a1-c43ca24de08d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c13836c845e1efc33c409939bdbec49b25c84e63
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46027590"
---
# <a name="compiler-error-c2683"></a>Compilerfehler C2683

'cast': 'Typ' ist kein polymorpher Typ

Sie können keine [Dynamic_cast](../../cpp/dynamic-cast-operator.md) aus einer nicht polymorph-Klasse (eine Klasse ohne virtuelle Funktionen) zu konvertieren.

Sie können ["static_cast"](../../cpp/static-cast-operator.md) zum Durchführen von Konvertierungen von nicht polymorphen Typen. Allerdings `static_cast` führt eine laufzeitüberprüfung nicht aus.

Im folgende Beispiel wird die C2683 generiert:

```
// C2683.cpp
// compile with: /c
class B { };
class D : public B { };

void f(B* pb) {
   D* pd1 = dynamic_cast<D*>(pb);  // C2683
   D* pd1 = static_cast<D*>(pb);   // OK
}
```