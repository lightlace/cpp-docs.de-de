---
title: Compilerfehler Fehler C2280 | Microsoft Docs
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
ms.openlocfilehash: b55e07a7109c090126dfdec61bbc18bdaf5ef710
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33177644"
---
# <a name="compiler-error-c2280"></a>Compilerfehler Fehler C2280  
  
"*Deklaration*": Es wird versucht, eine gelöschte Funktion zu verweisen  
  
Der Compiler hat festgestellt, der Versuch einen verweisen eine `deleted` Funktion. Dieser Fehler kann verursacht werden, durch einen Aufruf an eine Memberfunktion, die explizit als markiert wurde `= deleted` im Quellcode. Dieser Fehler kann auch verursacht werden, durch einen Aufruf eine implizite spezielle Memberfunktion einer Struktur oder Klasse, die automatisch deklariert und markiert als `deleted` durch den Compiler. Weitere Informationen darüber, wenn der Compiler automatisch generiert `default` oder `deleted` spezielle Memberfunktionen finden Sie unter [spezielle Memberfunktionen](../../cpp/special-member-functions.md).  
  
## <a name="example-explicitly-deleted-functions"></a>Beispiel: Explizit deleted-Funktionen  

Ein Aufruf einer explizit `deleted` Funktion verursacht diesen Fehler. Ein explizit `deleted` Memberfunktion impliziert, dass die Klasse oder Struktur dient absichtlich zum Verhindern der Verwendungsmöglichkeiten, um dieses Problem zu beheben, sollten Sie den Code, um es zu vermeiden.  
  
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
  
Eine nicht initialisierte Verweismember Datentyp oder `const` -Datenmember bewirkt, dass der Compiler implizit deklariert eine `deleted` Standardkonstruktor. Um dieses Problem zu beheben, initialisieren Sie das Datenelement, nach deren Deklaration ist.  
  
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
  
Ein `const` oder Verweis Typdatenmember veranlasst den Compiler, deklarieren Sie eine `deleted` Kopierzuweisungsoperator. Nach der Initialisierung können diese Member, zugewiesen werden, damit eine einfache Kopier- oder Verschiebevorgänge nicht funktionieren. Um dieses Problem zu beheben, wird empfohlen, dass Sie Ihre Logik, um die Zuweisungsvorgänge zu entfernen, die bei des Fehlers auftreten geändert werden.  
  
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
  
Wenn eine Klasse ein bewegungskonstruktor oder bewegungszuweisungsoperator deklariert, aber nicht explizit einen Kopierkonstruktor deklarieren, der Compiler implizit einen Kopierkonstruktor deklariert und definiert als `deleted`. Auf ähnliche Weise, wenn eine Klasse ein bewegungskonstruktor oder bewegungszuweisungsoperator deklariert, aber nicht explizit einen Kopierzuweisungsoperator deklarieren, der Compiler implizit deklariert einen Kopierzuweisungsoperator und definiert als `deleted`. Um dieses Problem zu beheben, müssen Sie diese Member explizit deklarieren.  
 
Wenn angezeigt wird, Fehler "C2280" in Verbindung mit einer `unique_ptr`, es ist fast sicherlich, da Sie versuchen, den Kopierkonstruktor aufzurufen, der ist eine `deleted` Funktion. Programmbedingt eine `unique_ptr` kann nicht kopiert werden. Verwenden Sie einen bewegungskonstruktor, um den Besitz stattdessen übertragen.  

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
  
Compilerversionen vor Visual Studio 2015 Update 2 wurden nicht konforme und generierte standardmäßige Konstruktoren und Destruktoren für anonyme Unions. Diese werden jetzt implizit als deklariert `deleted`. Diese Versionen werden ebenfalls nicht konforme implizite Definition der zulässig `default` Kopier- und bewegungskonstruktoren und `default` kopieren und Verschieben von Zuweisungsoperatoren in Klassen und Strukturen, die über `volatile` Membervariablen. Der Compiler jetzt betrachtet diese mit nicht trivialen Konstruktoren und Zuweisungsoperatoren haben und nicht generieren `default` Implementierungen. Wenn eine solche Klasse ein Member einer Union oder einer anonymen Union innerhalb einer Klasse ist, verschieben und Kopieren von Konstruktoren und verschieben und kopieren Zuweisungsoperatoren der Union oder Klasse sind implizit definiert als `deleted`. Um dieses Problem zu beheben, müssen Sie die erforderlichen speziellen Memberfunktionen explizit deklarieren.  
  
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
  
Compilerversionen vor Visual Studio 2015 Update 2 wurden nicht konforme und eine abgeleitete Klasse, um spezielle Memberfunktionen aufrufen, der indirekt abgeleiteten zulässig `private virtual` Basisklassen. Der Compiler gibt jetzt Compilerfehler C2280 aus, wenn ein Aufruf erfolgt ist.  
  
In diesem Beispiel-Klasse `top` indirekt ableitet, Private virtuelle `base`. Im übereinstimmenden Code dadurch die Member der `base` nicht zugegriffen werden kann, um `top`; ein Objekt des Typs `top` nicht standardmäßig erstellt oder zerstört. Ändern Sie zur Behebung dieses Problems im Code, der auf das alte Compilerverhalten baute, die intermediate-Klasse, verwendet `protected virtual` Ableitung, oder ändern Sie die `top` Klasse, um die direkte Ableitung verwenden:  

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
  