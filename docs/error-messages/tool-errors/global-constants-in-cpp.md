---
title: Globale Konstanten in C++
ms.date: 11/04/2016
helpviewer_keywords:
- global constants
- constants, global
ms.assetid: df5a9bd4-d0a8-4c1c-956e-b481d0bded7d
ms.openlocfilehash: 2f0621f52fe445f8f2058ef902824ddc1f5e2bb5
ms.sourcegitcommit: 283cb64fd7958a6b7fbf0cd8534de99ac8d408eb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64856109"
---
# <a name="global-constants-in-c"></a>Globale Konstanten in C++

Globale Konstanten in C++ haben statische Verknüpfung. Dies unterscheidet sich vom C. Wenn Sie versuchen, eine globale erhalten Konstante in C++ in mehreren Dateien Sie nicht aufgelösten externe Fehler. Der Compiler globale Konstanten werden optimiert, sodass kein Platz reserviert für die Variable.

Eine Möglichkeit zum Beheben dieses Fehlers ist die const Initialisierungen in einer Headerdatei einschließen, und schließen Sie diesen Header in CPP-Dateien bei Bedarf, als ob es Funktionsprototyp war. Eine andere Möglichkeit ist die Variable nicht Konstante und verwenden einen konstanten Verweis, wenn Sie darauf zugreifen.

Im folgende Beispiel wird die C2019 generiert:

```cpp
// global_constants.cpp
// LNK2019 expected
void test(void);
const int lnktest1 = 0;

int main() {
   test();
}
```

und anschließend

```cpp
// global_constants_2.cpp
// compile with: global_constants.cpp
extern int lnktest1;

void test() {
  int i = lnktest1;   // LNK2019
}
```

## <a name="see-also"></a>Siehe auch

[Linkertoolfehler LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)