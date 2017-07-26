---
title: 'Visual C++: Neuerungen von 2003 bis 2015 | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: c4afde6f-3d75-40bf-986f-be57e3818e26
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: 3c1955bece0c8cdadb4a151ee06fa006402666a4
ms.openlocfilehash: 7995451c0c89fbef55bd96291978775f89932f3b
ms.contentlocale: de-de
ms.lasthandoff: 06/08/2017

---
# <a name="visual-c-what39s-new-2003-through-2015"></a>Visual C++: Neuerungen von 2003 bis 2015

**Hinweis** Informationen zu Visual Studio 2017 finden Sie unter [Neuerungen bei Visual C++ in Visual Studio 2017](../what-s-new-for-visual-cpp-in-visual-studio.md) und [Verbesserungen bei der Übereinstimmung mit Standards in Visual C++ in Visual Studio 2017](../cpp-conformance-improvements-2017.md).

In Visual C++ 2015 und höher können fortlaufende Verbesserungen der Übereinstimmung des Compilers mit Standards mitunter ändern, wie der Compiler den vorhandenen Quellcode versteht. In diesem Fall treten während Ihres Builds ggf. neue oder andere Fehler oder sogar Verhaltensunterschiede im Code auf, für den zuvor Builds erstellt wurden und die Ausführung ordnungsgemäß schien.  
  
 Glücklicherweise haben diese Unterschiede wenig oder keinen Einfluss auf den Großteil Ihres Quellcodes. Sollten Quellcode- oder andere Änderungen zum Ausgleichen dieser Unterschiede erforderlich sein, sind Korrekturen in der Regel klein und einfach. Wir haben zahlreiche Beispiele für zuvor zulässigen Quellcode, die möglicherweise geändert werden müssen *(vorher)*, und die Updates zur Korrektur *(nachher)* hinzugefügt.  
  
 Obwohl diese Unterschiede sich auf Ihren Quellcode oder andere Buildartefakte auswirken können, wirken sie sich nicht auf die Binärkompatibilität zwischen Updates für Visual C++-Versionen aus. Eine schwerwiegendere Art der Änderung, die *bedeutende Änderung*, kann die Binärkompatibilität beeinträchtigen. Doch diese Arten von Unterbrechung der Binärkompatibilität treten nur zwischen Hauptversionen von Visual C++ auf. Beispielsweise zwischen Visual C++ 2013 und Visual C++ 2015. Informationen zu bedeutenden Änderungen, die zwischen Visual C++ 2013 und Visual C++ 2015 vorgenommen wurden, finden Sie unter [Änderungsverlauf von Visual C++ von 2003 bis 2015](../porting/visual-cpp-change-history-2003-2015.md).  
  
-   [Verbesserungen bei der Übereinstimmung mit Standards in Visual C++ 2015](#VS_RTM)  
  
-   [Verbesserungen bei der Übereinstimmung mit Standards in Update 1](#VS_Update1)  
  
-   [Verbesserungen bei der Übereinstimmung mit Standards in Update 2](#VS_Update2)  
  
-   [Verbesserungen bei der Übereinstimmung mit Standards in Update 3](#VS_Update3)  
  
##  <a name="VS_RTM"></a> Verbesserungen bei der Übereinstimmung mit Standards in Visual C++ 2015  
  
-   /Zc:forScope-Option  
  
     Die Compileroption **/Zc:forScope-** ist veraltet und wird in der nächsten Version entfernt.  
  
    ```  
    Command line warning  D9035: option 'Zc:forScope-' has been deprecated and will be removed in a future release  
    ```  
  
     Die Option wurde in der Regel für nicht dem Standard entsprechenden Code verwendet, der Schleifenvariablen gemäß dem Standard nach dem Punkt verwendet, an dem diese den Gültigkeitsbereich verlassen sollten. Dies war nur dann erforderlich, wenn die Kompilierung mit der /Za-Option erfolgte. Ohne der /Za-Option war eine Schleifenvariable nach dem Ende der Schleife immer zulässig. Wenn die Einhaltung von Standards keine Rolle spielt (z. B. wenn der Code nicht auf andere Compiler übertragbar ist), können Sie die /Za-Option deaktivieren (oder die Eigenschaft „Spracherweiterungen deaktivieren“ auf „Nein“ festlegen). Wenn Sie übertragbaren Code schreiben möchten, der den Standards entspricht, sollten Sie den Code umschreiben, indem Sie die Deklaration der Variablen an eine Stelle außerhalb der Schleifen verschieben.  
  
    ```  
    // zc_forScope.cpp  
    // compile with: /Zc:forScope- /Za  
    // C2065 expected  
    int main() {  
       // Uncomment the following line to resolve.  
       // int i;  
       for (int i =0; i < 1; i++)  
          ;  
       i = 20;   // i has already gone out of scope under /Za  
    }  
    ```  
  
-   **/Zg (Compileroption)**  
  
     Die /Zg-Compileroption (Funktionsprototypen generieren) ist nicht mehr verfügbar. Diese Compileroption wurde zuvor als veraltet markiert.  
  
-   Sie können Komponententests nicht mehr mit C++/CLI über die Befehlszeile mit mstest.exe ausführen. Verwenden Sie stattdessen vstest.console.exe. Siehe [Befehlszeilenoptionen für VSTest.Console.exe](/devops-test-docs/test/vstest-console-exe-command-line-options).  
  
-   **mutable (Schlüsselwort)**  
  
     Der `mutable` -Speicherklassenspezifizierer ist nicht mehr an Positionen zulässig, wo beim Kompilieren zuvor ein Fehler aufgetreten ist. Der Compiler generiert nun den Fehler C2071 (Ungültige Speicherklasse). Gemäß dem Standard kann der mutable-Spezifizierer nur auf Namen von Klassendatenmembern angewendet werden und kann nicht auf als konstant oder statisch deklarierte Namen sowie nicht auf Verweismember angewendet werden.  
  
     Beachten Sie z. B. folgenden Code:  
  
    ```  
    struct S {  
        mutable int &r;  
    };  
    ```  
  
     In früheren Versionen des Visual C++-Compilers war dies zulässig, jetzt generiert der Compiler jedoch den folgenden Fehler:  
  
    ```Output  
    error C2071: 'S::r': illegal storage class  
    ```  
  
     Entfernen Sie einfach das redundante mutable-Schlüsselwort, um den Fehler zu beheben.  
  
-   **char_16_t und char32_t**  
  
     `char16_t` oder `char32_t` können nicht mehr als Aliase in typedef verwendet werden, da diese Typen nun als integrierte Typen behandelt werden. Bisher war es üblich, dass Benutzer und Bibliothekenautoren char16_t und char32_t als Aliase von unit16_t und uint32_t definiert haben.  
  
    ```  
    #include <cstdint>  
  
    typedef uint16_t char16_t; //C2628  
    typedef uint32_t char32_t; //C2628  
  
    int main(int argc, char* argv[])  
    {  
    uint16_t x = 1; uint32_t y = 2;  
    char16_t a = x;   
    char32_t b = y;   
    return 0;  
    }  
    ```  
  
     Entfernen Sie zum Aktualisieren des Codes die typedef-Deklarationen und benennen Sie andere Bezeichner um, die mit diesen Namen in Konflikt stehen.  
  
-   **Nichttyp-Vorlagenparameter**  
  
     Bestimmter Code mit Nichttyp-Vorlagenparametern wird auf Typkompatibilität korrekt geprüft, wenn Sie explizite Vorlagenargumente bereitstellen. Der folgende Code wurde z. B. ohne Fehler in früheren Versionen von Visual C++ kompiliert.  
  
    ```  
    struct S1  
    {  
    void f(int);  
    void f(int, int);  
    };  
  
    struct S2  
    {  
    template <class C, void (C::*Function)(int) const> void f() {}  
    };  
  
    void f()  
    {  
    S2 s2;  
    s2.f<S1, &S1::f>();  
    }  
  
    ```  
  
     Der aktuelle Compiler generiert ordnungsgemäß einen Fehler, da der Typ des Vorlagenparameters nicht mit dem Vorlagenargument übereinstimmt (der Parameter ist ein Zeiger auf einen konstanten Member, die f-Funktion ist jedoch nicht konstant):  
  
    ```Output  
    error C2893: Failed to specialize function template 'void S2::f(void)'note: With the following template arguments:note: 'C=S1'note: 'Function=S1::f'  
    ```  
  
     Stellen Sie zum Beheben dieses Fehlers im Code sicher, dass der Typ des verwendeten Vorlagenarguments mit dem deklarierten Typ des Vorlagenparameters übereinstimmt.  
  
-   **__declspec(align)**  
  
     Der Compiler lässt `__declspec(align)` in Funktionen nicht mehr zu. Dies wurde bisher ignoriert, nun wird jedoch ein Compilerfehler generiert.  
  
    ```  
    error C3323: 'alignas' and '__declspec(align)' are not allowed on function declarations  
    ```  
  
     Entfernen Sie zum Beheben dieses Problems `__declspec(align)` aus der Funktionsdeklaration. Da dies keine Auswirkungen hatte, ändert sich durch das Entfernen nichts.  
  
-   **Ausnahmebehandlung**  
  
     Es gibt eine Reihe von Änderungen bei der Ausnahmebehandlung. Ausnahmeobjekte müssen kopiert oder verschoben werden können. Der folgende Code wurde [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)] kompiliert, kann jedoch in [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)] nicht kompiliert werden:  
  
    ```  
    struct S {  
    public:  
        S();  
    private:  
        S(const S &);  
    };  
  
    int main()  
    {  
        throw S(); // error  
    }  
  
    ```  
  
     Das Problem besteht darin, dass der Kopierkonstruktor privat ist. Somit kann das Objekt nicht während des normalen Betriebs der Ausnahmebehandlung kopiert werden. Das gleiche gilt, wenn der Kopierkonstruktor als `explicit`deklariert ist.  
  
    ```  
    struct S {  
        S();  
        explicit S(const S &);  
    };  
  
    int main()  
    {  
        throw S(); // error  
    }  
  
    ```  
  
     Stellen Sie zum Aktualisieren des Codes sicher, dass der Kopierkonstruktor für Ihr Ausnahmeobjekt öffentlich und nicht als `explicit`deklariert ist.  
  
     Beim Abfangen einer Ausnahme nach Wert muss das Ausnahmeobjekt ebenfalls kopiert werden können. Der folgende Code wurde [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)] kompiliert, kann jedoch in [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)] nicht kompiliert werden:  
  
    ```  
    struct B {  
    public:  
        B();  
    private:  
        B(const B &);  
    };  
  
    struct D : public B {  
    };  
  
    int main()  
    {  
        try  
        {  
        }  
        catch (D d) // error  
        {  
        }  
    }  
  
    ```  
  
     Sie können dieses Problem beheben, indem Sie das den Parametertyp für `catch` auf einen Verweis festlegen.  
  
    ```  
    catch(D& d)  
    {  
    }  
    ```  
  
-   **Zeichenfolgenliterale gefolgt von Makros**  
  
     Der Compiler unterstützt nun benutzerdefinierte Literale. Folglich werden Zeichenfolgenliterale, auf die Makros ohne dazwischenliegende Leerzeichen folgen, als benutzerdefinierte Literale interpretiert, was zu Fehlern oder unerwarteten Ergebnissen führen kann. In vorherigen Compilern wurde der beispielsweise der folgende Code erfolgreich kompiliert:  
  
    ```  
    #define _x "there"  
    char* func() {  
        return "hello"_x;  
    }  
    int main()  
    {  
        char * p = func();  
        return 0;  
    }  
    ```  
  
     Der Compiler interpretierte dies als ein Zeichenfolgenliteral „Hello“ gefolgt von einem Makro, das um „there“ erweitert wird, und führte die zwei Zeichenfolgenliterale zu einer verketteten Zeichenfolge zusammen. In [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)] interpretiert der Compiler dies als ein benutzerdefiniertes Literal, aber da kein entsprechendes benutzerdefiniertes Literal _x definiert ist, wird ein Fehler generiert.  
  
    ```  
    error C3688: invalid literal suffix '_x'; literal operator or literal operator template 'operator ""_x' not found  
    note: Did you forget a space between the string literal and the prefix of the following string literal?  
  
    ```  
  
     Fügen Sie zur Behebung dieses Problems ein Leerzeichen zwischen das Zeichenfolgenliteral und das Makro ein.  
  
-   **Angrenzende Zeichenfolgenliterale**  
  
     Auf ähnliche Weise wurden angrenzende Zeichenfolgenliterale ohne Leerzeichen aufgrund von zugehörigen Änderungen in der Zeichenfolgenanalyse als eine verkettete Zeichenfolge in den vorherigen Versionen von Visual C++ interpretiert. In [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)] müssen Sie ein Leerzeichen zwischen den beiden Zeichenfolgen hinzufügen. Der folgende Code muss z. B. geändert werden:  
  
    ```  
    char * str = "abc""def";  
    ```  
  
     Fügen Sie einfach ein Leerzeichen zwischen den beiden Zeichenfolgen hinzu.  
  
    ```  
    char * str = "abc" "def";  
    ```  
  
-   **Platzierungsoperatoren „new“ und „delete“**  
  
     An dem delete-Operator wurde eine Änderung vorgenommen, damit er den C++14-Standard entspricht. Detaillierte Informationen zur Standardänderung finden Sie unter [Aufhebung der Zuordnung mit C++-Größeninformationen](http://isocpp.org/files/papers/n3778.html). Durch die Änderungen wird eine Form des globalen delete-Operators hinzugefügt, der einen Größenparameter erfordert. Eine wichtige Änderung ist, dass wenn Sie zuvor einen delete-Operator mit der gleichen Signatur verwendet haben (damit dieser einem Platzierungsoperator „new“ entspricht) nun ein Compilerfehler geniert wird, nämlich C2956. Dieser tritt an der Stelle auf, an der der Plazierungsoperator „new“ verwendet wird, denn an dieser Stelle im Code versucht der Compiler einen entsprechenden delete-Operator zu identifizieren.  
  
     Die `void operator delete(void *, size_t)`-Funktion war ein Platzierungsoperator „delete“, die dem Platzierungsoperator „new“ der „void \* operator new(size_t, size_t)“-Funktion in C++11 entspricht. Durch die Aufhebung der Zuordnung mit C++14-Größeninformationen ist diese delete-Funktion nun eine *gewöhnliche Funktion zum Aufheben der Zuordnung* (globaler delete-Operator). Der Standard erfordert es, dass das Programm bei Verwendung eines Platzierungsoperators „new“, der eine entsprechenden delete-Funktion sucht und eine gewöhnliche Funktion zum Aufheben der Zuordnung ermittelt, nicht ordnungsgemäß formatiert ist.  
  
     Angenommen der Code definiert einen Platzierungsoperator „new“ und einen Platzierungsoperator „delete“:  
  
    ```  
    void * operator new(std::size_t, std::size_t);  
    void operator delete(void*, std::size_t) noexcept;  
  
    ```  
  
     Das Problem tritt aufgrund der Übereinstimmung zwischen den Funktionssignaturen im definierten Platzierungsoperator „delete“ und im neuen globalen delete-Operator. Überlegen Sie, ob Sie einen anderen Typ als size_t für alle Platzierungsoperatoren „new“ und „delete“ verwenden können.  Beachten Sie, dass der Typ der size_t-Typdefinition vom Compiler abhängig ist. In Visual C++ ist dies eine Typdefinition für eine ganze Zahl ohne Vorzeichen. Eine gute Lösung hierfür stellt die Verwendung eines enumerierten Typs wie die des folgenden dar:  
  
    ```  
    enum class my_type : size_t {};  
  
    ```  
  
     Ändern Sie anschließend die Definition der Platzierungsoperatoren „new“ und „delete“, um diesen Typ als zweites Argument anstelle von size_t zu verwenden. Sie müssen auch die Aufrufe des Platzierungsoperators „new“ aktualisieren, um den neuen Typ (z. B. den ganzzahligen Wert mithilfe von `static_cast<my_type>` zu konvertieren) zu übergeben und die Definition von „new“ und „delete“ so aktualisieren, dass dieser wieder in den ganzzahligen Typ umgewandelt wird. Dazu müssen Sie keine Enumeration verwenden. Ein Klassentyp mit einem size_t-Member funktioniert ebenfalls.  
  
     Eine alternative Lösung stellt möglicherweise eine vollständige Eliminierung des new-Platzierungsoperators dar. Wenn der Code mit dem new-Platzierungsoperator einen Speicherpool implementiert, wobei das Platzierungsargument die Größe des zugeordneten oder gelöschten Objekts ist, dann ist die Funktion zum Aufheben der Zuordnung mit Größeninformationen möglicherweise zum Ersetzen des benutzerdefinierten Speicherpoolcodes geeignet, und Sie können stattdessen den eigenen delete-Operator mit zwei Argumenten verwenden.  
  
     Wenn Sie Ihren Code nicht sofort aktualisieren möchten, können Sie mit der Compileroption „/Zc:sizedDealloc-“ das alte Verhalten wiederherstellen. Wenn Sie diese Option verwenden, sind die delete-Funktionen mit zwei Argumenten nicht mehr vorhanden und stehen nicht in Konflikt mit dem delete-Platzierungsoperator.  
  
-   **Union-Datenmember**  
  
     Union-Datenmember dürfen über keine Verweistypen verfügen. Der folgende Code wird in [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)] erfolgreich kompiliert, geniert jedoch in [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)] einen Fehler.  
  
    ```  
    union U1 {  
        const int i;  
    };  
    union U2 {  
       int &i;  
    };  
    union U3 {  
        struct {int &i;};  
    };  
    ```  
  
     Der oben genannte Code geniert die folgenden Fehler:  
  
    ```Output  
    test.cpp(67): error C2625: 'U2::i': illegal union member; type 'int &' is reference type  
    test.cpp(70): error C2625: 'U3::i': illegal union member; type 'int &' is reference type  
    ```  
  
     Ändern Sie zur Behebung dieses Fehlers die Verweistypen in einen Zeiger oder einen Wert. Für die Änderung des Typs in einen Zeiger sind Änderungen im Code erforderlich, der das Union-Feld verwendet. Durch die Änderung des Codes in einen Wert werden die in der Union gespeicherten Daten geändert, was Auswirkungen auf andere Felder hat, da Felder in Uniontypen den gleichen Speicher gemeinsam verwenden. Je nach Wertgröße kann dies ggf. auch die Größe der Union ändern.  
  
-   Anonyme Unions weisen nun eine größere Standardkonformität auf. Frühere Versionen des Compilers haben einen expliziten Konstruktor und Destruktor für anonyme Unions generiert. Diese werden in [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)] gelöscht.  
  
    ```  
    struct S {  
      S();  
     };  
  
     union {  
      struct {  
       S s;  
      };  
     } u; // C2280  
    ```  
  
     Der oben genannte Code geniert in [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)] die folgenden Fehler:  
  
    ```  
    error C2280: '<unnamed-type-u>::<unnamed-type-u>(void)': attempting to reference a deleted function  
    note: compiler has generated '<unnamed-type-u>::<unnamed-type-u>' here  
    ```  
  
     Geben Sie zur Behebung dieses Fehlers eigene Definitionen des Konstruktors und/oder des Destruktors an.  
  
    ```  
    struct S {  
    // Provide a default constructor by adding an empty function body.  
    S() {}   
    };  
  
    union {  
    struct {  
    S s;  
    };  
    } u;  
    ```  
  
-   **Unions mit anonymen Strukturen**  
  
     Zur Einhaltung des Standards wurde das Laufzeitverhalten für Member anonymer Strukturen in Unions geändert. Der Konstruktor für anonyme Strukturmember in einer Union wird nicht mehr implizit aufgerufen, wenn eine solche Union erstellt wird. Der Destruktor für anonyme Strukturmember in einer Union wird nicht mehr implizit aufgerufen, wenn die Union den Gültigkeitsbereich verlässt. Betrachten Sie den folgenden Code, in dem eine Union U eine anonyme Struktur mit einem Member enthält, der die Struktur S mit einem Destruktor darstellt.  
  
    ```  
    #include <stdio.h>  
    struct S {  
        S() { printf("Creating S\n"); }  
        ~S(){ printf("Destroying S\n"); }  
    };  
    union U {  
        struct {  
        S s;  
    };  
        U() {}  
        ~U(){}  
    };  
  
    void f()  
    {  
        U u;  
        // Destructor implicitly called here.  
    }  
  
    int main()  
    {  
        f();  
  
        char s[1024];  
        printf("Press any key.\n");  
        gets_s(s);  
        return 0;  
    }  
    ```  
  
     Der Konstruktor für S wird in [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)] immer dann aufgerufen, wenn die Union erstellt wird, und der Destruktor für S immer dann aufgerufen wird, wenn der Stapel für Funktion f bereinigt wird. In [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)] werden jedoch weder der Konstruktor noch der Destruktor aufgerufen. Der Compiler gibt eine Warnung zu dieser Verhaltensänderung aus.  
  
    ```Output  
    warning C4587: 'U::s': behavior change: constructor is no longer implicitly calledwarning C4588: 'U::s': behavior change: destructor is no longer implicitly called  
    ```  
  
     Benennen Sie zum Wiederherstellen des ursprünglichen Verhaltens die anonyme Struktur. Das Laufzeitverhalten von nicht anonymen Strukturen ist von der Compilerversion unabhängig.  
  
    ```  
    #include <stdio.h>  
  
    struct S {  
        S() { printf("Creating S.\n"); }  
        ~S() { printf("Destroying S\n"); }  
    };  
    union U {  
        struct {  
            S s;  
        } namedStruct;  
        U() {}  
        ~U() {}  
    };  
  
    void f()  
    {  
        U u;  
    }  
  
    int main()  
    {  
        f();  
  
        char s[1024];  
        printf("Press any key.\n");  
        gets_s(s);  
        return 0;  
    }  
    ```  
  
     Verschieben Sie alternativ den Konstruktor- und Destruktorcode in die neuen Funktionen, und fügen Sie diesen Funktionen aus der Konstruktor- und Destruktorunion Aufrufe hinzu.  
  
    ```  
    #include <stdio.h>  
  
    struct S {  
        void Create() { printf("Creating S.\n"); }  
        void Destroy() { printf("Destroying S\n"); }  
    };  
    union U {  
        struct {  
            S s;  
        };  
        U() { s.Create();  }  
        ~U() { s.Destroy(); }  
    };  
  
    void f()  
    {  
        U u;  
    }  
  
    int main()  
    {  
        f();  
  
    char s[1024];  
    printf("Press any key.\n");  
    gets_s(s);  
    return 0;  
    }  
    ```  
  
-   **Vorlagenauflösung**  
  
     Es wurden Änderungen an der Namensauflösung für Vorlagen vorgenommen. Bei Berücksichtigung der Kandidaten für eine Namensauflösung können potenzielle Namen in C++ ggf. eine ungültige Vorlageninstanziierung erzeugen. Diese ungültigen Instanziierungen generieren in der Regel keine Comilerfehler – das SFINAE-Prinzip (Ersetzungsfehler sind keine Fehler).  
  
     Wenn der Compiler jetzt von SFINAE zum Instanziieren der Spezialisierung einer Klassenvorlage aufgefordert wird, handelt es sich bei allen während dieses Prozesses aufgetretenen Fehler um Compilerfehler. In früheren Versionen hat der Compiler diese Fehler ignoriert. Beachten Sie z. B. folgenden Code:  
  
    ```  
    #include <type_traits>  
  
    template<typename T>  
    struct S  
    {  
    S() = default;  
    S(const S&);  
    S(S&&);  
  
    template<typename U, typename = typename std::enable_if<std::is_base_of<T, U>::value>::type>  
    S(S<U>&&);  
    };  
  
    struct D;  
  
    void f1()  
    {  
    S<D> s1;  
        S<D> s2(s1);  
    }  
  
    struct B  
    {  
    };  
  
    struct D : public B  
    {  
    };  
  
    void f2()  
    {  
    S<D> s1;  
        S<D> s2(s1);  
    }  
  
    ```  
  
     Beim Kompilieren mit dem aktuellen Compiler tritt der folgende Fehler auf:  
  
    ```Output  
    type_traits(1110): error C2139: 'D': an undefined class is not allowed as an argument to compiler intrinsic type trait '__is_base_of'  
    ..\t331.cpp(14): note: see declaration of 'D'  
    ..\t331.cpp(10): note: see reference to class template instantiation 'std::is_base_of<T,U>' being compiled  
            with  
            [  
                T=D,  
                U=D  
            ]  
    ```  
  
     Dies liegt daran, dass die D-Klasse zum Zeitpunkt des ersten Aufrufs von is_base_of noch nicht definiert war.  
  
     In diesem Fall besteht die Lösung darin, diese Typmerkmale nicht zu verwenden, bis die Klasse definiert wurde. Wenn Sie die Definitionen von B und D an den Anfang der Codedatei verschieben, wird der Fehler behoben. Überprüfen Sie, wenn sich die Definitionen in Headerdateien befinden, die Reihenfolge der Include-Anweisungen für die Headerdateien, um sicherzustellen, dass alle Klassendefinitionen kompiliert werden, bevor die problematischen Vorlagen verwendet werden.  
  
-   **Kopierkonstruktoren**  
  
     Sowohl in [!INCLUDE[vs_dev12](../atl-mfc-shared/includes/vs_dev12_md.md)] als auch in Visual Studio 2015 generiert der Compiler einen Kopierkonstruktor für eine Klasse, die über einen benutzerdefinierten Bewegungskonstruktor, jedoch über keinen benutzerdefinierten Kopierkonstruktor verfügt. In Dev14 wird dieser implizit generierte Kopierkonstruktor ebenfalls als „= delete“ gekennzeichnet.  
  
##  <a name="VS_Update1"></a> Verbesserungen bei der Übereinstimmung mit Standards in Update 1  
  
-   **Private virtuelle Basisklassen und indirekte Vererbung**  
  
     In früheren Versionen des Compilers war es abgeleiteten Klassen möglich, Member ihrer *indirekt abgeleiteten*`private virtual` Basisklassen aufzurufen. Dieses alte Verhalten war falsch und entsprach nicht dem C++-Standard. Der Compiler akzeptiert in dieser Weise erstellten Code nicht mehr und gibt den Compilerfehler C2280 als Ergebnis aus.  
  
    ```Output  
    error C2280: 'void *S3::__delDtor(unsigned int)': attempting to reference a deleted function  
    ```  
  
     Beispiel (vorher)  
  
    ```cpp  
    class base  
    {  
    protected:  
        base();  
        ~base();  
    };  
  
    class middle: private virtual base {};class top: public virtual middle {};  
  
    void destroy(top *p)  
    {  
        delete p;  //   
    }  
    ```  
  
     Beispiel (nachher)  
  
    ```cpp  
    class base;  // as above  
  
    class middle: protected virtual base {};  
    class top: public virtual middle {};  
  
    void destroy(top *p)  
    {  
        delete p;  
    }  
    ```  
  
     - oder -   
  
    ```  
    class base;  // as above  
  
    class middle: private virtual base {};  
    class top: public virtual middle, private virtual bottom {};  
  
    void destroy(top *p)  
    {  
        delete p;  
    }  
    ```  
  
-   **Überladener Operator „new“ und „delete“**  
  
     In früheren Versionen des Compilers konnte ein `operator new` , der kein Member war, und ein `operator delete` , der kein Member war, statisch deklariert werden und in anderen Namespaces als dem globalen deklariert werden.  Durch dieses alte Verhalten entstand eine Gefahr, dass das Programm den Operator `new` oder `delete` nicht in der vom Programmierer beabsichtigten Implementierung aufrief, was zu einem schlechten Laufzeitverhalten ohne Rückmeldung führte. Der Compiler akzeptiert in dieser Weise erstellten Code nicht mehr und gibt den Compilerfehler C2323 als Ergebnis aus.  
  
    ```Output  
    error C2323: 'operator new': non-member operator new or delete functions may not be declared static or in a namespace other than the global namespace.  
    ```  
  
     Beispiel (vorher)  
  
    ```cpp  
    static inline void * __cdecl operator new(size_t cb, const std::nothrow_t&)  // error C2323  
    ```  
  
     Beispiel (nachher)  
  
    ```cpp  
    void * __cdecl operator new(size_t cb, const std::nothrow_t&)  // removed 'static inline'  
    ```  
  
     Außerdem, auch wenn dazu keine spezifische Diagnose ausgegeben wird, wird ein Inlineoperator „new“ als nicht wohlgeformt angesehen.  
  
-   **Aufrufen von „operator *type*()“ (benutzerdefinierte Konversion) für Nichtklassentypen**  
  
     Frühere Versionen ließen den Aufruf von 'operator *type*()' für Nichtklassentypen zu und ignorierten den Aufruf stumm. Durch dieses alte Verhalten entstand die Gefahr der stummen Erzeugung von ungültigem Code, was zu unvorhersehbarem Laufzeitverhalten führt. Der Compiler akzeptiert in dieser Weise erstellten Code nicht mehr und gibt den Compilerfehler C2228 als Ergebnis aus.  
  
    ```Output  
    error C2228: left of '.operator type' must have class/struct/union  
    ```  
  
     Beispiel (vorher)  
  
    ```cpp  
    typedef int index_t;  
  
    void bounds_check(index_t index);  
  
    void login(int column)  
    {  
        bounds_check(column.operator index_t());  // error C2228  
    }  
    ```  
  
     Beispiel (nachher)  
  
    ```cpp  
    typedef int index_t;  
  
    void bounds_check(index_t index);  
  
    void login(int column)  
    {  
        bounds_check(column);  // removed cast to 'index_t', 'index_t' is an alias of 'int'  
    }  
    ```  
  
-   **Redundanter Typname in ausführlichen Typspezifizierern**  
  
     Frühere Versionen des Compilers ließen `typename` in ausführlichen Typbezeichnern zu; in dieser Weise erstellter Code ist semantisch inkorrekt. Der Compiler akzeptiert in dieser Weise erstellten Code nicht mehr und gibt den Compilerfehler C3406 als Ergebnis aus.  
  
    ```Output  
    error C3406: 'typename' cannot be used in an elaborated type specifier  
    ```  
  
     Beispiel (vorher)  
  
    ```cpp  
    template <typename class T>  
    class container;  
    ```  
  
     Beispiel (nachher)  
  
    ```cpp  
    template <class T>  // alternatively, could be 'template <typename T>'; 'typename' is not elaborating a type specifier in this case  
    class container;  
    ```  
  
-   **Typableitung von Arrays aus einer Initialisiererliste**  
  
     In früheren Versionen des Compilers wurde die Typableitung von Arrays aus einer Initialisiererliste nicht unterstützt. Der Compiler unterstützt jetzt diese Form der Typableitung. Das kann zur Folge haben, dass Aufrufe an Funktionsvorlagen mithilfe von Initialisiererlisten jetzt möglicherweise nicht mehr eindeutig sind, oder es wird eine andere Überladung gewählt als in früheren Versionen des Compilers. Um diese Probleme zu beheben, muss das Programm jetzt die vom Programmierer beabsichtigte Überladung explizit angeben.  
  
     Wenn dieses neue Verhalten dazu führt, dass bei der Überladungsauflösung ein weitere Kandidat als ebenso gut wie der historische Kandidat angesehen wird, ist der Aufruf nicht mehr eindeutig, und der Compiler gibt den Compilerfehler C2668 als Ergebnis aus.  
  
    ```Output  
    error C2668: 'function' : ambiguous call to overloaded function.  
    ```  
  
     Beispiel 1: Mehrdeutiger Aufruf einer überladenen Funktion (vorher)  
  
    ```cpp  
    // In previous versions of the compiler, code written in this way would unambiguously call f(int, Args...)  
    template <typename... Args>  
    void f(int, Args...);  //   
  
    template <int N, typename... Args>  
    void f(const int (&)[N], Args...);  
  
    int main()  
    {  
        // The compiler now considers this call ambiguous, and issues a compiler error  
        f({3});  error C2668: 'f' ambiguous call to overloaded function  
    }  
    ```  
  
     Beispiel 1: Mehrdeutiger Aufruf einer überladenen Funktion (nachher)  
  
    ```cpp  
    template <typename... Args>  
    void f(int, Args...);  //   
  
    template <int N, typename... Args>  
    void f(const int (&)[N], Args...);  
  
    int main()  
    {  
        // To call f(int, Args...) when there is just one expression in the initializer list, remove the braces from it.  
        f(3);  
    }  
    ```  
  
     Wenn dieses neue Verhalten bewirkt, dass ein anderer Kandidat bei der Überladungsauflösung als bessere Übereinstimmung als der historische Kandidat angesehen wird, wird der Aufruf unzweideutig zum neuen Kandidaten aufgelöst, was eine Änderung im Verhalten des Programms bewirkt, das vermutlich von den Absichten des Programmierers abweicht.  
  
     Beispiel 2: Änderung an der Überladungsauflösung (vorher)  
  
    ```cpp  
    // In previous versions of the compiler, code written in this way would unambiguously call f(S, Args...)  
    struct S  
    {  
        int i;  
        int j;  
    };  
  
    template <typename... Args>  
    void f(S, Args...);  
  
    template <int N, typename... Args>  
    void f(const int *&)[N], Args...);  
  
    int main()  
    {  
        // The compiler now resolves this call to f(const int (&)[N], Args...) instead  
        f({1, 2});  
    }  
    ```  
  
     Beispiel 2: Änderung an der Überladungsauflösung (nachher)  
  
    ```cpp  
    struct S;  // as before  
  
    template <typename... Args>  
    void f(S, Args...);  
  
    template <int N, typename... Args>  
    void f(const int *&)[N], Args...);  
  
    int main()  
    {  
        // To call f(S, Args...), perform an explicit cast to S on the initializer list.  
        f(S{1, 2});  
    }  
    ```  
  
-   **Wiederherstellung von Warnungen der switch-Anweisung**  
  
     In früheren Versionen des Compilers wurden bereits vorhandene Warnungen, die sich auf `switch` -Anweisungen bezogen, entfernt; diese Warnungen wurden jetzt wiederhergestellt. Der Compiler gibt jetzt die wiederhergestellten Warnungen aus, und Warnungen, die sich auf bestimmte Fälle (einschließlich des Standardfalls) bezogen, werden jetzt in der Zeile ausgegeben, die den Verstoß enthält, statt in der letzten Zeile der switch-Anweisung. Die Ausgabe dieser Warnungen in anderen Zeilen als bisher kann zur Folge haben, dass Warnungen, die früher mithilfe von `#pragma warning(disable:####)` unterdrückt wurden, möglicherweise nicht mehr wie beabsichtigt unterdrückt werden. Um diese Warnungen wie beabsichtigt zu unterdrücken, kann es erforderlich sein, die `#pragma warning(disable:####)` -Anweisung in eine Zeile oberhalb des ersten möglichen Verstoßes zu verschieben. Die wiederhergestellten Warnungen folgen hier:  
  
    ```Output  
    warning C4060: switch statement contains no 'case' or 'default' labels  
    ```  
  
    ```Output  
    warning C4061: enumerator 'bit1' in switch of enum 'flags' is not explicitly handled by a case label  
    ```  
  
    ```Output  
    warning C4062: enumerator 'bit1' in switch of enum 'flags' is not handled  
    ```  
  
    ```Output  
    warning C4063: case 'bit32' is not a valid value for switch of enum 'flags'  
    ```  
  
    ```Output  
    warning C4064: switch of incomplete enum 'flags'  
    ```  
  
    ```Output  
    warning C4065: switch statement contains 'default' but no 'case' labels  
    ```  
  
    ```Output  
    warning C4808: case 'value' is not a valid value for switch condition of type 'bool'  
    ```  
  
    ```Output  
    Warning C4809: switch statement has redundant 'default' label; all possible 'case' labels are given  
    ```  
  
     Beispiel für C4063 (vorher)  
  
    ```cpp  
    class settings  
    {  
    public:  
        enum flags  
        {  
            bit0 = 0x1,  
            bit1 = 0x2,  
            ...  
        };  
        ...  
    };  
  
    int main()  
    {  
        auto val = settings::bit1;  
  
        switch (val)  
        {  
        case settings::bit0:  
            break;  
  
        case settings::bit1:  
            break;  
  
        case settings::bit0 | settings::bit1:  // warning C4063  
            break;  
        }  
    };  
    ```  
  
     Beispiel für C4063 (nachher)  
  
    ```cpp  
    class settings {...};  // as above  
  
    int main()  
    {  
        // since C++11, use std::underlying_type to determine the underlying type of an enum  
        typedef std::underlying_type<settings::flags>::type flags_t;  
  
        auto val = settings::bit1;  
  
        switch (static_cast<flags_t>(val))  
        {  
        case settings::bit0:  
            break;  
  
        case settings::bit1:  
            break;  
  
        case settings::bit0 | settings::bit1:  // ok  
            break;  
        }  
    };  
    ```  
  
     Beispiele für die anderen wiederhergestellten Warnungen stehen in deren Dokumentation zur Verfügung.  
  
-   **#include: Verwendung des Bezeichners '..' für das übergeordnete Verzeichnis im Pfadnamen** (betrifft nur „/Wall /WX“)  
  
     Frühere Versionen des Compilers haben die Verwendung des Bezeichners '..' für das übergeordnete Verzeichnis im Pfadnamen von  `#include` -Anweisungen nicht erkannt. Bei in dieser Weise erstelltem Code wird normalerweise die Absicht verfolgt, Header einzuschließen, die sich außerhalb des Projekts befinden, und dazu werden fälschlicherweise projektrelative Pfade verwendet. Bei diesem alten Verhalten ergab sich die Gefahr, dass das Programm möglicherweise mit Einschluss einer anderen als der vom Programmierer beabsichtigten Quelldatei compiliert wurde oder dass diese relativen Pfade nicht auf andere Buildumgebungen portiert werden konnten. Der Compiler erkennt jetzt in dieser Weise erstellten Code und benachrichtigt den Programmierer mit der optionalen Compilerwarnung C4464, sofern diese aktiviert ist.  
  
    ```Output  
    warning C4464: relative include path contains '..'  
    ```  
  
     Beispiel (vorher)  
  
    ```cpp  
    #include "..\headers\C4426.h"  // emits warning C4464  
    ```  
  
     Beispiel (nachher)  
  
    ```cpp  
    #include "C4426.h"  // add absolute path to 'headers\' to your project's include directories  
    ```  
  
     Darüber hinaus empfehlen wir, auch wenn der Compiler dazu keine spezifischen Diagnosemeldungen ausgibt, den Bezeichner ".." für das übergeordnete Verzeichnis beim Angeben der Includeverzeichnisse des Projekts nicht zu verwenden.  
  
-   **#pragma optimize() erstreckt sich über das Ende der Headerdatei hinaus** (betrifft nur „/Wall /WX“)  
  
     In früheren Versionen wurden Änderungen an den Optimierungseinstellungen nicht erkannt, die zum Escapen einer in einer Übersetzungseinheit eingeschlossenen Headerddatei dienen. Der Compiler erkennt jetzt in dieser Weise erstellten Code und setzt den Programmierer mit der optionalen Compilerwarnung C4426 von der Position des `#include`-Verstoßes in Kenntnis, sofern diese aktiviert ist. Diese Warnung wird nur ausgegeben, wenn die Änderungen im Konflikt mit den Optimierungseinstellungen stehen, die durch die Befehlszeilenargumente für den Compiler festgelegt wurden.  
  
    ```Output  
    warning C4426: optimization flags changed after including header, may be due to #pragma optimize()  
    ```  
  
     Beispiel (vorher)  
  
    ```cpp  
    // C4426.h  
    #pragma optimize("g", off)  
    ...  
    // C4426.h ends  
  
    // C4426.cpp  
    #include "C4426.h"  // warning C4426  
    ```  
  
     Beispiel (nachher)  
  
    ```cpp  
    // C4426.h  
    #pragma optimize("g", off)  
    ...  
    #pragma optimize("", on)  // restores optimization flags set via command-line arguments  
    // C4426.h ends  
  
    // C4426.cpp  
    #include "C4426.h"  
    ```  
  
-   **Nicht übereinstimmende Festlegung von „#pragma warning“(push)** und **„#pragma warning“(pop)** (betrifft nur „/Wall /WX“)  
  
     Frühere Versionen des Compilers konnten keine `#pragma warning(push)`-Statusänderungen erkennen, die in Kombination mit `#pragma warning(pop)`-Statusänderungen in einer anderen Quelldatei auftraten, was selten beabsichtigt ist. Dieses alte Verhalten brachte die Gefahr mit sich, dass das Programm mit anderen Warnungseinstellungen als den vom Programmierer vorgesehenen kompiliert wurde, was möglicherweise zu einem schlechten Laufzeitverhalten führt. Der Compiler erkennt jetzt auf diese Weise erstellten Code und setzt den Programmierer mit der optionalen Compilerwarnung C5031 von der Position der `#pragma warning(pop)`-Übereinstimmung in Kenntnis, sofern diese aktiviert ist. Diese Warnung enthält einen Hinweis, der auf den Speicherort der entsprechenden „#pragma warning(push)“ verweist.  
  
    ```Output  
    warning C5031: #pragma warning(pop): likely mismatch, popping warning state pushed in different file  
    ```  
  
     Beispiel (vorher)  
  
    ```cpp  
    // C5031_part1.h  
    #pragma warning(push)  
    #pragma warning(disable:####)  
    ...  
    // C5031_part1.h ends without #pragma warning(pop)  
  
    // C5031_part2.h  
    ...  
    #pragma warning(pop)  // pops a warning state not pushed in this source file   
    ...  
    // C5031_part1.h ends  
  
    // C5031.cpp  
    #include "C5031_part1.h" // leaves #pragma warning(push) 'dangling'  
    ...  
    #include "C5031_part2.h" // matches 'dangling' #pragma warning(push), resulting in warning C5031  
    ...  
  
    ```  
  
     Beispiel (nachher)  
  
    ```cpp  
    // C5031_part1.h  
    #pragma warning(push)  
    #pragma warning(disable:####)  
    ...  
    #pragma warning(pop)  // pops the warning state pushed in this source file  
    // C5031_part1.h ends without #pragma warning(pop)  
  
    // C5031_part2.h  
    #pragma warning(push)  // pushes the warning state pushed in this source file  
    #pragma warning(disable:####)  
    ...  
    #pragma warning(pop)  
    // C5031_part1.h ends  
  
    // C5031.cpp  
    #include "C5031_part1.h" // #pragma warning state changes are self-contained and independent of other source files or their #include order.  
    ...  
    #include "C5031_part2.h"  
    ...  
  
    ```  
  
     Wenngleich ungewöhnlich, wird Code mitunter absichtlich auf diese Weise geschrieben. Auf diese Weise erstellter Code ist empfindlich gegenüber Änderungen an der `#include`-Reihenfolge. Wir empfehlen, dass Quellcodedateien den Warnungsstatus nach Möglichkeit eigenständig verwalten sollten.  
  
-   **Nicht zugeordnete „#pragma warning“ (push)** (betrifft nur „/Wall /WX“)  
  
     Frühere Versionen des Compilers haben nicht zugeordnete `#pragma warning(push)` -Statusänderungen am Ende einer Übersetzungseinheit nicht erkannt. Der Compiler erkennt jetzt in dieser Weise erstellten Code und setzt den Programmierer mit der optionalen Compilerwarnung C5032 von der Position der nicht zugeordneten „#pragma warning“(push) in Kenntnis, sofern diese aktiviert ist. Diese Warnung wird nur ausgegeben, wenn in der Übersetzungseinheit keine Kompilierfehler auftreten.  
  
    ```Output  
    warning C5032: detected #pragma warning(push) with no corresponding #pragma warning(pop)  
    ```  
  
     Beispiel (vorher)  
  
    ```cpp  
    // C5032.h  
    #pragma warning(push)  
    #pragma warning(disable:####)  
    ...  
    // C5032.h ends without #pragma warning(pop)  
  
    // C5032.cpp  
    #include "C5032.h"  
    ...  
    // C5032.cpp ends -- the translation unit is completed without #pragma warning(pop), resulting in warning C5032 on line 1 of C5032.h  
    ```  
  
     Beispiel (nachher)  
  
    ```cpp  
    // C5032.h  
    #pragma warning(push)  
    #pragma warning(disable:####)  
    ...  
    #pragma warning(pop) // matches #pragma warning (push) on line 1  
    // C5032.h ends  
  
    // C5032.cpp  
    #include "C5032.h"  
    ...  
    // C5032.cpp ends -- the translation unit is completed without unmatched #pragma warning(push)  
    ```  
  
-   **Möglicherweise werden weitere Warnungen als Folge der verbesserten Statusnachverfolgung bei „#pragma warning“ angezeigt**  
  
     In früheren Versionen des Compilers wurden Statusänderungen bei „#pragma warning“ nicht hinreichend gut nachverfolgt, um alle beabsichtigten Warnungen auszugeben. Durch dieses Verhalten bestand die Gefahr, dass bestimmte Warnungen unter anderen als den vom Programmierer beabsichtigten Umständen effektiv unterdrückt wurden. Die Nachverfolgung des Status von „#pragma warning“ erfolgt nun stabiler – insbesondere im Zusammenhang mit „#pragma warning“-Statusänderungen in Vorlagen – und gibt optional die neuen Warnungen C5031 und C5032 aus, die den Programmierer bei der Suche nach unbeabsichtigter Verwendung von `#pragma warning(push)` und `#pragma warning(pop)`unterstützen sollen.  
  
     Als Ergebnis der verbesserten Nachverfolgung des Status von „#pragma warning“ können jetzt Warnungen ausgegeben werden, die früher fälschlicherweise unterdrückt wurden oder mit falsch identifizierten Problemen zusammenhingen.  
  
-   **Verbesserte Erkennung von unerreichbarem Code**  
  
     Änderungen an der C++-Standardbibliothek und eine im Vergleich mit früheren Versionen des Compilers verbesserte Möglichkeit zur Inlineausführung von Funktionsaufrufen ermöglichen dem Compiler jetzt unter Umständen den Nachweis, dass bestimmter Code unerreichbar ist. Dieses neue Verhalten kann zu neuen und häufiger ausgegebenen Instanzen von Warnung C4720 führen.  
  
    ```Output  
    warning C4720: unreachable code  
    ```  
  
     In vielen Fällen wird diese Warnung nur beim Kompilieren mit aktivierten Optimierungen ausgegeben, da bei den Optimierungen mehr Funktionsaufrufe inline erfolgen, redundanter Code eliminiert wird oder auf andere Weise die Möglichkeit geschaffen wird, bestimmten Code als unerreichbar zu erkennen. Nach unseren Beobachtungen treten neue Instanzen von Warnung C4720 häufig in Try/Catch-Blöcken auf, insbesondere in Verbindung mit [std::find](assetId:///std::find?qualifyHint=False&autoUpgrade=True).  
  
     Beispiel (vorher)  
  
    ```cpp  
    try   
    {   
        auto iter = std::find(v.begin(), v.end(), 5);   
    }   
    catch(...)   
    {   
        do_something();  // ok   
    }  
    ```  
  
     Beispiel (nachher)  
  
    ```cpp  
    try   
    {   
        auto iter = std::find(v.begin(), v.end(), 5);   
    }   
    catch(...)   
    {   
        do_something();  // warning C4702: unreachable code  
    }  
    ```  
  
##  <a name="VS_Update2"></a> Verbesserungen bei der Übereinstimmung mit Standards in Update 2  
  
-   **Zusätzliche Warnungen und Fehler können als Ergebnis der Teilunterstützung für den Ausdruck SFINAE ausgegeben werden**  
  
     In früheren Versionen des Compilers werden bestimmte Arten von Ausdrücken in `decltype`-Spezifizierern nicht analysiert, weil der Ausdruck SFINAE nicht unterstützt wird. Dieses alte Verhalten war falsch und entsprach nicht dem C++-Standard. Der Compiler analysiert diese Ausdrücke jetzt und hat aufgrund kontinuierlicher Konformitätsverbesserungen eine Teilunterstützung für den Ausdruck SFINAE. Daher gibt der Compiler jetzt Warnungen und Fehler aus, die er in Ausdrücken findet, die von früheren Versionen des Compilers nicht analysiert werden.  
  
     Wenn wegen dieses neuen Verhaltens ein `decltype`-Ausdruck analysiert wird, der einen Typ enthält, der noch nicht deklariert ist, gibt der Compiler den Compilerfehler C2039 aus.  
  
    ```Output  
    error C2039: 'type': is not a member of '`global namespace''  
    ```  
  
     Beispiel 1: Verwendung eines nicht deklarierten Typs (vorher)  
  
    ```cpp  
    struct s1  
    {  
      template <typename T>  
      auto f() -> decltype(s2<T>::type::f());  // error C2039  
  
      template<typename>  
      struct s2 {};  
    }  
    ```  
  
     Beispiel 1 (nachher)  
  
    ```cpp  
    struct s1  
    {  
      template <typename>  // forward declare s2struct s2;  
  
      template <typename T>  
      auto f() -> decltype(s2<T>::type::f());  
  
      template<typename>  
      struct s2 {};  
    }  
    ```  
  
     Wenn wegen dieses neuen Verhaltens ein `decltype`-Ausdruck analysiert wird, in dem das erforderliche Schlüsselwort `typename` für die Angabe fehlt, dass ein abhängiger Name ein Typ ist, gibt der Compiler die Compilerwarnung C4346 zusammen mit dem Compilerfehler C2923 aus.  
  
    ```Output  
    warning C4346: 'S2<T>::Type': dependent name is not a type  
    ```  
  
    ```Output  
    error C2923: 's1': 'S2<T>::Type' is not a valid template type argument for parameter 'T'  
    ```  
  
     Beispiel 2: Abhängiger Name ist kein Typ (vorher)  
  
    ```cpp  
    template <typename T>  
    struct s1  
    {  
      typedef T type;  
    };  
  
    template <typename T>  
    struct s2  
    {  
      typedef T type;  
    };  
  
    template <typename T>  
    T declval();  
  
    struct s  
    {  
      template <typename T>  
      auto f(T t) -> decltype(t(declval<S1<S2<T>::type>::type>()));  // warning C4346, error C2923  
    };  
    ```  
  
     Beispiel 2 (nachher)  
  
    ```cpp  
    template <typename T> struct s1 {...};  // as above  
    template <typename T> struct s2 {...};  // as above  
  
    template <typename T>  
    T declval();  
  
    struct s  
    {  
      template <typename T>  
      auto f(T t) -> decltype(t(declval<S1<typename S2<T>::type>::type>()));  
    };  
    ```  
  
-   `volatile` **Membervariablen verhindern implizit definierte Konstruktoren und Zuweisungsoperatoren**  
  
     In früheren Versionen des Compilers ist es für eine Klasse, die Membervariablen des Typs `volatile` hat, zulässig, dass Kopier-/Verschiebe-Standardkonstruktoren und Kopier-/Verschiebe-Standardzuweisungsoperatoren automatisch generiert werden. Dieses alte Verhalten war falsch und entsprach nicht dem C++-Standard. Der Compiler geht bei einer Klasse mit volatilen Membervariablen davon aus, dass sie nicht triviale Konstruktions- und Zuweisungsoperatoren hat. Dies verhindert, dass Standardimplementierungen dieser Operatoren automatisch generiert werden.  Ist eine solche Klasse ein Member einer Union (oder einer anonymen Union innerhalb einer Klasse), werden Kopier-/Verschiebekonstruktoren und Kopier-/Verschiebezuweisungsoperatoren der Union (oder die Klasse, die die anonyme Union enthält) implizit als gelöscht definiert. Wird versucht, die Union (oder die Klasse, die die anonyme Union enthält) zu erstellen oder zu kopieren, ohne sie explizit zu definieren, tritt ein Fehler auf, und der Compiler gibt daher den Compilerfehler C2280 aus.  
  
    ```Output  
    error C2280: 'B::B(const B &)': attempting to reference a deleted function  
    ```  
  
     Beispiel (vorher)  
  
    ```cpp  
    struct A  
    {  
      volatile int i;  
      volatile int j;  
    };  
  
    extern A* pa;  
  
    struct B  
    {  
      union  
      {  
        A a;  
        int i;  
      };  
    };  
  
    B b1 {*pa};  
    B b2 (b1);  // error C2280  
    ```  
  
     Beispiel (nachher)  
  
    ```cpp  
    struct A  
    {  
      int i;int j;  
    };  
  
    extern volatile A* pa;  
  
    A getA()  // returns an A instance copied from contents of pa  
    {  
      A a;  
      a.i = pa->i;  
      a.j = pa->j;  
      return a;  
    }  
  
    struct B;  // as above  
  
    B b1 {GetA()};  
    B b2 (b1);  // error C2280  
    ```  
  
-   **Statische Memberfunktionen unterstützen keine CV-Qualifizierer.**  
  
     In früheren Versionen von Visual C++ 2015 ist es zulässig, dass statische Memberfunktionen CV-Qualifizierer haben. Dieses Verhalten ist durch einen Rückschritt in Visual C++ 2015 und Visual C++ 2015 Update 1 begründet. Visual C++ 2013 und frühere Versionen von Visual C++ weisen Code zurück, der in dieser Weise geschrieben ist. Das Verhalten von Visual C++ 2015 und Visual C++ 2015 Update 1 ist falsch und entspricht nicht dem C++-Standard.  Visual Studio 2015 Update 2 weist Code, der in dieser Weise geschrieben ist, zurück und gibt stattdessen den Compilerfehler C2511 aus.  
  
    ```Output  
    error C2511: 'void A::func(void) const': overloaded member function not found in 'A'  
    ```  
  
     Beispiel (vorher)  
  
    ```  
    struct A  
    {  
      static void func();  
    };  
  
    void A::func() const {}  // C2511  
  
    ```  
  
     Beispiel (nachher)  
  
    ```  
    struct A  
    {  
      static void func();  
    };  
  
    void A::func() {}  // removed const  
  
    ```  
  
-   **Vorwärtsdeklaration einer Enumeration ist in WinRT-Code nicht zulässig** (betrifft nur /Zw)  
  
     In Code, der für Windows-Runtime (WinRT) kompiliert wird, darf es keine Vorwärtsdeklarationen von `enum`-Typen geben. Dies ist ähnlich damit, wenn verwalteter C++-Code für .NET Framework mit dem Compilerschalter /clr kompiliert wird. Dieses Verhalten stellt sicher, dass die Größe einer Enumeration immer bekannt ist und richtig in das WinRT-Typsystem projiziert werden kann. Der Compiler lehnt in dieser Weise geschriebenen Code ab und gibt den Compilerfehler C2599 zusammen mit dem Compilerfehler C3197 aus.  
  
    ```Output  
    error C2599: 'CustomEnum': the forward declaration of a WinRT enum is not allowed  
    ```  
  
    ```Output  
    error C3197: 'public': can only be used in definitions  
    ```  
  
     Beispiel (vorher)  
  
    ```cpp  
    namespace A {  
      public enum class CustomEnum: int32;  // forward declaration; error C2599, error C3197  
    }  
  
    namespace A {  
      public enum class CustomEnum: int32  
      {  
        Value1  
      };  
    }  
  
    public ref class Component sealed  
    {  
    public:  
      CustomEnum f()  
      {  
        return CustomEnum::Value1;  
      }  
    };  
    ```  
  
     Beispiel (nachher)  
  
    ```cpp  
              // forward declaration of CustomEnum removed  
  
    namespace A {  
      public enum class CustomEnum: int32  
      {  
        Value1  
      };  
    }  
  
    public ref class Component sealed  
    {  
    public:  
      CustomEnum f()  
      {  
        return CustomEnum::Value1;  
      }  
    };  
    ```  
  
-   **new- oder delete-Funktionen eines überladenen Nicht-Memberoperators dürfen nicht inline deklariert werden** (Level 1 (/W1) standardmäßig aktiviert)  
  
     Frühere Versionen des Compilers geben keine Warnung aus, wenn new- oder delete-Funktionen eines Nicht-Memberoperators inline deklariert werden. In dieser Weise geschriebener Code ist nicht wohlgeformt (keine Diagnose erforderlich) und kann zu Arbeitsspeicherproblemen führen, die sich aus nicht zusammengehörigen new- und delete-Operatoren ergeben (insbesondere bei Verwendung von Zuordnungsaufhebung mit Größenangabe), die sich nur schwer diagnostizieren lassen.   Der Compiler gibt jetzt die Warnung C4595 aus, um Code erkennen zu können, der in dieser Weise geschrieben ist.  
  
    ```Output  
    warning C4595: 'operator new': non-member operator new or delete functions may not be declared inline  
    ```  
  
     Beispiel (vorher)  
  
    ```cpp  
              inline void* operator new(size_t sz)  // warning C4595  
    {  
      ...  
    }  
    ```  
  
     Beispiel (nachher)  
  
    ```cpp  
              void* operator new(size_t sz)  // removed inline  
    {  
      ...  
    }  
    ```  
  
     Ein Korrigieren von Code, der in dieser Weise geschrieben ist, kann erfordern, dass die Operatordefinitionen aus einer Headerdatei in eine entsprechende Quelldatei verschoben werden.  
  
##  <a name="VS_Update3"></a> Verbesserungen bei der Übereinstimmung mit Standards in Update 3  
  
-   **std::is_convertable erkennt jetzt Selbstzuweisung** (Standardbibliothek)  
  
     Frühere Versionen des Typmerkmals `std::is_convertable` erkannten die Selbstzuweisung eines Klassentyps nicht ordnungsgemäß, wenn der Kopierkonstruktor gelöscht wurde oder privat war. Jetzt ist `std::is_convertable<>::value` bei Anwendung auf einen Klassentyp mit einem gelöschten oder privaten Kopierkonstruktor richtig auf `false` festgelegt.  
  
     Dieser Änderung ist keine Compilerdiagnose zugeordnet.  
  
     Beispiel  
  
    ```cpp  
    #include <type_traits>  
  
    class X1  
    {  
    public:  
        X1(const X1&) = delete;  
    };  
  
    class X2  
    {  
    private:  
        X2(const X2&);  
    };  
  
    static_assert(std::is_convertible<X1&, X1>::value, "BOOM");static_assert(std::is_convertible<X2&, X2>::value, "BOOM");  
    ```  
  
     In früheren Versionen von Visual C++ wurden die statischen Assertionen unten in diesem Beispiel übergeben, da `std::is_convertable<>::value` fälschlicherweise auf `true` festgelegt war. Jetzt ist `std::is_convertable<>::value` richtig auf `false` festgelegt, was einen Fehler der statischen Assertionen verursacht.  
  
-   **Als Standard festgelegte und gelöschte triviale Kopier- und Verschiebekonstruktoren beachten Zugriffsspezifizierer**  
  
     In früheren Versionen des Compilers wurden die Zugriffsspezifizierer von als Standard festgelegten und gelöschten trivialen Kopier- und Verschiebekonstruktoren nicht geprüft, ehe ihr Aufrufen erlaubt wurde. Dieses alte Verhalten war falsch und entsprach nicht dem C++-Standard. Durch dieses alte Verhalten entstand in einigen Fällen die Gefahr der stummen Erzeugung von ungültigem Code, was zu unvorhersehbarem Laufzeitverhalten führt. Der Compiler prüft jetzt den Zugriffsspezifizierer von als Standard festgelegten und gelöschten trivialen Kopier- und Verschiebekonstruktoren, um zu bestimmen, ob diese aufgerufen werden können. Falls nicht, gibt der Compiler die Warnung C2248 aus.  
  
    ```Output  
    error C2248: 'S::S' cannot access private member declared in class 'S'  
    ```  
  
     Beispiel (vorher)  
  
    ```cpp  
    class S {  
    public:  
           S() = default;  
    private:  
        S(const S&) = default;  
    };  
  
    void f(S);  // pass S by value  
  
    int main()  
    {  
        S s;  
        f(s);  // error C2248, can't invoke private copy constructor  
    }  
    ```  
  
     Beispiel (nachher)  
  
    ```cpp  
    class S {  
    public:  
           S() = default;  
    private:  
        S(const S&) = default;  
    };  
  
    void f(const S&);  // pass S by reference  
  
    int main()  
    {  
        S s;  
        f(s);  
    }  
    ```  
  
-   **Attributierter ATL-Code veraltet** (Level 1 (/W1) standardmäßig EIN)  
  
     Frühere Versionen des Compilers haben attributierten ATL-Code unterstützt. In der nächsten Phase der Aufhebung der Unterstützung von attributiertem ATL-Code, die [in Visual C++ 2008 begann](https://msdn.microsoft.com/library/bb384632\(v=vs.90\).aspx), gilt attributierter ATL-Code nun als veraltet. Der Compiler gibt jetzt die Warnung C4467 aus, um diese Art von veraltetem Code erkennen zu können.  
  
    ```Output  
    warning C4467: Usage of ATL attributes is deprecated  
    ```  
  
     Wenn Sie attributierten ATL-Code bis zur Aufhebung der Unterstützung durch den Compiler weiter nutzen möchten, können Sie diese Warnung deaktivieren, indem Sie das Befehlszeilenargument `/Wv:18` oder `/wd4467` an den Compiler übergeben oder `#pragma warning(disable:4467)` Ihrem Quellcode hinzufügen.  
  
     Beispiel 1 (vorher)  
  
    ```cpp  
              [uuid("594382D9-44B0-461A-8DE3-E06A3E73C5EB")]  
    class A {};  
    ```  
  
     Beispiel 1 (nachher)  
  
    ```cpp  
    __declspec(uuid("594382D9-44B0-461A-8DE3-E06A3E73C5EB")) A {};  
  
    ```  
  
     Mitunter müssen oder möchten Sie ggf. eine IDL-Datei erstellen, um die Nutzung veralteter ATL-Attribute zu vermeiden (siehe den folgenden Beispielcode).  
  
     Beispiel 2 (vorher)  
  
    ```cpp  
    [emitidl];  
    [module(name="Foo")];  
  
    [object, local, uuid("9e66a290-4365-11d2-a997-00c04fa37ddb")]  
    __interface ICustom {  
        HRESULT Custom([in] long l, [out, retval] long *pLong);  
        [local] HRESULT CustomLocal([in] long l, [out, retval] long *pLong);  
    };  
  
    [coclass, appobject, uuid("9e66a294-4365-11d2-a997-00c04fa37ddb")]  
    class CFoo : public ICustom  
    {  
        // ...  
    };  
    ```  
  
     Erstellen Sie zunächst die IDL-Datei. Die generierte Datei „vc140.idl“ kann zum Abrufen einer „\*.idl“-Datei verwendet werden, die die Schnittstellen und Anmerkungen enthält.  
  
     Fügen Sie als Nächstes Ihrem Build einen MIDL-Schritt hinzu, um sicherzustellen, dass die C++-Schnittstellendefinitionen generiert werden.  
  
     Beispiel 2: IDL (nachher)  
  
    ```cpp  
    import "docobj.idl";  
  
    [  
        object,local,uuid(9e66a290-4365-11d2-a997-00c04fa37ddb)  
    ]  
  
    interface ICustom : IUnknown {  
        HRESULT  Custom([in] long l, [out,retval] long *pLong);  
        [local] HRESULT  CustomLocal([in] long l, [out,retval] long *pLong);  
    };  
  
    [ version(1.0), uuid(29079a2c-5f3f-3325-99a1-3ec9c40988bb) ]  
    library Foo  
    {  
        importlib("stdole2.tlb");  
        importlib("olepro32.dll");  
            [  
                version(1.0),  
                appobject,uuid(9e66a294-4365-11d2-a997-00c04fa37ddb)  
            ]  
  
        coclass CFoo {  
            interface ICustom;  
        };  
    }  
    ```  
  
     Verwenden Sie dann ATL direkt in der Implementierungsdatei (siehe den folgenden Beispielcode).  
  
     Beispiel 2: Implementierung (nachher)  
  
    ```cpp  
    #include <idl.header.h>  
    #include <atlbase.h>  
  
    class ATL_NO_VTABLE CFooImpl :  
        public ICustom,  
        public ATL::CComObjectRootEx<CComMultiThreadModel>  
    {  
    public:  
        BEGIN_COM_MAP(CFooImpl)  
        COM_INTERFACE_ENTRY(ICustom)  
        END_COM_MAP()  
    };  
    ```  
  
-   **Vorkompilierte Headerdateien (PCH) und nicht übereinstimmende #include-Direktiven** (wirkt sich nur auf /Wall /WX aus)  
  
     Frühere Version des Compilers haben bei Verwendung vorkompilierter Headerdateien (PCH) nicht übereinstimmende `#include`-Direktiven in Quelldateien zwischen `-Yc`- und `-Yu`-Kompilierungen akzeptiert. Auf diese Weise geschriebener Code wird vom Compiler nicht mehr akzeptiert.   Der Compiler gibt nun die Compilerwarnung CC4598 aus, um bei Verwenden von PCH-Dateien nicht übereinstimmende `#include`-Direktiven zu bestimmen.  
  
    ```Output  
    warning C4598: 'b.h': included header file specified for Ycc.h at position 2 does not match Yuc.h at that position  
    ```  
  
     Beispiel (vorher):  
  
     X.cpp (-Ycc.h)  
  
    ```cpp  
    #include "a.h"  
    #include "b.h"  
    #include "c.h"  
    ```  
  
     Z.cpp (-Yuc.h)  
  
    ```cpp  
    #include "b.h"  
    #include "a.h"  // mismatched order relative to X.cpp  
    #include "c.h"  
    ```  
  
     Beispiel (nachher)  
  
     X.cpp (-Ycc.h)  
  
    ```cpp  
    #include "a.h"  
    #include "b.h"   
    #include "c.h"  
    ```  
  
     Z.cpp (-Yuc.h)  
  
    ```cpp  
    #include "a.h"  
    #include "b.h" // matched order relative to X.cpp  
    #include "c.h"  
    ```  
  
-   **Vorkompilierte Headerdateien (PCH) und nicht übereinstimmende include-Verzeichnisse** (wirkt sich nur auf /Wall /WX aus)  
  
     Frühere Version des Compilers haben bei Verwendung vorkompilierter Headerdateien (PCH) nicht übereinstimmende Befehlszeilenargumente des Typs „include-Verzeichnis“ (`-I`) für den Compiler zwischen `-Yc`- und `-Yu`-Kompilierungen akzeptiert. Auf diese Weise geschriebener Code wird vom Compiler nicht mehr akzeptiert.   Der Compiler gibt nun die Compilerwarnung CC4599 aus, um bei Verwenden von PCH-Dateien nicht übereinstimmende Befehlszeilenargumente des Typs „include-Verzeichnis“ (`-I`) zu bestimmen.  
  
    ```Output  
    warning C4599: '-I..' : specified for Ycc.h at position 1 does not match Yuc.h at that position  
    ```  
  
     Beispiel (vorher)  
  
    ```ms-dos  
    cl /c /Wall /Ycc.h -I.. X.cpp  
    cl /c /Wall /Yuc.h Z.cpp  
    ```  
  
     Beispiel (nachher)  
  
    ```ms-dos  
    cl /c /Wall /Ycc.h -I.. X.cpp  
    cl /c /Wall /Yuc.h -I.. Z.cpp  
    ```
