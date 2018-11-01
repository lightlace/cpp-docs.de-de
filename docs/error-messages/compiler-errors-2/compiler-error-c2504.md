---
title: Compilerfehler C2504
ms.date: 11/04/2016
f1_keywords:
- C2504
helpviewer_keywords:
- C2504
ms.assetid: c9e002a6-a4ee-4ba7-970e-edf4adb83692
ms.openlocfilehash: 8f428699aa14cbd1f021a57ed8dcabefa8b24c16
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50444390"
---
# <a name="compiler-error-c2504"></a>Compilerfehler C2504

'Klasse': Basisklasse undefiniert

Die Basisklasse der Klasse deklariert, aber nicht definiert.  Mögliche Ursachen:

1. Include-Datei fehlt.

1. Externe Basisklasse ist nicht mit deklariert ["extern"](../../cpp/using-extern-to-specify-linkage.md).

Im folgende Beispiel wird die C2504 generiert:

```
// C2504.cpp
// compile with: /c
class A;
class B : public A {};   // C2504
```

OKAY

```
class C{};
class D : public C {};
```