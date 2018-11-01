---
title: Compilerfehler C2951
ms.date: 11/04/2016
f1_keywords:
- C2951
helpviewer_keywords:
- C2951
ms.assetid: c6f95aa2-c894-425b-a51c-d40d70c8daa1
ms.openlocfilehash: dbc7186edfce6cc12a38fb2fc1dda08ac4a181c7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50638697"
---
# <a name="compiler-error-c2951"></a>Compilerfehler C2951

Deklarationen von Typen dürfen nur im globalen, Namespace- oder Klassengültigkeitsbereich

Sie können eine generische oder Vorlagenklasse, die außerhalb des globalen oder im Namespacebereich nicht deklarieren. Wenn Sie die generische oder Vorlagenklasse Deklarationen in einer Include-Datei vornehmen, stellen Sie sicher, dass die Include-Datei im globalen Gültigkeitsbereich.

Im folgende Beispiel wird die C2951 generiert:

```
// C2951.cpp
template <class T>
class A {};

int main() {
   template <class T>   // C2951
   class B {};
}
```

C2951 kann auch auftreten, wenn Generika verwendet werden:

```
// C2951b.cpp
// compile with: /clr /c

// OK
generic <class T>
ref class GC { };

int main() {
   generic <class T> ref class GC2 {};   // C2951
}
```