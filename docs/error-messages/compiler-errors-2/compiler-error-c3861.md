---
title: Compilerfehler C3861
ms.date: 03/23/2018
f1_keywords:
- C3861
helpviewer_keywords:
- C3861
ms.assetid: 0a1eee30-b3db-41b1-b1e5-35949c3924d7
ms.openlocfilehash: 4ebfd3b0129e25cf543cac803a3b33fb074f3d70
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62302410"
---
# <a name="compiler-error-c3861"></a>Compilerfehler C3861

> "*Bezeichner*": Bezeichner wurde nicht gefunden.

Der Compiler konnte einen Verweis sogar mit der Suche „argument-dependent“ zu einem Bezeichner nicht auflösen.

## <a name="remarks"></a>Hinweise

Um diesen Fehler zu beheben, vergleichen Sie die Verwendung von *Bezeichner* auf die identifziererdeklaration hinsichtlich Groß-/Kleinschreibung und Rechtschreibung. Überprüfen Sie, ob [Bereich Auflösung Operatoren](../../cpp/scope-resolution-operator.md) und Namespace [using-Direktiven](../../cpp/namespaces-cpp.md#using_directives) ordnungsgemäß verwendet werden. Wenn der Bezeichner in einer Headerdatei deklariert ist, stellen Sie sicher, dass der Header einbezogen werden, bevor der Bezeichner referenziert wird. Wenn der Bezeichner als extern sichtbar sein soll, stellen Sie sicher, dass sie in jeder Quelldatei deklariert ist, der verwendet wird. Überprüfen Sie auch, dass der Bezeichner-Deklaration oder Definition nicht ausgeschlossen ist [Bedingte Kompilierungsdirektiven](../../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md).

Änderungen an veraltete Funktionen aus der C-Laufzeitbibliothek in Visual Studio 2015 zu entfernen, können C3861 führen. Um diesen Fehler zu beheben, entfernen Sie Verweise auf diese Funktionen, oder Ersetzen Sie sie durch ihre sichere Alternativen, sofern vorhanden. Weitere Informationen finden Sie unter [veraltete Funktionen](../../c-runtime-library/obsolete-functions.md).

Wenn der Fehler C3861 aus älteren Versionen des Compilers nach der Projektmigration angezeigt wird, Sie möglicherweise Probleme im Zusammenhang mit unterstützten Windows-Versionen. Visual C++ unterstützt nicht mehr die Zielversionen Windows 95, Windows 98, Windows ME, Windows NT oder Windows 2000. Wenn das **WINVER** - oder **_WIN32_WINNT** -Makro einer dieser Versionen von Windows zugewiesen ist, müssen Sie die Makros ändern. Weitere Informationen finden Sie unter [Ändern von WINVER und _WIN32_WINNT](../../porting/modifying-winver-and-win32-winnt.md).

## <a name="examples"></a>Beispiele

### <a name="undefined-identifier"></a>Nicht definierter Bezeichner

Im folgende Beispiel wird C3861 generiert, da der Bezeichner nicht definiert ist.

```cpp
// C3861.cpp
void f2(){}
int main() {
   f();    // C3861
   f2();   // OK
}
```

### <a name="identifier-not-in-scope"></a>Der Bezeichner nicht im Bereich

Im folgende Beispiel wird C3861 generiert: ein Bezeichner ist nur im Dateibereich seiner Definition, sichtbar, es sei denn, sie in anderen Quelldateien deklariert ist, die sie verwenden.

```cpp
// C3861_a1.cpp
// Compile with: cl /EHsc /W4 C3861_a1.cpp C3861_a2.cpp
#include <iostream>
// Uncomment the following line to fix:
// int f();  // declaration makes external function visible
int main() {
   std::cout << f() << std::endl;    // C3861
}
```

```cpp
// C3861_a2.cpp
int f() {  // declared and defined here
   return 42;
}
```

### <a name="namespace-qualification-required"></a>Namespace-Qualifizierung erforderlich

Ausnahmeklassen in der C++-Standardbibliothek erfordern die `std` Namespace.

```cpp
// C3861_b.cpp
// compile with: /EHsc
#include <iostream>
int main() {
   try {
      throw exception("Exception");   // C3861
      // try the following line instead
      // throw std::exception("Exception");
   }
   catch (...) {
      std::cout << "caught an exception" << std::endl;
   }
}
```

### <a name="obsolete-function-called"></a>Veraltete Funktion wird aufgerufen

Veraltete Funktionen wurden aus der CRT-Bibliothek entfernt.

```cpp
// C3861_c.cpp
#include <stdio.h>
int main() {
   char line[21]; // room for 20 chars + '\0'
   gets( line );  // C3861
   // Use gets_s instead.
   printf( "The line entered was: %s\n", line );
}
```

### <a name="adl-and-friend-functions"></a>ADL und Friend-Funktionen

Das folgende Beispiel generiert C3767, da der Compiler nicht das Argumentabhängige Lookup für verwendet `FriendFunc`:

```cpp
namespace N {
   class C {
      friend void FriendFunc() {}
      friend void AnotherFriendFunc(C* c) {}
   };
}

int main() {
   using namespace N;
   FriendFunc();   // C3861 error
   C* pC = new C();
   AnotherFriendFunc(pC);   // found via argument-dependent lookup
}
```

Um den Fehler zu beheben, deklarieren Sie die "Friend" in den Gültigkeitsbereich der Klasse, und im Namespacebereich definieren:

```cpp
class MyClass {
   int m_private;
   friend void func();
};

void func() {
   MyClass s;
   s.m_private = 0;
}

int main() {
   func();
}
```
