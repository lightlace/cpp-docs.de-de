---
title: "Wichtige &#196;nderungen in Visual C++ 2015"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Wichtige Änderungen [C++]"
ms.assetid: b38385a9-a483-4de9-99a6-797488bc5110
caps.latest.revision: 124
caps.handback.revision: "117"
ms.author: "mblome"
manager: "ghogen"
---
# Wichtige &#196;nderungen in Visual C++ 2015
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie auf eine neue Version des Visual C\+\+\-Compilers aktualisieren, treten unter Umständen Kompilierungs\- und\/oder Laufzeitfehler im Code auf, der zuvor ordnungsgemäß kompiliert und ausgeführt wurde. Änderungen in der neuen Version, die solche Probleme verursachen, werden als *wichtige Änderungen* bezeichnet und werden in der Regel durch Änderungen im C\+\+\-Sprachenstandard, in den Funktionssignaturen oder im Layout von Objekten im Arbeitsspeicher erforderlich.  
  
 Um Laufzeitfehler zu vermeiden, die schwer zu erkennen und zu diagnostizieren sind, wird empfohlen, keine statischen Links mit den Binärdateien zu erstellen, die mit verschiedenen Versionen des Compilers kompiliert wurden. Stellen Sie beim Aktualisieren eines EXE\- oder DLL\-Projekts außerdem sicher, die Bibliotheken zu aktualisieren, mit denen es verknüpft ist. Wenn Sie CRT\- \(C Runtime\) oder STL\-Typen \(Standardvorlagenbibliothek\) verwenden, übergeben Sie sie nicht zwischen Binärdateien \(einschließlich DLLs\), die mit verschiedenen Versionen des Compilers kompiliert wurden. Weitere Informationen finden Sie unter [Potenzielle Fehler bei der Übergabe von CRT\-Objekten über DLL\-Grenzen](../c-runtime-library/potential-errors-passing-crt-objects-across-dll-boundaries.md).  
  
 Es wird außerdem empfohlen, niemals Code, der von einem bestimmten Layout abhängt, für ein Objekt zu schreiben, das keine COM\-Schnittstelle oder kein POD\-Objekt ist. Wenn Sie diesen Code schreiben, müssen Sie sicherstellen, dass er nach dem Upgrade funktioniert. Weitere Informationen finden Sie unter [Portabilität an ABI\-Grenzen](../cpp/portability-at-abi-boundaries-modern-cpp.md).  
  
 Der restliche Artikel beschreibt spezifische wichtige Änderungen in [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)], und die Begriffe „neues Verhalten“ und „jetzt“ in diesem Artikel beziehen sich auf diese Version. Die Begriffe „altes Verhalten“ und „davor“ beziehen sich auf Visual Studio 2013 und frühere Versionen. Weitere Informationen zu zusätzlichen Änderungen in Visual Studio 2015 Update 1 finden Sie unter [Wichtige Änderungen in Update 1](../misc/breaking-changes-in-visual-cpp-2015-update-1.md).  
  
1.  [Wichtige Compileränderungen](#BK_compiler)  
  
2.  [Wichtige Änderungen der C\-Laufzeitbibliothek \(CRT\)](#BK_CRT)  
  
3.  [Wichtige Änderungen der Standard\-C\+\+\-Bibliothek und der Standardvorlagenbibliothek \(STL\)](#BK_STL)  
  
4.  [Wichtige MFC\- und ATL\-Änderungen](#BK_MFC)  
  
5.  [Wichtige Concurrency Runtime\-Änderungen](#BK_ConcRT)  
  
##  <a name="BK_compiler"></a> Visual C\+\+\-Compiler  
  
-   \/Zc:forScope\-Option  
  
     Die Compileroption **\/Zc:forScope\-** ist veraltet und wird in der nächsten Version entfernt.  
  
    ```  
    Command line warning  D9035: option 'Zc:forScope-' has been deprecated and will be removed in a future release  
    ```  
  
     Die Option wurde in der Regel für nicht dem Standard entsprechenden Code verwendet, der Schleifenvariablen gemäß dem Standard nach dem Punkt verwendet, an dem diese den Gültigkeitsbereich verlassen sollten. Dies war nur dann erforderlich, wenn die Kompilierung mit der \/Za\-Option erfolgte. Ohne der \/Za\-Option war eine Schleifenvariable nach dem Ende der Schleife immer zulässig. Wenn die Einhaltung von Standards keine Rolle spielt \(z. B. wenn der Code nicht auf andere Compiler übertragbar ist\), können Sie die \/Za\-Option deaktivieren \(oder die Eigenschaft „Spracherweiterungen deaktivieren“ auf „Nein“ festlegen\). Wenn Sie übertragbaren Code schreiben möchten, der den Standards entspricht, sollten Sie den Code umschreiben, indem Sie die Deklaration der Variablen an eine Stelle außerhalb der Schleifen verschieben.  
  
    ```  
    // zc_forScope.cpp // compile with: /Zc:forScope- /Za // C2065 expected int main() { // Uncomment the following line to resolve. // int i; for (int i =0; i < 1; i++) ; i = 20;   // i has already gone out of scope under /Za }  
    ```  
  
-   **\/Zg \(Compileroption\)**  
  
     Die \/Zg\-Compileroption \(Funktionsprototypen generieren\) ist nicht mehr verfügbar. Diese Compileroption wurde zuvor als veraltet markiert.  
  
-   Sie können Komponententests nicht mehr mit C\+\+\/CLI über die Befehlszeile mit mstest.exe ausführen. Verwenden Sie stattdessen vstest.console.exe. Weitere Informationen finden Sie unter [Befehlszeilenoptionen für VSTest.Console.exe](../Topic/VSTest.Console.exe%20command-line%20options.md).  
  
-   **mutable\-Schlüsselwort**  
  
     Der `mutable`\-Speicherklassenspezifizierer ist nicht mehr an Positionen zulässig, wo beim Kompilieren zuvor ein Fehler aufgetreten ist. Der Compiler generiert nun den Fehler C2071 \(Ungültige Speicherklasse\). Gemäß dem Standard kann der mutable\-Spezifizierer nur auf Namen von Klassendatenmembern angewendet werden und kann nicht auf als konstant oder statisch deklarierte Namen sowie nicht auf Verweismember angewendet werden.  
  
     Beachten Sie z. B. folgenden Code:  
  
    ```  
    struct S { mutable int &r; };  
    ```  
  
     In früheren Versionen des Visual C\+\+\-Compilers war dies zulässig, jetzt generiert der Compiler jedoch den folgenden Fehler:  
  
    ```Output  
    Fehler C2071: „S::r“: ungültige Speicherklasse.  
    ```  
  
     Entfernen Sie einfach das redundante mutable\-Schlüsselwort, um den Fehler zu beheben.  
  
-   **char\_16\_t und char32\_t**  
  
     `char16_t` oder `char32_t` können nicht mehr als Aliase in typedef verwendet werden, da diese Typen nun als integrierte Typen behandelt werden. Bisher war es üblich, dass Benutzer und Bibliothekenautoren char16\_t und char32\_t als Aliase von unit16\_t und uint32\_t definiert haben.  
  
    ```  
    #include <cstdint> typedef uint16_t char16_t; //C2628 typedef uint32_t char32_t; //C2628 int main(int argc, char* argv[]) { uint16_t x = 1; uint32_t y = 2; char16_t a = x; char32_t b = y; return 0; }  
    ```  
  
     Entfernen Sie zum Aktualisieren des Codes die typedef\-Deklarationen und benennen Sie andere Bezeichner um, die mit diesen Namen in Konflikt stehen.  
  
-   **Nichttyp\-Vorlagenparameter**  
  
     Bestimmter Code mit Nichttyp\-Vorlagenparametern wird auf Typkompatibilität korrekt geprüft, wenn Sie explizite Vorlagenargumente bereitstellen. Der folgende Code wurde z. B. ohne Fehler in früheren Versionen von Visual C\+\+ kompiliert.  
  
    ```  
    struct S1 { void f(int); void f(int, int); }; struct S2 { template <class C, void (C::*Function)(int) const> void f() {} }; void f() { S2 s2; s2.f<S1, &S1::f>(); }  
  
    ```  
  
     Der aktuelle Compiler generiert ordnungsgemäß einen Fehler, da der Typ des Vorlagenparameters nicht mit dem Vorlagenargument übereinstimmt \(der Parameter ist ein Zeiger auf einen konstanten Member, die f\-Funktion ist jedoch nicht konstant\):  
  
    ```Output  
    Fehler C2893: Fehler beim Spezialisieren der Funktionsvorlage „void S2::f(void)“ Hinweis: Mit den folgenden Vorlagenargumenten: „C=S1“ Hinweis: „C=S1“ Hinweis: „Function=S1::f“  
    ```  
  
     Stellen Sie zum Beheben dieses Fehlers im Code sicher, dass der Typ des verwendeten Vorlagenarguments mit dem deklarierten Typ des Vorlagenparameters übereinstimmt.  
  
-   **\_\_declspec\(align\)**  
  
     Der Compiler lässt `__declspec(align)` in Funktionen nicht mehr zu. Dies wurde bisher ignoriert, nun wird jedoch ein Compilerfehler generiert.  
  
    ```  
    error C3323: 'alignas' and '__declspec(align)' are not allowed on function declarations  
    ```  
  
     Entfernen Sie zum Beheben dieses Problems `__declspec(align)` aus der Funktionsdeklaration. Da dies keine Auswirkungen hatte, ändert sich durch das Entfernen nichts.  
  
-   **Ausnahmebehandlung**  
  
     Es gibt eine Reihe von Änderungen bei der Ausnahmebehandlung. Ausnahmeobjekte müssen kopiert oder verschoben werden können. Der folgende Code wurde [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)] kompiliert, kann jedoch in [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)] nicht kompiliert werden:  
  
    ```  
    struct S { public: S(); private: S(const S &); }; int main() { throw S(); // error }  
  
    ```  
  
     Das Problem besteht darin, dass der Kopierkonstruktor privat ist. Somit kann das Objekt nicht während des normalen Betriebs der Ausnahmebehandlung kopiert werden. Das gleiche gilt, wenn der Kopierkonstruktor als `explicit` deklariert ist.  
  
    ```  
    struct S { S(); explicit S(const S &); }; int main() { throw S(); // error }  
  
    ```  
  
     Stellen Sie zum Aktualisieren des Codes sicher, dass der Kopierkonstruktor für Ihr Ausnahmeobjekt öffentlich und nicht als `explicit` deklariert ist.  
  
     Beim Abfangen einer Ausnahme nach Wert muss das Ausnahmeobjekt ebenfalls kopiert werden können. Der folgende Code wurde [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)] kompiliert, kann jedoch in [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)] nicht kompiliert werden:  
  
    ```  
    struct B { public: B(); private: B(const B &); }; struct D : public B { }; int main() { try { } catch (D d) // error { } }  
  
    ```  
  
     Sie können dieses Problem beheben, indem Sie das den Parametertyp für `catch` auf einen Verweis festlegen.  
  
    ```  
    catch(D& d) { }  
    ```  
  
-   **Zeichenfolgenliterale gefolgt von Makros**  
  
     Der Compiler unterstützt nun benutzerdefinierte Literale. Folglich werden Zeichenfolgenliterale, auf die Makros ohne dazwischenliegende Leerzeichen folgen, als benutzerdefinierte Literale interpretiert, was zu Fehlern oder unerwarteten Ergebnissen führen kann. In vorherigen Compilern wurde der beispielsweise der folgende Code erfolgreich kompiliert:  
  
    ```  
    #define _x "there" char* func() { return "hello"_x; } int main() { char * p = func(); return 0; }  
    ```  
  
     Der Compiler interpretierte dies als ein Zeichenfolgenliteral „Hello“ gefolgt von einem Makro, das um „there“ erweitert wird, und führte die zwei Zeichenfolgenliterale zu einer verketteten Zeichenfolge zusammen. In [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)] interpretiert der Compiler dies als ein benutzerdefiniertes Literal, aber da kein entsprechendes benutzerdefiniertes Literal \_x definiert ist, wird ein Fehler generiert.  
  
    ```  
    error C3688: invalid literal suffix '_x'; literal operator or literal operator template 'operator ""_x' not found note: Did you forget a space between the string literal and the prefix of the following string literal?  
  
    ```  
  
     Fügen Sie zur Behebung dieses Problems ein Leerzeichen zwischen das Zeichenfolgenliteral und das Makro ein.  
  
-   **Angrenzende Zeichenfolgenliterale**  
  
     Auf ähnliche Weise wurden angrenzende Zeichenfolgenliterale ohne Leerzeichen aufgrund von zugehörigen Änderungen in der Zeichenfolgenanalyse als eine verkettete Zeichenfolge in den vorherigen Versionen von Visual C\+\+ interpretiert. In [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)] müssen Sie ein Leerzeichen zwischen den beiden Zeichenfolgen hinzufügen. Der folgende Code muss z. B. geändert werden:  
  
    ```  
    char * str = "abc""def";  
    ```  
  
     Fügen Sie einfach ein Leerzeichen zwischen den beiden Zeichenfolgen hinzu.  
  
    ```  
    char * str = "abc" "def";  
    ```  
  
-   **Platzierungsoperatoren „new“ und „delete“**  
  
     An dem delete\-Operator wurde eine Änderung vorgenommen, damit er den C\+\+14\-Standard entspricht. Detaillierte Informationen zur Standardänderung finden Sie unter [Aufhebung der Zuordnung mit C\+\+\-Größeninformationen](http://isocpp.org/files/papers/n3778.html). Durch die Änderungen wird eine Form des globalen delete\-Operators hinzugefügt, der einen Größenparameter erfordert. Eine wichtige Änderung ist, dass wenn Sie zuvor einen delete\-Operator mit der gleichen Signatur verwendet haben \(damit dieser einem Platzierungsoperator „new“ entspricht\) nun ein Compilerfehler geniert wird, nämlich C2956. Dieser tritt an der Stelle auf, an der der Plazierungsoperator „new“ verwendet wird, denn an dieser Stelle im Code versucht der Compiler einen entsprechenden delete\-Operator zu identifizieren.  
  
     Die `void operator delete(void *, size_t)`\-Funktion war ein Platzierungsoperator „delete“, die dem Platzierungsoperator „new“ der „void \* operator new\(size\_t, size\_t\)“\-Funktion in C\+\+11 entspricht. Durch die Aufhebung der Zuordnung mit C\+\+14\-Größeninformationen ist diese delete\-Funktion nun eine *gewöhnliche Funktion zum Aufheben der Zuordnung* \(globaler delete\-Operator\). Der Standard erfordert es, dass das Programm bei Verwendung eines Platzierungsoperators „new“, der eine entsprechenden delete\-Funktion sucht und eine gewöhnliche Funktion zum Aufheben der Zuordnung ermittelt, nicht ordnungsgemäß formatiert ist.  
  
     Angenommen der Code definiert einen Platzierungsoperator „new“ und einen Platzierungsoperator „delete“:  
  
    ```  
    void * operator new(std::size_t, std::size_t); void operator delete(void*, std::size_t) noexcept;  
  
    ```  
  
     Das Problem tritt aufgrund der Übereinstimmung zwischen den Funktionssignaturen im definierten Platzierungsoperator „delete“ und im neuen globalen delete\-Operator. Überlegen Sie, ob Sie einen anderen Typ als size\_t für alle Platzierungsoperatoren „new“ und „delete“ verwenden können.  Beachten Sie, dass der Typ der size\_t\-Typdefinition vom Compiler abhängig ist. In Visual C\+\+ ist dies eine Typdefinition für eine ganze Zahl ohne Vorzeichen. Eine gute Lösung hierfür stellt die Verwendung eines enumerierten Typs wie die des folgenden dar:  
  
    ```  
    enum class my_type : size_t {};  
  
    ```  
  
     Ändern Sie anschließend die Definition der Platzierungsoperatoren „new“ und „delete“, um diesen Typ als zweites Argument anstelle von size\_t zu verwenden. Sie müssen auch die Aufrufe des Platzierungsoperators „new“ aktualisieren, um den neuen Typ \(z. B. den ganzzahligen Wert mithilfe von `static_cast<my_type>` zu konvertieren\) zu übergeben und die Definition von „new“ und „delete“ so aktualisieren, dass dieser wieder in den ganzzahligen Typ umgewandelt wird. Dazu müssen Sie keine Enumeration verwenden. Ein Klassentyp mit einem size\_t\-Member funktioniert ebenfalls.  
  
     Eine alternative Lösung stellt möglicherweise eine vollständige Eliminierung des new\-Platzierungsoperators dar. Wenn der Code mit dem new\-Platzierungsoperator einen Speicherpool implementiert, wobei das Platzierungsargument die Größe des zugeordneten oder gelöschten Objekts ist, dann ist die Funktion zum Aufheben der Zuordnung mit Größeninformationen möglicherweise zum Ersetzen des benutzerdefinierten Speicherpoolcodes geeignet, und Sie können stattdessen den eigenen delete\-Operator mit zwei Argumenten verwenden.  
  
     Wenn Sie Ihren Code nicht sofort aktualisieren möchten, können Sie mit der Compileroption „\/Zc:sizedDealloc\-“ das alte Verhalten wiederherstellen. Wenn Sie diese Option verwenden, sind die delete\-Funktionen mit zwei Argumenten nicht mehr vorhanden und stehen nicht in Konflikt mit dem delete\-Platzierungsoperator.  
  
-   **Union\-Datenmember**  
  
     Union\-Datenmember dürfen über keine Verweistypen verfügen. Der folgende Code wird in [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)] erfolgreich kompiliert, geniert jedoch in [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)] einen Fehler.  
  
    ```  
    union U1 { const int i; }; union U2 { int &i; }; union U3 { struct {int &i;}; };  
    ```  
  
     Der oben genannte Code geniert die folgenden Fehler:  
  
    ```Output  
    test.cpp(67): Fehler C2625: „U2::i“: ungültiger Unionmember; Typ „int &“ ist ein Verweistyp. test.cpp(70): Fehler C2625: „U3::i“: ungültiger Unionmember; Typ „int &“ ist ein Verweistyp.  
    ```  
  
     Ändern Sie zur Behebung dieses Fehlers die Verweistypen in einen Zeiger oder einen Wert. Für die Änderung des Typs in einen Zeiger sind Änderungen im Code erforderlich, der das Union\-Feld verwendet. Durch die Änderung des Codes in einen Wert werden die in der Union gespeicherten Daten geändert, was Auswirkungen auf andere Felder hat, da Felder in Uniontypen den gleichen Speicher gemeinsam verwenden. Je nach Wertgröße kann dies ggf. auch die Größe der Union ändern.  
  
-   Anonyme Unions weisen nun eine größere Standardkonformität auf. Frühere Versionen des Compilers haben einen expliziten Konstruktor und Destruktor für anonyme Unions generiert. Diese werden in [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)] gelöscht.  
  
    ```  
    struct S { S(); }; union { struct { S s; }; } u; // C2280  
    ```  
  
     Der oben genannte Code geniert in [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)] die folgenden Fehler:  
  
    ```  
    error C2280: '<unnamed-type-u>::<unnamed-type-u>(void)': attempting to reference a deleted function note: compiler has generated '<unnamed-type-u>::<unnamed-type-u>' here  
    ```  
  
     Geben Sie zur Behebung dieses Fehlers eigene Definitionen des Konstruktors und\/oder des Destruktors an.  
  
    ```  
    struct S { // Provide a default constructor by adding an empty function body. S() {} }; union { struct { S s; }; } u;  
    ```  
  
-   **Unions mit anonymen Strukturen**  
  
     Zur Einhaltung des Standards wurde das Laufzeitverhalten für Member anonymer Strukturen in Unions geändert. Der Konstruktor für anonyme Strukturmember in einer Union wird nicht mehr implizit aufgerufen, wenn eine solche Union erstellt wird. Der Destruktor für anonyme Strukturmember in einer Union wird nicht mehr implizit aufgerufen, wenn die Union den Gültigkeitsbereich verlässt. Betrachten Sie den folgenden Code, in dem eine Union U eine anonyme Struktur mit einem Member enthält, der die Struktur S mit einem Destruktor darstellt.  
  
    ```  
    #include <stdio.h> struct S { S() { printf("Creating S\n"); } ~S(){ printf("Destroying S\n"); } }; union U { struct { S s; }; U() {} ~U(){} }; void f() { U u; // Destructor implicitly called here. } int main() { f(); char s[1024]; printf("Press any key.\n"); gets_s(s); return 0; }  
    ```  
  
     Der Konstruktor für S wird in [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)] immer dann aufgerufen, wenn die Union erstellt wird, und der Destruktor für S immer dann aufgerufen wird, wenn der Stapel für Funktion f bereinigt wird. In [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)] werden jedoch weder der Konstruktor noch der Destruktor aufgerufen. Der Compiler gibt eine Warnung zu dieser Verhaltensänderung aus.  
  
    ```Output  
    Warnung C4587: „U::s“: Verhaltensänderung: Konstruktor wird nicht mehr implizit aufgerufen. Warnung C4588: „U::s“: Verhaltensänderung: Destruktor wird nicht mehr implizit aufgerufen.  
    ```  
  
     Benennen Sie zum Wiederherstellen des ursprünglichen Verhaltens die anonyme Struktur. Das Laufzeitverhalten von nicht anonymen Strukturen ist von der Compilerversion unabhängig.  
  
    ```  
    #include <stdio.h> struct S { S() { printf("Creating S.\n"); } ~S() { printf("Destroying S\n"); } }; union U { struct { S s; } namedStruct; U() {} ~U() {} }; void f() { U u; } int main() { f(); char s[1024]; printf("Press any key.\n"); gets_s(s); return 0; }  
    ```  
  
     Verschieben Sie alternativ den Konstruktor\- und Destruktorcode in die neuen Funktionen, und fügen Sie diesen Funktionen aus der Konstruktor\- und Destruktorunion Aufrufe hinzu.  
  
    ```  
    #include <stdio.h> struct S { void Create() { printf("Creating S.\n"); } void Destroy() { printf("Destroying S\n"); } }; union U { struct { S s; }; U() { s.Create();  } ~U() { s.Destroy(); } }; void f() { U u; } int main() { f(); char s[1024]; printf("Press any key.\n"); gets_s(s); return 0; }  
    ```  
  
-   **Vorlagenauflösung**  
  
     Es wurden Änderungen an der Namensauflösung für Vorlagen vorgenommen. Bei Berücksichtigung der Kandidaten für eine Namensauflösung können potenzielle Namen in C\+\+ ggf. eine ungültige Vorlageninstanziierung erzeugen. Diese ungültigen Instanziierungen generieren in der Regel keine Comilerfehler – das SFINAE\-Prinzip \(Ersetzungsfehler sind keine Fehler\).  
  
     Wenn der Compiler jetzt von SFINAE zum Instanziieren der Spezialisierung einer Klassenvorlage aufgefordert wird, handelt es sich bei allen während dieses Prozesses aufgetretenen Fehler um Compilerfehler. In früheren Versionen hat der Compiler diese Fehler ignoriert. Beachten Sie z. B. folgenden Code:  
  
    ```  
    #include <type_traits> template<typename T> struct S { S() = default; S(const S&); S(S&&); template<typename U, typename = typename std::enable_if<std::is_base_of<T, U>::value>::type> S(S<U>&&); }; struct D; void f1() { S<D> s1; S<D> s2(s1); } struct B { }; struct D : public B { }; void f2() { S<D> s1; S<D> s2(s1); }  
  
    ```  
  
     Beim Kompilieren mit dem aktuellen Compiler tritt der folgende Fehler auf:  
  
    ```Output  
    type_traits(1110): Fehler C2139: „D“: Eine nicht definierte Klasse ist nicht als Argument für das systeminterne Typmerkmal „__is_base_of“ des Compilers zulässig. \t331.cpp(14): Hinweis: Siehe Deklaration von „D“. \t331.cpp(10): Hinweis: Siehe Verweis auf die mit [ T=D, U=D ] kompilierte Klassenvorlageninstanziierung „std::is_base_of<T,U>“.  
    ```  
  
     Dies liegt daran, dass die D\-Klasse zum Zeitpunkt des ersten Aufrufs von is\_base\_of noch nicht definiert war.  
  
     In diesem Fall besteht die Lösung darin, diese Typmerkmale nicht zu verwenden, bis die Klasse definiert wurde. Wenn Sie die Definitionen von B und D an den Anfang der Codedatei verschieben, wird der Fehler behoben. Überprüfen Sie, wenn sich die Definitionen in Headerdateien befinden, die Reihenfolge der Include\-Anweisungen für die Headerdateien, um sicherzustellen, dass alle Klassendefinitionen kompiliert werden, bevor die problematischen Vorlagen verwendet werden.  
  
-   **Kopierkonstruktoren**  
  
     In [!INCLUDE[vs_dev12](../atl-mfc-shared/includes/vs_dev12_md.md)] und [!INCLUDE[vs_dev14](../ide/includes/vs_dev14_md.md)] generiert der Compiler einen Kopierkonstruktor für eine Klasse, die über einen benutzerdefinierten Bewegungskonstruktor jedoch keinen benutzerdefinierten Kopierkontruktor verfügt. In Dev14 wird dieser implizit generierte Kopierkonstruktor ebenfalls als „\= delete“ gekennzeichnet.  
  
##  <a name="BK_CRT"></a> C Runtime Library \(CRT\)  
  
### Allgemeine Änderungen  
  
-   **Umgestaltete Binärdateien**  
  
     Die CRT\-Bibliothek wurde in zwei verschiedenen Binärdateien umgestaltet, eine Universal CRT \(ucrtbase\), die den Großteil der Standardfunkionen enthält, und eine VC\-Laufzeitbibliothek \(vcruntime140\) mit complilergebundenen Funktionen wie Ausnahmebehandlung und systeminterne Funktionen. Wenn Sie die standardmäßigen Projekteinstellungen verwenden, sind Sie von dieser Änderung nicht betroffen, da der Linker automatisch die neuen Standardbibliotheken verwendet. Wenn Sie die **Linker**\-Eigenschaft **Alle Standardbibliotheken ignorieren** des Projekts auf **Ja** festgelegt haben oder die \/NODEFAULTLIB\-Linkeroption in der Befehlszeile verwenden, müssen Sie die Liste der Bibliotheken \(in der Eigenschaft **Zusätzliche Abhängigkeiten**\) so aktualisieren, dass sie die neuen umgestalteten Bibliotheken enthält. Ersetzen Sie die alte CRT\-Bibliothek \(libcmt.lib, libcmtd.lib, msvcrt.lib, msvcrtd.lib\) mit den entsprechenden umgestalteten Bibliotheken. Für jede der beiden umgestalteten Bibliotheken gibt es eine statische \(.lib\) und eine dynamische \(.dll\) Version sowie endgültige \(ohne Suffix\) und Debugversionen \(mit dem Suffix „d“\). Die dynamischen Versionen haben eine Importbibliothek, mit der eine Verknüpfung erstellt wird. Die zwei umgestalteten Bibliotheken sind Universal CRT, insbesondere ucrtbase.dll oder .lib, ucrtbased.dll oder .lib, und die VC\-Laufzeitbibliothek, libvcruntime.lib, libvcruntime.dll, libvcruntimed.lib und libvcruntimed.dll. Siehe [CRT\-Bibliotheksfunktionen](../c-runtime-library/crt-library-features.md).  
  
### \<locale.h\>  
  
-   **localeconv**  
  
     Die in locale.h deklarierte [localeconv](../c-runtime-library/reference/localeconv.md)\-Funktion funktioniert nun ordnungsgemäß, wenn [threadspezifisches Gebietsschema](../parallel/multithreading-and-locales.md) aktiviert ist. In früheren Versionen der Bibliothek hat diese Funktion die iconv\-Daten für das globale Gebietsschema zurückgegeben statt den für das Threadgebietsschema.  
  
     Bei der Verwendung des threadspezifischen Schemas sollten Sie localeconv darauf prüfen, ob der Code annimmt, dass lconv\-Daten für das globale Gebietsschema zurückgegeben werden und dies entsprechend anpassen.  
  
### \<math.h\>  
  
-   **C\+\+\-Überladungen der math\-Bibliotheksfunktionen**  
  
     In früheren Versionen wurden einige, jedoch nicht alle, Überladungen für die math\-Bibliotheksfunktionen in \<math.h\> definiert. Die verbleibenden Überladungen wurden in \<cmath\> definiert, sodass alle Überladungen abgerufen wurden, die zum Einschließen des Headers \<cmath\> erforderlich waren. Dies führte zu Problemen mit der Auflösung von Funktionsüberladungen im Code, die nur \<math.h\> eingeschlossen haben. Alle C\+\+\-Überladungen wurden nun aus \<math.h\> entfernt und sind nur in \<cmath\> vorhanden.  
  
     Fügen Sie zur Behebung dieser Art von Problemen \<cmath\> ein, um alle Deklarationen von aus \<math.h\> entfernten Funktionen abzurufen. In der folgenden Tabelle werden die verschobenen Funktionen aufgeführt.  
  
     Funktionen, die verschoben wurden:  
  
    1.  double abs\(double\) und float abs\(float\)  
  
    2.  double pow\(double, int\), float pow\(float, float\), float pow\(float, int\), long double pow\(long double, long double\), long double pow\(long double, int\)  
  
    3.  float\- und long double\-Versionen von floating point\-Funktionen acos, acosh, asin, asinh, atan, atanh, atan2, cbrt, ceil, copysign, cos, cosh, erf, erfc, exp, exp2, expm1, fabs, fdim, floor, fma, fmax, fmin, fmod, frexp, hypot, ilogb, ldexp, lgamma, llrint, llround, log, log10, log1p, log2, lrint, lround, modf, nearbyint, nextafter, nexttoward, remainder, remquo, rint, round, scalbln, scalbn, sin, sinh, sqrt, tan, tanh, tgamma, trunc  
  
     Wenn Sie über Code verfügen, der abs mit einem Gleitkommatyp verwendet, der nur den math.h\-Header enthält, sind Gleitkommaversionen nicht mehr verfügbar, sodass der Aufruf, auch mit einem Gleitkommaargument, zu abs\(int\) aufgelöst wird. Dadurch wird der folgende Fehler generiert:  
  
    ```Output  
    Warnung C4244: „Argument“: Konvertierung von „float“ in „int“, möglicher Datenverlust.  
    ```  
  
     Ersetzen Sie zur Behebung dieses Problems den Aufruf von abs mit einer Gleitkommaversion von abs, z. B. bei einem doppelten Argument mit fabs oder bei einem Gleitkommaargument mit fabsf, oder fügen Sie den cmath\-Header ein, und verwenden Sie abs.  
  
-   **Gletkommakonformität**  
  
     Viele an der math\-Bibliothek vorgenommenen Änderungen wurden zur Verbesserung der Konformität mit den im Anhang F enthaltenen IEEE\-754\- und C11\-Spezifikationen in Bezug auf Eingaben bei Sonderfällen wie NaN\- und unendliche Werte. Stille NaN\-Eingaben, die in früheren Bibliotheksversionen häufig als Fehler behandelt wurden, werden z. B. nicht mehr als Fehler behandelt. Weitere Informationen finden Sie unter [IEEE 754\-Standard](http://grouper.ieee.org/groups/754) und Anhang F des [C11\-Standards](http://www.iso-9899.info/wiki/The_Standard).  
  
     Diese Änderungen führen nicht zu Kompilierungsfehlern, können jedoch dazu führen, dass Programme ggf. ein anderes und standardkonformeres Verhalten aufweisen.  
  
-   **FLT\_ROUNDS**  
  
     Das FLT\_ROUNDS\-Makro wurde in Visual Studio 2013 auf einen konstanten Ausdruck erweitert, was nicht korrekt war, da der Rundungsmodus, z. B. beim Aufruf von fesetround, zur Laufzeit konfigurierbar ist. Das FLT\_ROUNDS\-Makro ist jetzt dynamisch und spiegelt ordnungsgemäß den aktuellen Rundungsmodus wider.  
  
### \<new\> und \<new.h\>  
  
-   **Operatoren „new“ und „delete“**  
  
     In früheren Bibliotheksversionen wurden die in der Implementierung definierten Operatorfunktionen „new“ und „delete“ aus der DLL\-Datei der Laufzeitbibliothek \(z. B. msvcr120.dll\) exportiert. Dieser Operatorfunktionen sind immer statisch mit Ihren Binärdateien verknüpft, selbst wenn DLL\-Dateien der Laufzeitbibliothek verwendet werden.  
  
     Es handelt sich dabei nicht um eine wichtige Änderung für systemeigenen oder gemischten Code \(\/clr\), sondern eher für Code, der als [\/clr: pure](../build/reference/clr-common-language-runtime-compilation.md) kompiliert wird, denn diese Änderung kann dann zu einem Fehler beim Kompilieren führen. Wenn Sie Code als \/clr:pure kompilieren, müssen Sie möglicherweise „\#include \<new\>“ oder „\#include \< new.h \>“ hinzufügen, um Buildfehler aufgrund dieser Änderung zu umgehen. Beachten Sie, dass \/clr:pure in [!INCLUDE[vs_dev14](../ide/includes/vs_dev14_md.md)] veraltet ist und in zukünftigen Versionen ggf. entfernt wird.  
  
### \<process.h\>  
  
-   **\_beginthread und \_beginthreadex**  
  
     Die [\_beginthread](../c-runtime-library/reference/beginthread-beginthreadex.md)\- und [\_beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md)\-Funktionen enthalten jetzt einen Verweis auf das Modul, in dem die Threadprozedur für die Dauer des Threads definiert wird. Dadurch wird sichergestellt, dass Module nicht entladen werden, bis ein Thread vollständig ausgeführt wurde.  
  
### \<stdarg.h\>  
  
-   **va\_start und Verweistypen**  
  
     Beim Kompilieren von C\+\+\-Code prüft [va\_start](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md) nun zur Kompilierzeit, dass das übergebene Argument kein Verweistyp ist. Verweistyp\-Argumente sind gemäß dem C\+\+\-Standard nicht zulässig.  
  
### \<stdio.h\> und \<conio.h\>  
  
-   **Die printf\- und scanf\-Funktionsreihe werden nun inline definiert.**  
  
     Die Definitionen aller printf und scanf\-Funktionen wurden nun in \<stdio.h\>, \<conio.h\> und andere CRT\-Header verschoben. Dies ist eine wichtige Änderung, die zu einem Linkerfehler \(LNK2019, nicht aufgelöstes externes Symbol\) für alle Programme führt, die diese Funktionen ohne die entsprechenden CRT\-Header lokal deklariert haben. Sie sollten nach Möglichkeit den Code um die CRT\-Header \(d. h. \#include \<stdio.h\>\) und die Inlinefunktionen ergänzen. Wenn Sie diese Headerdateien nicht zu Ihrem Code hinzufügen möchten, können Sie alternativ eine Bibliothek zur Linkereingabe, legacy\_stdio\_definitions.lib, hinzufügen.  
  
     Öffnen Sie zum Hinzufügen dieser Bibliothek zu Ihrer Linkereingabe in IDE das Kontextmenü für den Projektknoten, wählen Sie **Eigenschaften**, wählen Sie dann im Dialogfeld **ProjekteigenschaftenLinker** aus, und fügen Sie in **Linkereingabe** legacy\_stdio\_definitions.lib zur durch Semikolons getrennter Liste hinzu.  
  
     Wenn Ihr Projekt mit statischen Bibliotheken verknüpft ist, die mit einer früheren Visual C\+\+\-Version als 2015 kompiliert wurden, meldet der Linker möglicherweise ein nicht aufgelöstes externes Symbol. Diese Fehler verweisen möglicherweise auf interne stdio\-Definitionen für \_iob, \_iob\_func oder verknüpfte Importe für bestimmte stdio\-Funktionen in der Form von \_imp\_\*. Microsoft empfiehlt, alle statischen Bibliotheken mit der neuesten Version von Visual C\+\+\-Compiler und Bibliotheken zu kompilieren, wenn Sie ein Upgrade für ein Projekt durchführen. Wenn die Bibliothek eine Drittanbieterbibliothek ohne verfügbare Quelle ist, sollten Sie entweder eine aktualisierte Binärdatei vom Drittanbieter anfordern oder die Verwendung dieser Bibliothek in einer separaten DLL kapseln, die Sie mit einer älteren Version von Visual C\+\+\-Compiler und Bibliotheken kompilieren.  
  
    > [!WARNING]
    >  Wenn Sie eine Verknüpfung mit Windows SDK 8.1 oder früher erstellen, tritt ggf. der Fehler „nicht aufgelöstes externes Symbol“ auf. Fügen Sie zur Behebung dieses Fehlers in diesem Fall legacy\_stdio\_definitions.lib zu der Linkerausgabe wie bereits beschrieben hinzu.  
  
     Um nicht aufgelöste Symbolfehler zu beheben, können Sie mit [dumpbin.exe](../build/reference/dumpbin-reference.md) versuchen, die in einer Binärdatei definierten Symbole zu überprüfen. Verwenden Sie zum Anzeigen der in einer Bibliothek definierten Symbole die folgende Befehlszeile.  
  
    ```  
    dumpbin.exe /LINKERMEMBER somelibrary.lib  
    ```  
  
-   **gets und \_getws**  
  
     Die [gets](../c-runtime-library/gets-getws.md)\- und [\_getws](../c-runtime-library/gets-getws.md)\-Funktionen wurden entfernt. Die gets\-Funktion wurde aus der C\-Standardbibliothek in C11 entfernt, da keine sichere Verwendung dieser Funktion gewährleistet werden kann. Bei der \_getws\-Funktion handelte es sich um eine Microsoft\-Erweiterung, die der gets\-Funktion für Breitzeichenfolgen entsprach. Alternativen zu dieser Funktionen stellen [fgets](../c-runtime-library/reference/fgets-fgetws.md), [fgetws](../c-runtime-library/reference/fgets-fgetws.md), [gets\_s](../c-runtime-library/reference/gets-s-getws-s.md) und [\_getws\_s](../c-runtime-library/reference/gets-s-getws-s.md) dar.  
  
-   **\_cgets und \_cgetws**  
  
     Die [cets](../c-runtime-library/cgets-cgetws.md)\- und [\_cgetws](../c-runtime-library/cgets-cgetws.md)\-Funktionen wurden entfernt. Alternativen zu diesen Funktionen stellen [\_cgets\_s](../c-runtime-library/reference/cgets-s-cgetws-s.md) und [\_cgetws\_s](../c-runtime-library/reference/cgets-s-cgetws-s.md) dar.  
  
-   **Formatierung von unendlichen und NaN\-Werten**  
  
     In früheren Versionen wurden unendliche und NaN\-Werte mit einem Satz Visual C\+\+\-spezifischer Sentinelzeichenfolgen formatiert.  
  
    -   Unendlich: 1.\#INF  
  
    -   Stiller NaN: 1. \#QNAN  
  
    -   Signaling\-NaN: 1.\#SNAN  
  
    -   Unbestimmter NaN: 1. \#IND  
  
     Allen diesen Werte konnte ein Vorzeichen vorangestellt werden und sie wurden möglicherweise je nach Feldbreite und Genauigkeit unterschiedlich formatiert \(z. B. mit ungewöhnlichen Effekten, z. B. würde die Funktion „printf\("%.2f\\n", INFINITY\)“ „1.\#J“ ausgeben, da \#INF auf zwei Stellen „gerundet“ werden würde\). In C99 wurden neue Anforderungen an die Formatierung von unendlichen und NaN\-Werten eingeführt. Die Visual C\+\+\-Implementierung entspricht nun diesen Anforderungen. Die neuen Zeichenfolgen lauten wie folgt:  
  
    -   Unendlich: inf  
  
    -   Stiller NaN: nan  
  
    -   Signaling\-NaN: nan\(snan\)  
  
    -   Unbestimmter NaN:nan\(ind\)  
  
     All diesen Werten kann ein Vorzeichen vorangestellt werden. Bei Verwendung eines Großbuchstaben\-Formatspezifizierers \(%F statt %f\) werden die Zeichenfolgen wie angefordert in Großbuchstaben ausgegeben \(INF statt inf\).  
  
     Die [scanf](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)\-Funktionen analysieren die neuen Zeichenfolgen so, dass über printf und scanf ein Roundtrip für diese ausgeführt wird.  
  
-   **Formatierung von Gleitkommawerten und Analyse**  
  
     Neue Formatierung von Gleitkommawerten und Analysealgorithmen wurden zur Verbesserung der Genauigkeit eingeführt. Diese Änderung wirkt sich auf die [printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)\- und [scanf](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)\-Funktionsreihen sowie auf Funktionen wie [strtod](../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md) aus.  
  
     Mit den alten Formatierungsalgorithmen wurde nur eine begrenzte Zifferanzahl erzeugt und die übrigen Dezimalstellen wurden mit 0 dargestellt. Dies ist in der Regel zum Generieren von Zeichenfolgen ausreichend, für die ein Roundtrip zum ursprünglichen Gleitkommawert durchgeführt wird. Es ist jedoch nicht zufriedenstellend, wenn Sie den exakten Wert \(oder einen angenäherten Dezimalwert hiervon\) benötigen. Mit den neuen Formatierungsalgorithmen werden beliebig viele Ziffern zur Darstellung des Werts \(oder der angegeben Genauigkeit\) generiert. Schauen Sie sich als Beispiel für die Verbesserung die Ergebnisse bei der Ausgabe einer hohen Potenz von zwei an:  
  
    ```  
    printf("%.0f\n", pow(2.0, 80))  
  
    ```  
  
    ```Output  
        Alt: 1208925819614629200000000    Neu: 1208925819614629174706176  
    ```  
  
     Mit den alten Analysealgorithmen werden nur bis zu 17 signifikante Ziffern aus der Eingabezeichenfolge berücksichtigt und die restlichen Ziffern verworfen. Dies ist ausreichend, um einen durch die Zeichenfolge dargestellten Näherungswert zu generieren. Das Ergebnis liegt in der Regel sehr nah am richtigen gerundeten Ergebnis. Mit der neuen Implementierung werden alle vorhanden Ziffern berücksichtigt und das ordnungsgemäß gerundete Ergebnis für alle Eingaben \(bis zu 768 Ziffern\) generiert. Darüber hinaus berücksichtigen diese Funktionen nun den Rundungsstatus \(steuerbar über fesetround\).  Dies ist eine potenziell wichtige Verhaltensänderung, da diese Funktionen ggf. abweichende Ergebnisse ausgeben. Die neuen Ergebnisse sind in jedem Fall genauer als die alten Ergebnisse.  
  
-   **Analyse von Hexadezimal\- und unendlichen\-\/NaN\-Gleitkommawerten**  
  
     Mit den Analysealgorithmen für Gleitkommawerte werden nun Zeichenfolgen mit Hexadezimal\-Gleitkommawerten \(z. B. die von %a\- und %A\-Ausgabeformatspezifizierer generierten\) und alle unendlichen und NaN\-Zeichenfolgen, die von den printf\-Funktion generiert werden, wie oben beschrieben analysiert.  
  
-   **Auffüllung von %A und %a mit Nullen**  
  
     Mit den %a\- und %A\-Formatspezifizierern werden Gleitkommawerte als Hexadezimalmantisse und binärer Exponent formatiert. In früheren Versionen wurden mit den printf\-Funktionen die Zeichenfolgen nicht ordnungsgemäß mit Nullen aufgefüllt. Beispiel: printf\("%07.0a\\n", 1.0\) hat 00x1p\+0 ausgegeben, statt 0x01p\+0. Dies wurde korrigiert.  
  
-   **Genauigkeit von %A und %a**  
  
     Die Standardgenauigkeit der %A\- und %a\-Formatspezifizierer lag in früheren Bibliotheksversionen bei 6. Die Standardgenauigkeit liegt jetzt bei 13 und entspricht somit dem C\-Standard.  
  
     Dies ist eine Laufzeitverhaltensänderung in der Ausgabe von jeder Funktion, die eine Zeichenfolge mit %A oder % verwendet. Beim alten Verhalten lautete die Ausgabe bei Verwendung des %A\-Spezifizierers möglicherweise „1.1A2B3Cp\+111“. Die Ausgabe für den gleichen Wert lautet nun „1.1A2B3C4D5E6F7p \+ 111“. Zum Wiederherstellen des alten Verhaltens können Sie die Genauigkeit angeben, z. B. %.6A. Siehe [Genauigkeitsangabe](../c-runtime-library/precision-specification.md).  
  
-   **%F\-Spezifizierer**  
  
     Der %F\-Format\-\/Konvertierungsspezifizierer wird nun unterstützt. Er weist die gleiche Funktionalität auf, wie der Formatspezifizierer „%f“ auf, außer dass unendliche und NaN\-Werte mithilfe von Großbuchstaben formatiert werden.  
  
     In früheren Versionen wurden F\# und N als Längenmodifizierer von der Implementierung analysiert. Dieses Verhalten geht auf segmentierte Adressräume zurück: Mit diesen Längenspezifizierern wurden ferne und nahe Zeiger wie in %Fp oder %Ns ermittelt. Dieses Verhalten wurde entfernt. Wenn %F ermittelt wird, wird es nun als %F\-Formatspezifizierer behandelt. Wenn %N ermittelt wird, wird es nun als ungültiger Parameter behandelt.  
  
-   **Formatieren von Exponenten**  
  
     Mit den %e\- und %E\-Formatspezifizierern werden Gleitkommawerte als Dezimalmantisse und Exponent formatiert. Die %g\- und %G\-Formatspezifizierer formatieren die Zahlen in einigen Fällen auf die gleiche Weise. In früheren Versionen wurden Zeichenfolgen immer mit Exponenten mit drei Ziffern von der CRT generiert. printf \("%e\\n", 1.0\) hat beispielsweise 1.000000e\+000 ausgegeben. Dies war jedoch falsch: C erfordert, dass bei Exponenten, die mit nur einer oder zwei Ziffern dargestellt werden können, auch nur zwei Ziffern ausgegeben werden.  
  
     In Visual Studio 2005 wurde eine globale Übereinstimmungsoption hinzugefügt: [\_set\_output\_format](../c-runtime-library/set-output-format.md). Ein Programm konnte diese Funktion mit dem Argument \_TWO\_DIGIT\_EXPONENT aufrufen, um die übereinstimmende Ausgabe von Exponenten zu aktivieren. Das Standardverhalten wurde zum standardkonformen Exponentenausgabemodus geändert.  
  
-   **Überprüfung der Formatzeichenfolge**  
  
     In früheren Versionen haben die printf\- und scanf\-Funktionen automatisch viele ungültige Formatzeichenfolgen akzeptiert, was in einigen Fällen zu ungewöhnlichen Ergebnissen geführt hat. %hlhlhld wurde beispielsweise als %d behandelt. Alle ungültigen Formatzeichenfolgen werden jetzt als ungültige Parameter behandelt.  
  
-   **Überprüfung der fopen\-Moduszeichenfolgen**  
  
     In früheren Versionen hat die fopen\-Funktionsreihe einige ungültige Moduszeichenfolgen einfach akzeptiert \(z. B. „r\+b\+“\). Ungültige Moduszeichenfolgen werden nun erkannt und als ungültige Parameter behandelt.  
  
-   **\_O\_U8TEXT\-Modus**  
  
     Die [\_setmode](../c-runtime-library/reference/setmode.md)\-Funktion meldet jetzt ordnungsgemäß den Modus für im \_O\_U8TEXT\-Modus geöffnete Streams. In früheren Bibliotheksversionen wurden solche Streams als in \_O\_WTEXT geöffnete Streams gekennzeichnet.  
  
     Dies ist eine wichtige Änderung, wenn Ihr Code den \_O\_WTEXT\-Modus für Streams bei der UTF\-8\-Codierung interpretiert. Wenn UTF\_8 von Ihrer Anwendung nicht unterstützt wird, sollten Sie in Erwägung ziehen, Unterstützung für diese immer häufiger verwendete Codierung hinzuzufügen.  
  
-   **snprintf und vsnprintf**  
  
     Die [snprintf](../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md)\- und [vsnprintf](../c-runtime-library/reference/vsnprintf-vsnprintf-vsnprintf-l-vsnwprintf-vsnwprintf-l.md)\-Funktionen sind jetzt implementiert. Älterer Code stellte häufig die Versionen der Makrodefinitionen dieser Funktionen bereit, da sie nicht von der CRT\-Bibliothek implementiert wurden. In neueren Versionen ist dies nicht länger erforderlich. Wenn [snprintf](../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md) oder [vsnprintf](../c-runtime-library/reference/vsnprintf-vsnprintf-vsnprintf-l-vsnwprintf-vsnwprintf-l.md) vor dem Einfügen von  \<stdio.h\> als Makro definiert sind, tritt bei der Kompilierung ein Fehler auf, der angibt, wo das Makro definiert wurde.  
  
     In der Regel kann dieser Fehler behoben werden, indem alle Deklarationen von snprintf oder vsnprintf im Benutzercode gelöscht werden  
  
-   **tmpnam generiert verwendbare Dateinamen**  
  
     In früheren Versionen wurden mit den  tmpnam\- und tmpnam\_s\-Funktionen Dateinamen im Stammverzeichnis des Laufwerks \(z. B. \\sd3c.\) geniert. Mit diesen Funktionen werden jetzt verwendbare Dateinamenpfade in einem temporären Verzeichnis generiert.  
  
-   **Dateikapselung**  
  
     In früheren Versionen wurde der Dateityp vollständig in \<stdio.h\> definiert. So konnte der Benutzercode auf eine Datei zugreifen und interne Daten ändern. Die stdio\-Bibliothek blendet nun detaillierte Informationen zur Implementierung aus. Im Rahmen dieser Änderung stellt FILE wie in \<stdio.h\> definiert nun einen nicht transparenten Typ dar, und auf die Member kann nicht von außerhalb der CRT selbst zugegriffen werden.  
  
-   **\_outp und \_inp**  
  
     Die Funktionen [\_outp](../c-runtime-library/outp-outpw-outpd.md), [\_outpw](../c-runtime-library/outp-outpw-outpd.md), [\_outpd](../c-runtime-library/outp-outpw-outpd.md), [\_inp](../c-runtime-library/inp-inpw-inpd.md), [\_inpw](../c-runtime-library/inp-inpw-inpd.md) und [\_inpd](../c-runtime-library/inp-inpw-inpd.md) wurden entfernt.  
  
### \<stdlib.h\>, \<malloc.h\> und \<sys\/stat.h\>  
  
-   **strtof und wcstof**  
  
     Die strtof\- und wcstof\-Funktionen konnten errno nicht auf ERANGE festlegen, wenn der Wert nicht als Gleitkomma dargestellt werden konnte. Dies wurde korrigiert. \(Beachten Sie, dass dieser Fehler für diese beiden Funktionen spezifisch ist. Die strtod\-, wcstod\-, strtold\- und wcstold\-Funktionen sind davon nicht betroffen sind.\) Dies ist eine wichtige Laufzeitänderung.  
  
-   **Ausgerichtete Zuordnungsfunktionen**  
  
     In früheren Versionen haben die ausgerichteten Zuordnungsfunktionen \(\_aligned\_malloc, \_aligned\_offset\_malloc usw.\) automatisch Anforderungen für einen Block mit einer Ausrichtung von 0 akzeptiert. Die angeforderte Ausrichtung muss eine Potenz von zwei sein, was bei 0 nicht der Fall ist. Dieser Fehler wurde behoben. Eine angeforderte Ausrichtung von 0 wird als ungültiger Parameter behandelt. Dies ist eine wichtige Laufzeitänderung.  
  
-   **Heapfunktionen**  
  
     Die \_heapadd\-, \_heapset\- und \_heapused\-Funktionen wurden entfernt. Diese Funktionen waren nicht funktionsfähig, seit die CRT für die Verwendung des Windows\-Heaps aktualisiert wurde.  
  
-   **smallheap**  
  
     Die smalheap\-Funktion wurde entfernt. Siehe [Linkoptionen](../c-runtime-library/link-options.md).  
  
### \<string.h\>  
  
-   **wcstok**  
  
     Die Signatur der wcstok\-Funktion wurde geändert und erfüllt jetzt die Anforderungen von C\-Standard. In früheren Versionen der Bibliothek sah die Signatur dieser Funktion wie folgt aus:  
  
    ```  
    wchar_t* wcstok(wchar_t*, wchar_t const*)  
    ```  
  
     Sie verwendete internen threadspezifischen Kontext, um den Status aller Aufrufe nachzuverfolgen, wie für strtok durchgeführt. Die Funktion weist jetzt die Signatur wchar\_t\* wcstok\(wchar\_t\*, wchar\_t const\*, wchar\_t\*\*\) und erfordert, dass der Aufrufer den Kontext als drittes Argument an die Funktion übergibt.  
  
     Eine new \_wcstok\-Funktion mit der alten Signatur wurde hinzugefügt, um das Portieren zu erleichtern. Beim Kompilieren von C\+\+\-Code ist auch eine Inlineüberladung von wcstok mit der alten Signatur vorhanden. Diese Überladung ist veraltet. In C\-Code können Sie mit define\_CRT\_NON\_CONFORMING\_WCSTOKfestlegen, dass\_wcstok anstelle von wstok verwendet wird.  
  
### \<time.h\>  
  
-   **Uhr**  
  
     In früheren Versionen wurde die [clock](../c-runtime-library/reference/clock.md)\-Funktion mit der Windows\-API [GetSystemTimeAsFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724397.aspx) implementiert. Durch diese Implementierung war die die clock\-Funktion von der Systemzeit abhängig, und war daher nicht monoton. Die clock\-Funktion wurde hinsichtlich [QueryPerformanceCounter](https://msdn.microsoft.com/library/windows/desktop/ms644904.aspx) neu implementiert und ist jetzt monoton.  
  
-   **fstat und\_utime**  
  
     In früheren Versionen haben die [\_stat](../c-runtime-library/reference/stat-functions.md)\-, [fstat](../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)\- und [\_utime](../c-runtime-library/reference/utime-utime32-utime64-wutime-wutime32-wutime64.md)\-Funktionen die Sommerzeit nicht ordnungsgemäß behandelt. Vor Visual Studio 2013 haben all diese Funktionen die Normalzeiten fälschlicherweise als Sommerzeit behandelt.  
  
     In Visual Studio 2013 wurde das Problem in der \_stat\-Funktionsreihe behoben. Ähnliche Probleme in der fstat\- und \_utime\-Funktionsreihe wurden jedoch nicht behoben. Dies führte zu Problemen aufgrund von Inkonsistenzen zwischen den Funktionen. Die fstat\- und \_utime\-Funktionsreihe wurden nun behoben, sodass all diese Funktionen nun die Sommerzeiten ordnungsgemäß und konsistent behandeln.  
  
-   **asctime**  
  
     In früheren Versionen hat die [asctime](../c-runtime-library/reference/asctime-wasctime.md)\-Funktion einstellige Tagesangaben mit einer führenden 0 aufgefüllt, z. B. Freitag, 06 Juni 08:00:00 2014. Die Spezifikation erfordert, dass diese Tage mit einem führenden Leerzeichen aufgefüllt werden, z. B. Freitag, 6 Juni 08:00:00 2014. Dies wurde korrigiert.  
  
-   **strftime und wcsftime**  
  
     Die strftime\- und wcsftime\-Funktionen unterstützen jetzt die Formatspezifizierer %C, %D, %e, %F, %g, %G, %h, %n, %r, %R, %t, %T, %u, und %V. Darüber hinaus werden die E\- und O\-Modifizierer analysiert, aber ignoriert.  
  
     Der %c\-Formatspezifizierer erzeugt „Entsprechende Datum\- und Uhrzeitdarstellung“ für das aktuelle Gebietsschema. In der C\-Gebietsschema muss diese Darstellung mit %a %b %e %T %Y identisch sein. Dies ist die gleiche Form wie von asctime erzeugt. In früheren Versionen hat der %c\-Formatspezifizierer die Zeiten nicht ordnungsgemäß formatiert und sie in der Form MM\/TT\/JJ HH:MM:SS dargestellt. Dies wurde korrigiert.  
  
-   **timespec und TIME\_UTC**  
  
     Der \<time.h\>\-Header definiert nun den timespec\-Typ und die timespec\_get\-Funktion von C11 Standard. Darüber hinaus ist das TIME\_UTC\-Makro für die Verwendung mit der timespec\_get\-Funktion jetzt definiert. Dies ist eine wichtige Änderung für Code, der einen Konflikt mit der Definition für diese aufweist.  
  
-   **CLOCKS\_PER\_SEC**  
  
     Das CLOCKS\_PER\_SEC\-Makro wird jetzt auf eine ganze Zahl des Typs clock\_t erweitert, wie für C erforderlich.  
  
###  <a name="BK_STL"></a> Standard Template Library  
 Um neue Optimierungen und Debuggingüberprüfungen zu aktivieren, unterbricht die Visual Studio\-Implementierung der C\+\+\-Standardbibliothek absichtlich die binäre Kompatibilität von einer Version zur nächsten. Wenn die C\+\+\-Standardbibliothek verwendet wird, können Objektdateien und statische Bibliotheken, die unter Verwendung von verschiedenen Versionen kompiliert werden, nicht in einer Binärdatei \(EXE oder DLL\) vermischt werden, und C\+\+\-Standardbibliotheksobjekte können nicht zwischen Binärdateien übergeben werden, die mit verschiedenen Versionen kompiliert werden. Eine solche Kombination gibt Linkerfehler über \_MSC\_VER\-Konflikte aus. \(\_MSC\_VER ist das Makro, das die Hauptversion des Compilers enthält – z. B. 1800 für Visual Studio 2013.\) Diese Überprüfung kann weder eine gemischte DLL\-Verwendung noch eine gemischte Verwendung erkennen, die Visual C\+\+ 2008 oder früher betrifft.  
  
-   **STL\-Includedateien**  
  
     Es wurden einige Änderungen an der Includestruktur in den STL\-Headern vorgenommen. STL\-Header dürfen einander nicht auf unbekannte Weise enthalten. Im Allgemeinen sollten Sie Code schreiben, der sorgfältig alle entsprechend dem C\+\+\-Standard benötigten Header enthält, und nicht darauf beruht, welche STL\-Header in anderen STL\-Headern enthalten sind. Dadurch kann der Code für andere Versionen und Plattformen verwendet werden. Mindestens zwei Headeränderungen in [!INCLUDE[vs_dev14](../ide/includes/vs_dev14_md.md)] wirken sich auf den Benutzercode aus. Erstens ist \<iterator\> nicht mehr in \<string\> enthalten. Zweitens deklariert \<tuple\> jetzt std:: array ohne \<array\>, wodurch Code über die folgende Kombination von Codekonstrukten unterbrochen werden kann: der Code hat eine array\-Variable und Sie verfügen über eine using\-Direktive „using namespace std;“ und fügen einen STL\-Header \(z. B. \<functional\>\) mit \<tuple\> hinzu, von dem std::array nun deklariert wird.  
  
-   **steady\_clock**  
  
     Die \<chrono\>\-Implementierung von [steady\_clock](../standard-library/steady-clock-struct.md) wurde gemäß den Zuverlässigkeits\- und Stabilitätsanforderungen des C\+\+\-Standards geändert. „steady\_clock“ basiert nun auf [QueryPerformanceCounter](https://msdn.microsoft.com/library/windows/desktop/ms644904.aspx) und „high\_resolution\_clock“ ist jetzt eine Typedefinition für „steady\_clock“. Daher ist steady\_clock::time\_point nun in Visual C\+\+ eine Typdefinition für chrono::time\_point\<steady\_clock\>; Dies ist jedoch bei anderen Implementierungen nicht unbedingt der Fall.  
  
-   **Zuordnungen und Konstanten**  
  
     Es sind nun Vergleiche der Zuordnungen erforderlich, um Konstantenargumente zu akzeptieren.  Wenn Ihre Zuweisungen diese Operatoren wie folgt definieren:  
  
    ```  
    bool operator==(const MyAlloc& other)  
    ```  
  
     Sie sollten diese aktualisieren, damit sie sie als const\-Member deklarieren.  
  
    ```  
    bool operator==(const MyAlloc& other) const  
    ```  
  
-   **const\-Elemente**  
  
     Im C\+\+\-Standard waren Container von const\-Elementen nie zulässig \(z. B. vector\<const T \> oder set\<const T \>\). In Visual C\+\+ 2013 und in früheren Versionen waren solche Container zulässig. In der aktuellen Version tritt beim Kompilieren dieser Container ein Fehler auf.  
  
-   **std::allocator::deallocate**  
  
     In Visual C\+\+\-2013 und früheren Versionen hat std::allocator::deallocate\(p, n\) das für n übergebene Argument ignoriert.  Der C\+\+\-Standard erfordert, dass n dem Wert entspricht, der als erstes Argument für den Aufruf der von p zurückgegebenen Zuordnung entspricht. In der aktuellen Versionwird jedoch der Wert von „n“ untersucht. Code, der die von Standardanforderungen abweichenden Argumente übergibt, stürzt möglicherweise zur Laufzeit ab.  
  
-   **hash\_map und hash\_set**  
  
     Nicht standardmäßige Headerdateien ash\_map und hash\_set sind in [!INCLUDE[vs_dev14](../ide/includes/vs_dev14_md.md)] veraltet und werden in Zukunft entfernt. Verwenden Sie stattdessen unordered\_map und unordered\_set.  
  
-   **Vergleiche und operator\(\)**  
  
     Assoziative Container \(\<map\>\-Reihe\) erfordern jetzt Vergleiche mit const\-Funktionsaufrufoperatoren. Beim Ausführen des folgenden Codes tritt nun in einer Vergleichsklassendeklaration ein Fehler beim Kompilieren auf:  
  
    ```  
    bool operator()(const X& a, const X& b)  
    ```  
  
     Ändern Sie zur Behebung dieses Problems die Funktionsdeklaration zu der folgenden:  
  
    ```  
    bool operator()(const X& a, const X& b) const  
    ```  
  
-   **Typmerkmale**  
  
     Die alten Namen für Typmerkmale aus einer früheren Version des C\+\+\-Standardentwurfs wurden entfernt. Diese wurden in C\+\+11 auf die C\+\+11\-Werte in [!INCLUDE[vs_dev14](../ide/includes/vs_dev14_md.md)] aktualisiert. In der folgenden Tabelle werden die alten und neuen Namen aufgeführt.  
  
    |Alter Name|Neuer Name|  
    |----------------|----------------|  
    |add\_reference|add\_lvalue\_reference|  
    |has\_default\_constructor|is\_default\_constructible|  
    |has\_copy\_constructor|is\_copy\_constructible|  
    |has\_move\_constructor|is\_move\_constructible|  
    |has\_nothrow\_constructor|is\_nothrow\_default\_constructible|  
    |has\_nothrow\_default\_constructor|is\_nothrow\_default\_constructible|  
    |has\_nothrow\_copy|is\_nothrow\_copy\_constructible|  
    |has\_nothrow\_copy\_constructor|is\_nothrow\_copy\_constructible|  
    |has\_nothrow\_move\_constructor|is\_nothrow\_move\_constructible|  
    |has\_nothrow\_assign|is\_nothrow\_copy\_assignable|  
    |has\_nothrow\_copy\_assign|is\_nothrow\_copy\_assignable|  
    |has\_nothrow\_move\_assign|is\_nothrow\_move\_assignable|  
    |has\_trivial\_constructor|is\_trivially\_default\_constructible|  
    |has\_trivial\_default\_constructor|is\_trivially\_default\_constructible|  
    |has\_trivial\_copy|is\_trivially\_copy\_constructible|  
    |has\_trivial\_move\_constructor|is\_trivially\_move\_constructible|  
    |has\_trivial\_assign|is\_trivially\_copy\_assignable|  
    |has\_trivial\_move\_assign|is\_trivially\_move\_assignable|  
    |has\_trivial\_destructor|is\_trivially\_destructible|  
  
-   **launch::any\- und launch::sync\-Richtlinien**  
  
     Nicht dem Standard entsprechende launch::any\- und launch::sync\-Richtlinien wurden entfernt. Verwenden Sie stattdessen für launch::any, aunch:async &#124; launch:deferred. Verwenden Sie für launch::sync launch::deferred. Siehe [launch\-Enumeration](../Topic/launch%20Enumeration.md).  
  
###  <a name="BK_MFC"></a> MFC und ATL  
  
-   **MFC \(Microsoft Foundation Classes\)** ist aufgrund seiner Größe nicht mehr in der Standardinstallation von Visual Studio enthalten. Wählen Sie zur Installation von MFC die benutzerdefinierte Installationsoption im Visual Studio 2015\-Setup aus. Wenn Visual Studio 2015 bereits installiert ist, können Sie MFC installieren, indem Sie das Visual Studio\-Setup erneut ausführen, die benutzerdefinierte Installationsoption anklicken und dann Microsoft Foundation Classes auswählen. Sie können das Visual Studio\-Setup in der Systemsteuerung, unter „Programme und Funktionen“ oder über die Installationsmedien erneut ausführen.  
  
     Diese Bibliothek ist weiterhin im Visual C\+\+ Redistributable Package enthalten.  
  
###  <a name="BK_ConcRT"></a> Concurrency Runtime  
  
-   **Yield\-Makro aus Windows.h weist einen Konflikt auf mit concurrency::Context::Yield**  
  
     Die Concurrency Runtime verwendete zuvor \#undef, um die Yield\-Makrodefinition zur Vermeidung von Konflikten zwischen dem in Windows.h und der concurrency::Context::Yield\-Funktion definierten Yield\-Makro aufzuheben. \#undef wurde entfernt und es wurde ein neuer nicht in Konflikt stehender äquivalenter API\-Aufruf [concurrency::Context::YieldExecution](../Topic/Context::YieldExecution%20Method.md) hinzugefügt. Zur Umgehung von Konflikten mit Yield können Sie entweder den Code stattdessen zum Aufrufen der YieldExecution\-Funktion aktualisieren, oder den Yield\-Funktionsnamen auf der Aufrufsite wie im folgenden Beispiel aufgeführt durch Klammern umschließen:  
  
    ```  
    (concurrency::Context::Yield)();  
    ```  
  
## Siehe auch  
 [Erste Schritte](../misc/getting-started-with-visual-cpp-in-visual-studio-2015.md)   
 [Wichtige Änderungen in Visual C\+\+ 2013](https://msdn.microsoft.com/library/hh409293.aspx)