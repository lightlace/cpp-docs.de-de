---
title: Globale Konstanten in C++ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
dev_langs:
- C++
helpviewer_keywords:
- global constants
- constants, global
ms.assetid: df5a9bd4-d0a8-4c1c-956e-b481d0bded7d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 00d033c1c4fc8fc3e534c8e4ee0c3d7867b83834
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46103166"
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