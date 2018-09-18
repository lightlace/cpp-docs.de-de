---
title: Compilerfehler C3068 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3068
dev_langs:
- C++
helpviewer_keywords:
- C3068
ms.assetid: 613e3447-b4a8-4268-a661-297bed63ccdf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fdea26e204032c27f00639ee46a928c7bf084a4e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46035619"
---
# <a name="compiler-error-c3068"></a>Compilerfehler C3068

'Funktion': eine naked-Funktion dürfen nicht Objekten, die Entladung erforderlich wäre, wenn eine C++-Ausnahme aufgetreten ist.

Der Compiler konnte nicht zum Ausführen der stapelentladung auf eine [naked](../../cpp/naked-cpp.md) -Funktion, die eine Ausnahme ausgelöst hat, da ein temporäres Objekt, in der Funktion und der C++-Ausnahmebehandlung erstellt wurde ([/EHsc](../../build/reference/eh-exception-handling-model.md)) angegeben wurde.

Führen Sie mindestens eine der folgenden Schritte aus, um diesen Fehler zu beheben:

- Kompilieren Sie nicht mit/EHsc.

- Kennzeichnen Sie die Funktion als nicht `naked`.

- Erstellen Sie ein temporäres Objekt nicht in der Funktion.

Wenn eine Funktion ein temporäres Objekt auf dem Stapel erstellt, wenn die Funktion eine Ausnahme auslöst, und C++-Ausnahmebehandlung aktiviert ist, wird der Compiler im Stapel gelöscht, wenn eine Ausnahme ausgelöst wird.

Wenn eine Ausnahme ausgelöst wird, vom Compiler Code generierte, dem den Prolog und Epilog nicht in einer bloßen Funktion vorhanden sind, werden für eine Funktion ausgeführt.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3068 generiert:

```
// C3068.cpp
// compile with: /EHsc
// processor: x86
class A {
public:
   A(){}
   ~A(){}
};

void b(A){}

__declspec(naked) void c() {
   b(A());   // C3068
};
```