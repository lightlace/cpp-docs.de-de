---
title: Compilerwarnung (Stufe 3) C4290 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4290
dev_langs:
- C++
helpviewer_keywords:
- C4290
ms.assetid: d1c6d85b-28e0-4a1f-9d48-23593337a6fb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3a6f09d8f3396381f34a0fbe3c7150b5948cee01
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46015968"
---
# <a name="compiler-warning-level-3-c4290"></a>Compilerwarnung (Stufe 3) C4290

C++-Ausnahmespezifikation ignoriert, es sei denn, so dass eine Funktion ist nicht __declspec(nothrow).

Eine Funktion wird deklariert, mit der Ausnahmespezifikation, die Visual C++ akzeptiert, aber nicht implementiert. Code mit der Ausnahme, die Spezifikationen, die während der Kompilierung ignoriert werden neu kompiliert werden können und verknüpft sein wiederverwendet in zukünftigen Versionen, die Ausnahmespezifikationen unterstützen.

Weitere Informationen finden Sie unter [Ausnahmespezifikationen (Throw)](../../cpp/exception-specifications-throw-cpp.md) .

Sie können diese Warnung vermeiden, indem die [Warnung](../../preprocessor/warning.md) Pragma:

```
#pragma warning( disable : 4290 )
```

Im folgenden Codebeispiel wird die C4290 generiert:

```
// C4290.cpp
// compile with: /EHs /W3 /c
void f1(void) throw(int) {}   // C4290

// OK
void f2(void) throw() {}
void f3(void) throw(...) {}
```