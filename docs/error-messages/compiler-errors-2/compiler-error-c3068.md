---
title: Compilerfehler C3068
ms.date: 11/04/2016
f1_keywords:
- C3068
helpviewer_keywords:
- C3068
ms.assetid: 613e3447-b4a8-4268-a661-297bed63ccdf
ms.openlocfilehash: 9e20333a4fc18219f7f2514f3aefe73b81f284a6
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759489"
---
# <a name="compiler-error-c3068"></a>Compilerfehler C3068

"Function": eine naked-Funktion kann keine Objekte enthalten, für die eine Entwickelung C++ erforderlich wäre, wenn eine Ausnahme aufgetreten ist.

Der Compiler konnte keine Stapel Auflösung für eine [Naked](../../cpp/naked-cpp.md) -Funktion ausführen, die eine Ausnahme ausgelöst hat, weil ein temporäres Objekt in der Funktion C++ erstellt und die Ausnahmebehandlung ([/EHsc](../../build/reference/eh-exception-handling-model.md)) angegeben wurde.

Führen Sie mindestens eine der folgenden Aktionen aus, um diesen Fehler zu beheben:

- Nicht mit/EHsc. kompilieren

- Markieren Sie die Funktion nicht als `naked`.

- Erstellen Sie in der-Funktion kein temporäres-Objekt.

Wenn eine Funktion ein temporäres Objekt auf dem Stapel erstellt, wenn die Funktion eine Ausnahme auslöst und die C++ Ausnahmebehandlung aktiviert ist, bereinigt der Compiler den Stapel, wenn eine Ausnahme ausgelöst wird.

Wenn eine Ausnahme ausgelöst wird, wird der vom Compiler generierte Code, der als Prolog und Epilogcode bezeichnet und nicht in einer naked-Funktion vorhanden ist, für eine Funktion ausgeführt.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3068 generiert:

```cpp
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
