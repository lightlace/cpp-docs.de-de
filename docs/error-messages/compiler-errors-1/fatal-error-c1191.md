---
title: Schwerwiegender Fehler C1191
ms.date: 11/04/2016
f1_keywords:
- C1191
helpviewer_keywords:
- C1191
ms.assetid: 2888c6c4-b4e6-449e-8ee0-7917f31086df
ms.openlocfilehash: 7c6756dec29138af534278742d99c2f77109b1cc
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74747292"
---
# <a name="fatal-error-c1191"></a>Schwerwiegender Fehler C1191

"dll" kann nur im globalen Gültigkeitsbereich importiert werden.

Die Anweisung zum Importieren von "mscorlib. dll" in ein Programm, das/CLR-Programmierung verwendet, darf nicht in einem Namespace oder einer Funktion verwendet werden, muss jedoch im globalen Gültigkeitsbereich erscheinen.

Im folgenden Beispiel wird C1191 generiert:

```cpp
// C1191.cpp
// compile with: /clr
namespace sample {
   #using <mscorlib.dll>   // C1191 not at global scope
}
```

Mögliche Lösung:

```cpp
// C1191b.cpp
// compile with: /clr /c
#using <mscorlib.dll>
namespace sample {}
```
