---
title: Compilerfehler C2976 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2976
dev_langs:
- C++
helpviewer_keywords:
- C2976
ms.assetid: d9bf9836-325e-4f72-a7e3-a67cf19d32e7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a82cbe896d44190c5d7e6ee098f0f5a7a27e9378
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46072913"
---
# <a name="compiler-error-c2976"></a>Compilerfehler C2976

'Bezeichner': nicht genügend Typargumente

Eine generische oder Vorlagendeklaration fehlt mindestens eine tatsächliche Argumente. Überprüfen Sie die generische oder Vorlagendeklaration, um die richtige Anzahl von Parametern zu ermitteln.

Dieser Fehler kann durch fehlende Vorlagenargumente in C++-Standardbibliothek Komponenten verursacht werden.

Im folgende Beispiel wird die C2976 generiert:

```
// C2976.cpp
template <class T>
struct TC {
   T t;
};
int main() {
   TC<>* t;   // C2976
   TC<int>* t2;   // OK
}
```

C2976 kann auch auftreten, wenn Generika verwendet werden:

```
// C2976b.cpp
// compile with: /clr
generic <class T>
ref struct GC {
   T t;
};

int main() {
   GC<>^ g;   // C2976
   GC<int>^ g2;   // OK
}
```