---
title: Compilerfehler C2143 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2143
dev_langs:
- C++
helpviewer_keywords:
- C2143
ms.assetid: 1d8d1456-e031-4965-9240-09a6e33ba81c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1c6352c87748bafa635d8d6dae29bf37b78ac6c1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46041986"
---
# <a name="compiler-error-c2143"></a>Compilerfehler C2143

Syntaxfehler: Fehlendes "ttoken1" vor "token2"

Der Compiler erwartet ein bestimmtes Tokens (d. h. ein Sprachelement außer Leerzeichen) und stattdessen ein anderes Token gefunden.

Informationen zu diesem Fehler auftreten, wenn Sie einen Function-Try-Block verwenden, finden Sie unter [Knowledge Base-Artikel 241706](http://support.microsoft.com/kb/241706).

Überprüfen Sie die [C++-Sprachreferenz](../../cpp/cpp-language-reference.md) um zu bestimmen, in denen Code syntaktisch falsch ist. Da der Compiler diesen Fehler zu melden kann, nachdem er die Zeile trifft, die das Problem verursacht, überprüfen Sie mehrere Codezeilen, die den Fehler vorausgegangen sind.

C2143 kann in verschiedenen Situationen auftreten.

Er kann auftreten, wenn ein Operator, der einen Namen qualifiziert werden kann (`::`, `->`, und `.`) muss das Schlüsselwort folgen `template`, wie in diesem Beispiel:

```cpp
class MyClass
{
    template<class Ty, typename PropTy>
    struct PutFuncType : public Ty::PutFuncType<Ty, PropTy> // error C2143
    {
    };
};

```

Standardmäßig C++ setzt voraus, dass `Ty::PutFuncType` keine Vorlage ist; daher die folgenden `<` interpretiert wird, wie ein kleiner-als-Zeichen.  Sie müssen weisen dem Compiler explizit, die `PutFuncType` ist eine Vorlage aus, so dass sie ordnungsgemäß für die Spitze Klammer analysieren kann. Um diesen Fehler zu korrigieren, verwenden die `template` Schlüsselwort auf dem abhängigen Namen des Typs, wie hier gezeigt:

```cpp
class MyClass
{
    template<class Ty, typename PropTy>
    struct PutFuncType : public Ty::template PutFuncType<Ty, PropTy> // correct
    {
    };
};

```

C2143 kann auftreten, wenn **"/ CLR"** wird verwendet, und ein `using` Anweisung einen Syntaxfehler aufweist:

```cpp
// C2143a.cpp
// compile with: /clr /c
using namespace System.Reflection;   // C2143
using namespace System::Reflection;
```

Er kann auch auftreten, wenn Sie versuchen, eine Quellcodedatei mit CLR-Syntax ohne auch Kompilieren **"/ CLR"**:

```cpp
// C2143b.cpp
ref struct A {   // C2143 error compile with /clr
   void Test() {}
};

int main() {
   A a;
   a.Test();
}
```

Das erste nicht-Leerzeichen, das folgt eine `if` Anweisung muss es sich um eine linke Klammer. Der Compiler kann nicht alles übersetzen:

```cpp
// C2143c.cpp
int main() {
   int j = 0;

   // OK
   if (j < 25)
      ;

   if (j < 25)   // C2143
}
```

C2143 tritt auf, wenn eine schließende geschweifte Klammer, Klammern oder durch Semikolon fehlt in der Zeile, in dem der Fehler erkannt wird, oder auf eine der Zeilen unmittelbar vor:

```cpp
// C2143d.cpp
// compile with: /c
class X {
   int member1;
   int member2   // C2143
} x;
```

Oder wenn ein ungültiges Tag in einer Klassendeklaration:

```cpp
// C2143e.cpp
class X {
   int member;
} x;

class + {};   // C2143 + is an invalid tag name
class ValidName {};   // OK
```

Oder wenn eine Bezeichnung nicht an eine Anweisung angefügt ist. Wenn eine Bezeichnung allein eingefügt werden soll, z. B. am Ende einer verbundanweisung, fügen Sie es an eine null-Anweisung:

```cpp
// C2143f.cpp
// compile with: /c
void func1() {
   // OK
   end1:
      ;

   end2:   // C2143
}
```

Der Fehler kann auftreten, wenn ein nicht qualifizierter Aufruf mit einem Typ in der C++-Standardbibliothek erfolgt:

```cpp
// C2143g.cpp
// compile with: /EHsc /c
#include <vector>
static vector<char> bad;   // C2143
static std::vector<char> good;   // OK
```

Oder es ist ein fehlendes `typename` Schlüsselwort:

```cpp
// C2143h.cpp
template <typename T>
struct X {
   struct Y {
      int i;
   };
   Y memFunc();
};
template <typename T>
X<T>::Y X<T>::memFunc() {   // C2143
// try the following line instead
// typename X<T>::Y X<T>::memFunc() {
   return Y();
}
```

Oder wenn Sie versuchen, eine explizite Instanziierung zu definieren:

```cpp
// C2143i.cpp
// compile with: /EHsc /c
// template definition
template <class T>
void PrintType(T i, T j) {}

template void PrintType(float i, float j){}   // C2143
template void PrintType(float i, float j);   // OK
```

Klicken Sie in einem C-Programm Variablen müssen am Anfang der Funktion deklariert werden, und sie können nicht deklariert werden, nachdem die Funktion nicht-Declaration-Anweisungen ausführt.

```C
// C2143j.c
int main()
{
    int i = 0;
    i++;
    int j = 0; // C2143
}
```
