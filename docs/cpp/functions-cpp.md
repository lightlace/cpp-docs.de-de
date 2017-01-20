---
title: "Funktionen (C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Deklaratoren, Funktionen"
  - "Standardargumente"
  - "Standardwerte, arguments"
  - "Funktionsdefinitionen"
  - "Funktionsdefinitionen, Informationen über Funktionsdefinitionen"
ms.assetid: 33ba01d5-75b5-48d2-8eab-5483ac7d2274
caps.latest.revision: 19
caps.handback.revision: "19"
ms.author: "mblome"
manager: "ghogen"
---
# Funktionen (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Funktion ist ein Codeblock, der einige Vorgänge ausführt.  Eine Funktion kann optional Eingabeparameter definieren, die Aufrufern ermöglichen, Argumente in die Funktion weiterzugeben.  Eine Funktion kann einen Wert optional als Ausgabe zurückgeben.  Funktionen sind für das Kapseln allgemeiner Vorgänge in einem einzelnen wiederverwendbaren Block nützlich, und zwar ideal unter Verwendung eines Namens, der deutlich das beschreibt, was die Funktion vornimmt.  Die folgende Funktion akzeptiert zwei Ganzzahlen von einem Aufrufer und gibt deren Summe zurück; `a` und `b` sind *Parameter* des Typs `int`.  
  
```  
int sum(int a, int b)  
{  
    return a + b;  
}  
```  
  
 Die Funktion kann von beliebigen Plätzen im Programm *aufgerufen* werden.  Bei den an die Funktion weitergegebenen Werte handelt es sich um die *Argumente*, deren Typen mit den Parametertypen in der Funktionsdefinition kompatibel sein müssen.  
  
```  
int main()  
{  
    int i = sum(10, 32);  
    int j = sum(i, 66);  
    cout << "The value of j is" << j << endl; // 108  
}  
```  
  
 Es gibt keine praktische Begrenzung für die Funktionslänge, jedoch angemessene Entwurfsziele für Funktionen, die eine einzelne klar definierte Aufgabe ausführen.  Komplexe Algorithmen sollten möglichst in leicht verständliche einfachere Funktionen aufgeschlüsselt werden.  
  
 Im Klassenbereich definierte Funktionen werden als Memberfunktionen bezeichnet.  In C\+\+ kann eine Funktion im Gegensatz zu anderen Sprachen auch im Namespacebereich \(einschließlich des impliziten globalen Namespace\) definiert werden.  Derartige Funktionen werden als *freie Funktionen* oder *Nicht\-Memberfunktionen* bezeichnet. Sie werden umfassend in der Standardbibliothek verwendet.  
  
## Bestandteile einer Funktionsdeklaration  
 Eine minimale *Funktionsdeklaration* besteht aus dem Rückgabetyp, dem Funktionsnamen und der Parameterliste \(die leer sein kann\) sowie optionalen Schlüsselwörtern, die dem Compiler zusätzliche Anweisungen bereitstellen.  Eine Funktionsdefinition besteht aus einer Deklaration und dem *Textteil*. Hierbei handelt es sich um den gesamten Code zwischen den geschweiften Klammern.  Eine Funktionsdeklaration, auf die ein Semikolon folgt, wird möglicherweise an mehreren Stellen in einem Programm angezeigt.  Sie muss vor dem Aufrufen dieser Funktion in jeder Übersetzungseinheit angezeigt werden.  Die Funktionsdefinition darf gemäß der Regel mit einer Definition \(One Definition Rule, ODR\) nur einmal im Programm angezeigt werden.  
  
 Die erforderlichen Bestandteile einer Funktionsdeklaration lauten:  
  
1.  Der Rückgabetyp, der den Typ des Werts, den die Funktion zurückgibt, angibt, oder `void`, wenn kein Wert zurückgegeben wird.  In C\+\+ 11 ist „auto“ ein gültiger Rückgabetyp. Dieser weist den Compiler an, den Typ aus der Rückgabeanweisung schlusszufolgern.  In C\+\+14 ist „decltype\(auto\)“ ebenfalls zulässig.  Weitere Informationen finden Sie unten unter „Typableitung in Rückgabetypen“.  
  
2.  Der Funktionsname, der mit einem Buchstaben oder Unterstrich beginnen muss, darf keine Leerzeichen enthalten.  Im Allgemeinen weisen führende Unterstriche in Standardbibliothek\-Funktionsnamen auf private Memberfunktionen oder Nicht\-Memberfunktionen, die nicht für die Verwendung durch Ihren Code vorgesehen sind, hin.  
  
3.  Die Parameterliste, ein durch geschweifte Klammern getrennter, kommagetrennter Satz von mindestens null Parametern, die den Typ und optional einen lokalen Namen angeben, anhand dessen die Werte im Funktionsrumpf möglicherweise aufgerufen werden.  
  
 Optionale Bestandteile einer Funktionsdeklaration sind:  
  
1.  `constexpr`. Gibt an, dass es sich beim Rückgabewert der Funktion um einen konstanten Wert handelt, der zur Kompilierungszeit berechnet werden kann.  
  
    ```  
  
                  constexpr float exp(float x, int n)  
    {  
        return n == 0 ? 1 :  
            n % 2 == 0 ? exp(x * x, n / 2) :  
            exp(x * x, (n - 1) / 2) * x;  
    };  
    ```  
  
2.  Es handelt sich um eine `linkage`\-Spezifikation, `extern` oder `static`.  
  
    ```  
    Declare printf with C linkage.  
    extern "C" int printf( const char *fmt, ... );  
  
    ```  
  
     Weitere Informationen finden Sie unter [Programm und Verknüpfung](../cpp/program-and-linkage-cpp.md).  
  
3.  `inline`. Weist den Compiler an, jeden Funktionsaufruf durch den Funktionscode an sich zu ersetzen.  Durch den Inlinevorgang kann die Leistung in Szenarien verbessert werden, in denen eine Funktion schnell ausgeführt und wiederholt in einem leistungskritischen Codeabschnitt aufgerufen wird.  
  
    ```  
    inline double Account::GetBalance()  
    {  
        return balance;  
    }  
    ```  
  
     Weitere Informationen finden Sie unter [Inlinefunktionen](../cpp/inline-functions-cpp.md).  
  
4.  `noexcept`. Gibt an, ob die Funktion eine Ausnahme auslösen kann.  Im folgenden Beispiel löst die Funktion keine Ausnahme aus, wenn der Ausdruck `is_pod` als `true` ausgewertet wird.  
  
    ```  
    #include <type_traits>  
  
    template <typename T>  
    T copy_object(T& obj) noexcept(std::is_pod<T>) {...}  
    ```  
  
     Weitere Informationen finden Sie unter [noexcept](../cpp/noexcept-cpp.md).  
  
5.  \(nur Memberfunktionen\) Die CV\-Qualifizierer, die angeben, ob die Funktion `const` oder `volatile` ist.  
  
6.  \(nur Memberfunktionen\) `virtual`, `override` oder `final`.  `virtual`. Gibt an, dass eine Funktion in einer abgeleiteten Klasse überschrieben werden kann.  `override` bedeutet, dass eine Funktion in einer abgeleiteten Klasse eine virtuelle Funktion überschreibt.  `final` bedeutet, dass eine Funktion in keiner weiteren abgeleiteten Klasse überschrieben werden kann.  Weitere Informationen finden Sie unter [Virtuelle Funktionen](../cpp/virtual-functions.md).  
  
7.  \(nur Memberfunktionen\) Wenn `static` auf eine Memberfunktion angewendet ist, bedeutet dies, dass die Funktion nicht mit Objektinstanzen der Klasse verknüpft ist.  
  
8.  \(nur nicht statische Memberfunktionen\) Der ref\-Qualifizierer, der den Compiler angibt, welche eine auszuwählende Funktion überlädt, wenn der implizite Objektparameter \(\*this\) ein rvalue\-Verweis im Vergleich zu einem  lvalue\-Verweis ist.  
  
 Die folgende Abbildung zeigt die Teile einer Funktionsdefinition.  Der schattierte Bereich ist der Funktionsrumpf.  
  
 ![Teile einer Funktionsdefinition](../cpp/media/vc38ru1.png "vc38RU1")  
Teile einer Funktionsdefinition  
  
## Funktionsdefinitionen  
 Im Textteil deklarierte Variablen werden als lokale Variablen bezeichnet.  Sie verlassen den Gültigkeitsbereich, wenn die Funktion beendet wird. Daher sollte eine Funktion niemals einen Verweis zu einer lokalen Variable zurückgeben\!  
  
## Funktionsvorlagen  
 Eine Funktionsvorlage ähnelt einer Klassenvorlage. Sie generiert auf Grundlage der Vorlagenargumente konkrete Funktionen.  In vielen Fällen kann die Vorlage die Typargumente ableiten. Daher ist es nicht erforderlich, sie explizit anzugeben.  
  
```  
template<typename Lhs, typename Rhs>  
auto Add2(const Lhs& lhs, const Rhs& rhs)  
{  
    return lhs + rhs;  
}  
  
auto a = Add2(3.13, 2.895); // a is a double  
auto b = Add2(string{ "Hello" }, string{ " World" }); // b is a std::string  
```  
  
 Weitere Informationen finden Sie unter [Funktionsvorlagen](../cpp/function-templates.md).  
  
## Funktionsparameter und Argumente  
 Eine Funktion weist eine durch Kommas getrennte Liste von mindestens null Typen auf. Jede davon verfügt über einen Namen, unter dem es im Funktionsrumpf aufgerufen werden kann.  Eine Funktionsvorlage kann den zusätzliche Typ\- oder Wertparameter angeben.  Der Aufrufer gibt Argumente weiter, bei denen es sich um konkrete Werte handelt, deren Typen mit der Parameterliste kompatibel sind.  
  
 Argumente werden standardmäßig zur Funktion nach Wert weitergegeben. Die Funktion empfängt demnach eine Kopie des weiterzugebenden Objekts.  Für große Objekte kann das Erstellen einer Kopie aufwändig und nicht immer erforderlich sein.  Fügen Sie dem Parameter einen Verweisqualifizierer hinzu, damit Argumente nach Verweis \(insbesondere lvalue\-Verweis\) weitergegeben werden:  
  
```  
void DoSomething(std::string& input){...}  
```  
  
 Wenn eine Funktion ein Argument ändert, das nach Verweis weitergegeben wird, ändert sie das ursprüngliche Objekt und nicht eine lokale Kopie.  Qualifizieren Sie den Parameter als „const&“, um zu verhindern, dass eine Funktion ein derartiges Argument ändert:  
  
```  
void DoSomething(const std::string& input){...}  
```  
  
 **C\+\+ 11:**  Verwenden Sie zum expliziten Verarbeiten von Argumenten, die nach rvalue\-Verweis ODER nach lvalue\-Verweis weitergegeben werden, ein doppeltes kaufmännisches Und\-Zeichen im Parameter, um einen universellen Verweis anzugeben:  
  
```  
void DoSomething(const std::string&& input){...}  
```  
  
 Eine Funktion, die mit dem einzelnen Schlüsselwort `void` in der Parameterdeklarationsliste deklariert wird, akzeptiert keine Argumente, solange das Schlüsselwort `void` der erste und einzige Member der Argumentdeklarationsliste ist.  Argumente des Typs `void` an anderer Stelle in der Liste erzeugen Fehler.  Zum Beispiel:  
  
```  
  
// OK same as GetTickCount()  
long GetTickCount( void );   
```  
  
 Es ist zwar nicht zulässig, ein `void` Argument außer wie hier erläutert anzugeben. Aber Typen, die vom `void`\-Typ abgeleitet werden \(z. B. Zeiger auf `void` und Arrays von `void`\), können an beliebiger Stelle in der Argumentdeklarationsliste vorkommen.  
  
### Standardargumente  
 Der oder die letzten Parameter in einer Funktionssignatur werden möglicherweise einem Standardargument zugewiesen. Der Aufrufer kann demnach das Argument auslassen, wenn die Funktion aufgerufen wird, es sei denn, es soll ein anderer Wert angegeben werden.  
  
```  
int DoSomething(int num,   
    string str,   
    Allocator& alloc = defaultAllocator)  
{ ... }  
  
// OK both parameters are at end  
int DoSomethingElse(int num,   
    string str = string{ "Working" },   
    Allocator& alloc = defaultAllocator)  
{ ... }  
  
// C2548: 'DoMore': missing default parameter for parameter 2  
int DoMore(int num = 5, // Not a trailing parameter!  
    string str,  
    Allocator& = defaultAllocator)  
{...}  
```  
  
 Weitere Informationen finden Sie unter [Standardargumente](../cpp/default-arguments.md) und [Standardargumente für Klassenvorlagen](../Topic/Default%20Arguments%20for%20Class%20Templates.md).  
  
## Funktionsrückgabetypen  
 Eine Funktion darf weder eine andere Funktion noch ein integriertes Array zurückgeben. Sie kann jedoch Zeiger auf diese Typen oder ein *lambda* zurückgeben, wodurch ein Funktionsobjekt generiert wird.  Mit Ausnahme dieser Fälle gibt eine Funktion möglicherweise einen Wert eines beliebigen Typs zurück, der sich im Bereich befindet, oder sie gibt keinen Wert zurück. In diesem Fall lautet der Rückgabetyp `void`.  
  
### Nachstehende Rückgabetypen  
 Ein „gewöhnlicher“ Rückgabetyp befindet sich auf der linken Seite der Funktionssignatur.  Ein *nachstehender Rückgabetyp* befindet sich ganze rechts von der Signatur, und diesem ist der Operator \-\> vorangestellt.  Nachstehende Rückgabetypen sind insbesondere in Funktionsvorlagen nützlich, wenn der Typ des Rückgabewerts auf Vorlagenparametern beruht.  
  
```  
template<typename Lhs, typename Rhs>  
auto Add(const Lhs& lhs, const Rhs& rhs) -> decltype(lhs + rhs)  
{  
    return lhs + rhs;   
}  
```  
  
 Wenn `auto` zusammen mit einem nachstehenden Rückgabetyp verwendet wird, fungiert es als ein Platzhalter für das, was der decltype\-Ausdruck generiert, und es führt keine eigene Typableitung aus.  
  
###  <a name="type_deduction"></a> Typableitung in Rückgabetypen \(C\+\+14\)  
 In C\+\+14 können Sie `auto` verwenden, um den Compiler anzuweisen, den Rückgabetyp aus dem Funktionsrumpf abzuleiten, ohne einen nachstehenden Rückgabetyp anzugeben.  Beachten Sie, dass `auto` immer eine Rückgabe per Wert ableitet.  Verwenden Sie `auto&&` um den Compiler anzuweisen, einen Verweis abzuleiten.  
  
 In diesem Beispiel wird `auto` als eine nicht konstante Wertkopie der Summe von lhs und rhs abgeleitet.  
  
```  
template<typename Lhs, typename Rhs>  
auto Add2(const Lhs& lhs, const Rhs& rhs)  
{  
    return lhs + rhs; //returns a non-const object by value  
}  
```  
  
 Beachten Sie, dass `auto` nicht die Konstanz der abzuleitenden Typen beibehalten.  Bei Weiterleitungsfunktionen, deren Rückgabetyp die Konstanz oder Verweisbarkeit der entsprechenden Argumente beibehalten muss, können Sie das Schlüsselwort `decltype(auto)` verwenden. Dieses verwendet die `decltype`\-Typrückschlussregeln und behält alle Typinformationen bei.  `decltype(auto)` kann als ein gewöhnlicher Rückgabewert auf der linken Seite oder als ein nachstehender Rückgabewert verwendet werden.  
  
 Im folgenden Beispiel \(auf Grundlage des Codes aus [N3493](http://www.open-std.org/JTC1/SC22/WG21/docs/papers/2013/n3493.html)\) wird die Verwendung von `decltype(auto)` gezeigt, um die optimale Weiterleitung von Funktionsargumenten in einem Rückgabetyp zu ermöglichen, der bis zur Instanziierung der Vorlage unbekannt ist.  
  
```  
template<typename F, typename Tuple = tuple<T...>, int... I>  
decltype(auto) apply_(F&& f, Tuple&& args, index_sequence<I...>)   
{  
    return std::forward<F>(f)(std::get<I>(std::forward<Tuple>(args))...);  
}  
  
template<typename F, typename Tuple = tuple<T...>,  
    typename Indices = make_index_sequence<tuple_size<Tuple>::value >>  
   decltype( auto)  
    apply(F&& f, Tuple&& args)      
{  
    return apply_(std::forward<F>(f), std::forward<Tuple>(args), Indices());  
}  
}  
```  
  
## Lokale Funktionsvariablen  
 Eine in einem Funktionsrumpf deklarierte Variable wird als eine *lokale Variable* bezeichnet.  Nicht statische lokale Variablen sind nur innerhalb des Funktionsrumpfs sichtbar, wenn sie auf dem Stapel deklariert werden, wenn den Bereich verlässt, wenn die Funktion vorhanden ist.  Wenn Sie eine lokale Variable erstellen und nach Wert zurückgeben, kann der Compiler für gewöhnlich die Rückgabewertoptimierung vornehmen, um nicht erforderliche Kopiervorgänge zu vermeiden.  Wenn Sie eine lokale Variable nach Verweis zurückgeben, stellt eine Compiler eine Warnung aus, da jeder Versuch durch den Aufrufer, diesen Verweis zu verwenden, erst nach der Zerstörung der lokalen Variablen auftritt.  
  
 Lokale statische Objekte werden während der Beendigung zerstört, die von `atexit` angegeben wird.  Wenn kein statisches Objekt erstellt wurde, da die Ablaufsteuerung des Programms seine Deklaration umgangen ist, wird nicht versucht, das Objekt zu zerstören.  
  
### Statische lokale Variablen  
 In C\+\+ kann eine lokale Variable als statisch deklariert werden.  Die Variable ist nur innerhalb des Funktionsrumpfs sichtbar. Es ist jedoch eine einzelne Kopie der Variable für alle Instanzen der Funktion vorhanden.  
  
## Funktionszeiger  
 C\+\+ unterstützt Funktionszeiger auf die gleiche Weise wie die C\-Sprache.  Eine typsichere Alternative besteht jedoch darin, ein Funktionsobjekt zu verwenden.  
  
 Es wird empfohlen, dass `typedef` verwendet wird, um einen Alias für den Funktionszeigertyp zu deklarieren, wenn eine Funktion deklariert wird, die einen Funktionszeigertyp zurückgibt.  Beispiel:  
  
```  
typedef int (*fp)(int);  
fp myFunction(char* s); // function returning function pointer  
```  
  
 Wenn dies nicht erfolgt, kann die korrekte Syntax für die Funktionsdeklaration aus der Deklaratorsyntax für den Funktionszeiger abgeleitet werden, und zwar wie folgt durch Ersetzen des Bezeichners \(`fp` im obigen Beispiel\) durch den Namen und die Argumentliste der Funktion:  
  
```  
int (*myFunction(char* s))(int);  
```  
  
 Die vorhergehende Deklaration gleicht der Deklaration oben, die "typedef" verwendet.  
  
## Siehe auch  
 [Funktionsüberladung](../cpp/function-overloading.md)   
 [Funktionen mit Variablenargumentlisten](../cpp/functions-with-variable-argument-lists-cpp.md)   
 [Explizit vorgegebene und gelöschte Funktionen](../cpp/explicitly-defaulted-and-deleted-functions.md)   
 [Argumentbezogene Namenssuche \(Koenig\) in Funktionen](../cpp/argument-dependent-name-koenig-lookup-on-functions.md)   
 [Standardargumente](../cpp/default-arguments.md)   
 [Inlinefunktionen](../cpp/inline-functions-cpp.md)