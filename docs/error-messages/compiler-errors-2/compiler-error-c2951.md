---
title: Compilerfehler C2951
ms.date: 11/04/2016
f1_keywords:
- C2951
helpviewer_keywords:
- C2951
ms.assetid: c6f95aa2-c894-425b-a51c-d40d70c8daa1
ms.openlocfilehash: fdb837f8e9a9b769d470b70b962ce63d144161e1
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755979"
---
# <a name="compiler-error-c2951"></a>Compilerfehler C2951

Typdeklarationen sind nur im globalen, Namespace-oder Klassen Gültigkeitsbereich zulässig.

Sie können keine generische oder Vorlagen Klasse außerhalb des globalen oder Namespace Bereichs deklarieren. Wenn Sie die generische oder Vorlagen Deklarationen in einer Includedatei vornehmen, stellen Sie sicher, dass sich die Includedatei im globalen Gültigkeitsbereich befindet.

Im folgenden Beispiel wird C2951 generiert:

```cpp
// C2951.cpp
template <class T>
class A {};

int main() {
   template <class T>   // C2951
   class B {};
}
```

C2951 kann auch auftreten, wenn Generika verwendet werden:

```cpp
// C2951b.cpp
// compile with: /clr /c

// OK
generic <class T>
ref class GC { };

int main() {
   generic <class T> ref class GC2 {};   // C2951
}
```
