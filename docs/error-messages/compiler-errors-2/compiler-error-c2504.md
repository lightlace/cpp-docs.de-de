---
title: Compilerfehler C2504
ms.date: 11/04/2016
f1_keywords:
- C2504
helpviewer_keywords:
- C2504
ms.assetid: c9e002a6-a4ee-4ba7-970e-edf4adb83692
ms.openlocfilehash: d47d99962d089d873cb9bbdf9baac7eab706fc16
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74746889"
---
# <a name="compiler-error-c2504"></a>Compilerfehler C2504

"Class": Basisklasse nicht definiert

Die Basisklasse ist deklariert, wird aber nie definiert.  Mögliche Ursachen:

1. Fehlende Includedatei.

1. Externe Basisklasse nicht mit [extern](../../cpp/using-extern-to-specify-linkage.md)deklariert.

Im folgenden Beispiel wird C2504 generiert:

```cpp
// C2504.cpp
// compile with: /c
class A;
class B : public A {};   // C2504
```

Okay

```
class C{};
class D : public C {};
```
