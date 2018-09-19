---
title: Compilerwarnung (Ebenen 2 und 4) C4200 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4200
dev_langs:
- C++
helpviewer_keywords:
- C4200
ms.assetid: e44d6073-937f-42b7-acc1-65e802b475c6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 34e0befb93db742bb2d132b2092414a1a167b87b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46100720"
---
# <a name="compiler-warning-levels-2-and-4-c4200"></a>Compilerwarnung (Stufen 2 und 4) C4200

nicht dem Standard entsprechende Erweiterung: Null-Array in Struktur/Union

Gibt an, dass eine Struktur oder Union ein Array mit Größe Null enthält.

Die Deklaration eines Arrays der Größe 0 (null) ist eine Microsoft-Erweiterung. Dadurch wird eine Warnung der Stufe 2 bei der Kompilierung einer C++-Datei und eine Warnung der Stufe 4 kompiliert, wenn C-Datei kompiliert wird. C++ Kompilierung gibt auch diese Warnung: "Kann nicht generiert Copy-Ctor oder Copy-Assignment-Operator, wenn UDT ein Array der Größe 0 (null) enthält." In diesem Beispiel wird die Warnung C4200 generiert:

```cpp
// C4200.cpp
// compile by using: cl /W4 c4200.cpp
struct A {
    int a[0];  // C4200
};
int main() {
}
```

Diese nicht standardisierte Erweiterung wird häufig zum Verknüpfen von Code mit externen Datenstrukturen verwendet, die eine variable Länge haben. Wenn dieses Szenario für Ihren Code gilt, können Sie die Warnung deaktivieren:

## <a name="example"></a>Beispiel

```cpp
// C4200b.cpp
// compile by using: cl /W4 c4200a.cpp
#pragma warning(disable : 4200)
struct A {
    int a[0];
};
int main() {
}
```