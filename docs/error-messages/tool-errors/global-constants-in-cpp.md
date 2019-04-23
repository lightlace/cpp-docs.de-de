---
title: Globale Konstanten in C++
ms.date: 11/04/2016
helpviewer_keywords:
- global constants
- constants, global
ms.assetid: df5a9bd4-d0a8-4c1c-956e-b481d0bded7d
ms.openlocfilehash: 1ae29b8744e24b6471f0d5536f3f13cc5ae59499
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59030192"
---
# <a name="global-constants-in-c"></a>Globale Konstanten in C++

Globale Konstanten in C++ haben statische Verknüpfung. Dies unterscheidet sich vom C. Wenn Sie versuchen, eine globale erhalten Konstante in C++ in mehreren Dateien Sie nicht aufgelösten externe Fehler. Der Compiler globale Konstanten werden optimiert, sodass kein Platz reserviert für die Variable.

Eine Möglichkeit zum Beheben dieses Fehlers ist die const Initialisierungen in einer Headerdatei einschließen, und schließen Sie diesen Header in CPP-Dateien bei Bedarf, als ob es Funktionsprototyp war. Eine andere Möglichkeit ist die Variable nicht Konstante und verwenden einen konstanten Verweis, wenn Sie darauf zugreifen.

Im folgende Beispiel wird die C2019 generiert:

```
// global_constants.cpp
// LNK2019 expected
void test(void);
const int lnktest1 = 0;

int main() {
   test();
}
```

und anschließend

```
// global_constants_2.cpp
// compile with: global_constants.cpp
extern int lnktest1;

void test() {
  int i = lnktest1;   // LNK2019
}
```

## <a name="see-also"></a>Siehe auch

[Linkertoolfehler LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)