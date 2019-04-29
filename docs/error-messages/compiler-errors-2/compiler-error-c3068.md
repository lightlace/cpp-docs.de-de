---
title: Compilerfehler C3068
ms.date: 11/04/2016
f1_keywords:
- C3068
helpviewer_keywords:
- C3068
ms.assetid: 613e3447-b4a8-4268-a661-297bed63ccdf
ms.openlocfilehash: 4790c9caafd28722f3631104cfe5cfc762cf6426
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406885"
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