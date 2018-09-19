---
title: Compilerfehler C2280 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/25/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2280
helpviewer_keywords:
- C2280
dev_langs:
- C++
ms.assetid: e6c5b1fb-2b9b-4554-8ff9-775eeb37161b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b401ba3755113a71dd401efa8da1fe46adfe6a45
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46108669"
---
# <a name="compiler-error-c2280"></a>Compilerfehler C2280

"*Deklaration*': Es wird versucht, eine gelöschte Funktion zu verweisen

Der Compiler hat erkannt, auf Sie verweisen auf eine `deleted` Funktion. Dieser Fehler kann verursacht werden, durch einen Aufruf an eine Memberfunktion, die explizit als markiert wurde `= deleted` im Quellcode. Dieser Fehler kann auch verursacht werden, durch einen Aufruf eine implizite spezielle Memberfunktion einer Struktur oder Klasse, die automatisch deklariert und markiert als `deleted` durch den Compiler. Weitere Informationen zu können, wenn der Compiler automatisch generiert `default` oder `deleted` spezielle Memberfunktionen finden Sie unter [spezielle Memberfunktionen](../../cpp/special-member-functions.md).

## <a name="example-explicitly-deleted-functions"></a>Beispiel: Explizit deleted-Funktionen

Ein Aufruf einer explizit `deleted` Funktion verursacht diesen Fehler. Ein explizit `deleted` Member-Funktion bedeutet, dass die Klasse oder Struktur ist absichtlich zu zu verhindern, dass die verwenden, um dieses Problem zu beheben, ändern Sie sollten den Code, um dies zu vermeiden.

```cpp
// C2280_explicit.cpp
// compile with: cl /c /W4 C2280_explicit.cpp
struct A {
    A();
    A(int) = delete;
};

struct B {
    A a1;
    A a2 = A(3); // C2280, calls deleted A::A(int)
    // To fix, remove the call to A(int)
};

void f() {
    B b;    // calls implicit B::B(void)
}
```

## <a name="example-uninitialized-data-members"></a>Beispiel: Nicht initialisierte Datenmember

Eine nicht initialisierte Typ Verweisdatenmember oder `const` Datenmember, generiert der Compiler implizit deklarieren eine `deleted` Standardkonstruktor. Um dieses Problem zu beheben, Initialisieren des Datenmembers, wenn sie deklariert wird.

```cpp
// C2280_uninit.cpp
// compile with: cl /c C2280_uninit.cpp
struct A {
    const int i; // uninitialized const-qualified data
    // members or reference type data members cause
    // the implicit default constructor to be deleted.
    // To fix, initialize the value in the declaration:
    // const int i = 42;
} a;    // C2280
```

## <a name="example-reference-and-const-data-members"></a>Beispiel: Verweis und const-Datenmember

Ein `const` oder Verweisdatenmember für den Typ veranlasst den Compiler, deklarieren Sie eine `deleted` Kopierzuweisungsoperator. Nach der Initialisierung können nicht, diese Member zugewiesen werden, damit ein einfaches Kopieren oder Verschieben nicht funktioniert. Um dieses Problem zu beheben, empfehlen wir, dass Sie ändern die Logik, um die Zuweisungsvorgänge zu entfernen, die den Fehler zu verursachen.

```cpp
// C2280_ref.cpp
// compile with: cl /c C2280_ref.cpp
extern int k;
struct A {
    A();
    int& ri = k; // a const or reference data member causes
    // implicit copy assignment operator to be deleted.
};

void f() {
    A a1, a2;
    // To fix, consider removing this assignment.
    a2 = a1;    // C2280
}
```

## <a name="example-movable-deletes-implicit-copy"></a>Beispiel: Verschiebbare wird die implizite Kopie gelöscht.

Wenn eine Klasse ein bewegungskonstruktor oder bewegungszuweisungsoperator deklariert, aber nicht explizit einen Kopierkonstruktor deklarieren, der Compiler implizit einen Kopierkonstruktor deklariert und definiert es als `deleted`. Wenn eine Klasse ein bewegungskonstruktor oder bewegungszuweisungsoperator deklariert, aber nicht explizit einen Kopierzuweisungsoperator deklarieren, der Compiler implizit einen Kopierzuweisungsoperator deklariert und definiert es als `deleted`. Um dieses Problem zu beheben, müssen Sie diese Member explizit deklarieren.

Wenn angezeigt wird, Fehler "C2280" in Verbindung mit einer `unique_ptr`, es ist sicherlich, weil Sie versuchen, den Kopierkonstruktor aufzurufen, wird eine `deleted` Funktion. Standardmäßig eine `unique_ptr` kann nicht kopiert werden. Verwenden Sie einen bewegungskonstruktor, um den Besitz stattdessen übertragen.

```cpp
// C2280_move.cpp
// compile with: cl /c C2280_move.cpp
class base
{
public:
    base();
    ~base();
    base(base&&);
    // Move constructor causes copy constructor to be
    // implicitly declared as deleted. To fix this
    // issue, you can explicitly declare a copy constructor:
    // base(base&);
    // If you want the compiler default version, do this:
    // base(base&) = default;
};

void copy(base *p)
{
    base b{*p};  // C2280
}
```

## <a name="example-variant-and-volatile-members"></a>Beispiel: Variant und volatile-Elemente

Versionen des Compilers vor Visual Studio 2015 Update 2 wurden nicht konforme und generierte standardmäßige Konstruktoren und Destruktoren für anonyme Unions. Diese werden jetzt implizit als deklariert `deleted`. Diese Versionen werden ebenfalls nicht konforme implizite Definition von zulässig `default` Kopier- und bewegungskonstruktoren und `default` kopieren und verschieben Sie die Zuweisungsoperatoren in Klassen und Strukturen, die `volatile` Membervariablen. Der Compiler jetzt stuft diese als nicht trivialen Konstruktoren und Zuweisungsoperatoren haben und nicht generieren `default` Implementierungen. Wenn eine solche Klasse ein Member einer Union oder einer anonymen Union innerhalb einer Klasse ist, die Konstruktoren für verschieben und kopieren und verschieben und Kopieren von Zuweisungsoperatoren der Union oder Klasse implizit als definiert sind `deleted`. Um dieses Problem zu beheben, müssen Sie die erforderlichen speziellen Memberfunktionen explizit deklarieren.

```cpp
// C2280_variant.cpp
// compile with: cl /c C2280_variant.cpp
struct A {
    A() = default;
    A(const A&);
};

struct B {
    union {
        A a;
        int i;
    };
    // To fix this issue, declare the required
    // special member functions:
    // B();
    // B(const B& b);
};

int main() {
    B b1;
    B b2(b1);  // C2280
}
```

## <a name="example-indirect-base-members-deleted"></a>Beispiel: Indirekte Basismember gelöscht

Versionen des Compilers vor Visual Studio 2015 Update 2 wurden nicht konforme und war es abgeleiteten Klassen, die spezielle Memberfunktionen aufrufen, der indirekt abgeleiteten `private virtual` Basisklassen. Der Compiler gibt jetzt Compilerfehler c2280 generiert, wenn solch ein Aufruf erfolgt.

In diesem Beispiel-Klasse `top` indirekt abgeleitet ist, von der privaten virtuellen `base`. Im entsprechenden Code wird dadurch die Member der `base` für `top`; ein Objekt vom Typ `top` nicht standardmäßig erstellt oder zerstört wird. Ändern Sie zum Beheben dieses Problems im Code, der auf dem alten Compilerverhalten beruhte, die dazwischen liegende Klasse mit `protected virtual` Ableitung, oder ändern Sie die `top` Klasse, um die direkte Ableitung verwenden:

```cpp
// C2280_indirect.cpp
// compile with: cl /c C2280_indirect.cpp
class base
{
protected:
    base();
    ~base();
};

class middle : private virtual base {};
// Possible fix: Replace line above with:
// class middle : protected virtual base {};
class top : public virtual middle {};    // C4594, C4624
// Another possible fix: use direct derivation:
// class top : public virtual middle, private virtual base {};

void destroy(top *p)
{
    delete p;  // C2280
}
```
