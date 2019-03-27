---
title: Compilerfehler C2059
ms.date: 03/26/2019
f1_keywords:
- C2059
helpviewer_keywords:
- C2059
ms.assetid: 2be4eb39-3f37-4b32-8e8d-75835e07c78a
ms.openlocfilehash: 2fb2aa86a1fd8f8e0710d787682fdd44abd941ec
ms.sourcegitcommit: 06fc71a46e3c4f6202a1c0bc604aa40611f50d36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "58508831"
---
# <a name="compiler-error-c2059"></a>Compilerfehler C2059

Syntaxfehler: "token"

Das Token verursachte einen Syntaxfehler.

Im folgenden Beispiel wird eine Fehlermeldung für die Zeile, die deklariert `j`.

```
// C2059e.cpp
// compile with: /c
// C2143 expected
// Error caused by the incorrect use of '*'.
   int j*; // C2059
```

Um die Ursache des Fehlers zu ermitteln, untersuchen Sie nicht nur die Zeile, die in der Fehlermeldung aufgeführt ist, sondern auch die darüber liegenden Zeilen. Wenn keine Ahnung, über das Problem untersuchen die Zeilen zu werden, versuchen Sie die Zeile, die in der Fehlermeldung aufgeführt ist und möglicherweise mehrere Zeilen darüber auskommentieren.

Wenn die Fehlermeldung auf ein Symbol auftritt, die unmittelbar folgt eine `typedef` Variable, stellen Sie sicher, dass die Variable im Quellcode definiert ist.

C2059 generiert wird ausgelöst, wenn ein Präprozessorsymbol Name erneut als Bezeichner verwendet wird. Im folgenden Beispiel erkennt der Compiler `DIGITS.ONE` als die Zahl 1, dies ist nicht zulässig als Name für eine Enum-Element:

```cpp
#define ONE 1

enum class DIGITS {
    ZERO,
    ONE // error C2059
};
```

Ergibt ein Symbol auf nichts verweist, wie auftreten können, erhalten Sie möglicherweise C2059 beim **/d**_Symbol_ **=** wird verwendet, um Sie zu kompilieren.

```
// C2059a.cpp
// compile with: /DTEST=
#include <stdio.h>

int main() {
   #ifdef TEST
      printf_s("\nTEST defined %d", TEST);   // C2059
   #else
      printf_s("\nTEST not defined");
   #endif
}
```

Ein weiterer Fall, in dem C2059 auftreten können, ist beim Kompilieren einer Anwendungs, die eine Struktur in die Standardargumente für eine Funktion angibt. Der Standardwert für ein Argument muss ein Ausdruck sein. Eine Initialisiererliste – z. B. eine, die zum Initialisieren einer Struktur verwendet, ist kein Ausdruck.  Um dieses Problem zu beheben, definieren Sie einen Konstruktor, um die erforderliche Initialisierung auszuführen.

Im folgende Beispiel wird die C2059 generiert:

```
// C2059b.cpp
// compile with: /c
struct ag_type {
   int a;
   float b;
   // Uncomment the following line to resolve.
   // ag_type(int aa, float bb) : a(aa), b(bb) {}
};

void func(ag_type arg = {5, 7.0});   // C2059
void func(ag_type arg = ag_type(5, 7.0));   // OK
```

C2059 kann bei einer Umwandlung falsch formatiertes auftreten.

Im folgende Beispiel wird die C2059 generiert:

```
// C2059c.cpp
// compile with: /clr
using namespace System;
ref class From {};
ref class To : public From {};

int main() {
   From^ refbase = gcnew To();
   To^ refTo = safe_cast<To^>(From^);   // C2059
   To^ refTo2 = safe_cast<To^>(refbase);   // OK
}
```

C2059 kann auch auftreten, wenn Sie versuchen, einen Namespacenamen zu erstellen, der einen Punkt enthält.

Im folgende Beispiel wird die C2059 generiert:

```
// C2059d.cpp
// compile with: /c
namespace A.B {}   // C2059

// OK
namespace A  {
   namespace B {}
}
```

C2059 kann auftreten, wenn ein Operator, der einen Namen qualifiziert werden kann (`::`, `->`, und `.`) muss das Schlüsselwort folgen `template`, wie im folgenden Beispiel gezeigt:

```cpp
template <typename T> struct Allocator {
    template <typename U> struct Rebind {
        typedef Allocator<U> Other;
    };
};

template <typename X, typename AY> struct Container {
    typedef typename AY::Rebind<X>::Other AX; // error C2059
};
```

Standardmäßig C++ setzt voraus, dass `AY::Rebind` keine Vorlage ist; daher die folgenden `<` interpretiert wird, wie ein kleiner-als-Zeichen.  Sie müssen weisen dem Compiler explizit, die `Rebind` ist eine Vorlage aus, so dass sie ordnungsgemäß für die Spitze Klammer analysieren kann. Um diesen Fehler zu korrigieren, verwenden die `template` Schlüsselwort auf dem abhängigen Namen des Typs, wie hier gezeigt:

```cpp
template <typename T> struct Allocator {
    template <typename U> struct Rebind {
        typedef Allocator<U> Other;
    };
};

template <typename X, typename AY> struct Container {
    typedef typename AY::template Rebind<X>::Other AX; // correct
};
```
