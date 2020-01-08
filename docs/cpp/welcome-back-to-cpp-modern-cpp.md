---
title: Willkommen zurück bei C++ (Modern C++)
ms.date: 11/19/2019
ms.topic: conceptual
ms.assetid: 1cb1b849-ed9c-4721-a972-fd8f3dab42e2
ms.openlocfilehash: 4dee4779e941c66af1c23f62a88cecec4916a475
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301742"
---
# <a name="welcome-back-to-c-modern-c"></a>Willkommen zurück bei C++ (Modern C++)

In den letzten 25 Jahren C++ war eine der am häufigsten verwendeten Programmiersprachen in der Welt. Gut geschriebene C++-Programme sind schnell und effizient. Die Sprache ist flexibler als andere Sprachen, da Sie auf Low-Level-Hardware Features zugreifen kann, um die Geschwindigkeit zu maximieren und die Arbeitsspeicher Anforderungen zu minimieren. Sie können damit eine Vielzahl von apps Erstellen – von Spielen bis hin zu hochleistungsfähigen wissenschaftlichen Software, Gerätetreibern, eingebetteten Programmen, Bibliotheken und Compilern für andere Programmiersprachen, Windows-Client-apps und vielem mehr.

Eine der ursprünglichen Anforderungen für C++ war Abwärtskompatibilität mit der Programmiersprache C. Folglich C++ ermöglichte die Programmierung im C-Stil mit unformatierten Zeigern, Arrays, auf NULL endenden Zeichen folgen, benutzerdefinierten Datenstrukturen und anderen Features, die möglicherweise eine hohe Leistung ermöglichen, aber auch Fehler und Komplexität erzeugen können. Die Entwicklung von C++ hat Features hervorgehoben, die die Notwendigkeit der Verwendung von Idioms im C-Stil erheblich verringern. Die alten Funktionen für die C-Programmierung sind vorhanden, wenn Sie Sie benötigen, C++ aber mit modernem Code sollten Sie Sie weniger und weniger benötigen. Moderner C++ Code ist einfacher, sicherer, eleganter und immer noch so schnell wie je zuvor.

Die folgenden Abschnitte bieten einen Überblick über die wichtigsten Features von modern C++. Sofern nicht anders angegeben, sind die hier aufgeführten Funktionen in c++ 11 und höher verfügbar. Im Microsoft C++ -Compiler können Sie die [/Std](../build/reference/std-specify-language-standard-version.md) -Compileroption festlegen, um anzugeben, welche Version des Standards für das Projekt verwendet werden soll.

## <a name="raii-and-smart-pointers"></a>RAII und intelligente Zeiger

Eine der Hauptklassen von Fehlern bei der Programmierung im C-Stil ist der *Speicher* Platz, weil der **Delete** -Vorgang für den Arbeitsspeicher, der mit **New**zugewiesen wurde, nicht aufgerufen werden konnte. Modern C++ betont das Prinzip der *Ressourcenbeschaffung ist die Initialisierung* , die besagt, dass jede Ressource (Heap Speicher, Datei Handles, Sockets usw.) im *Besitz* eines Objekts sein sollte, das die neu zugeordnete Ressource in Ihrem Konstruktor erstellt oder empfängt, und löscht sie in Ihrem Dekonstruktor. Wenn Sie das Prinzip von RAII einhalten, gewährleisten Sie, dass alle Ressourcen ordnungsgemäß an das Betriebssystem zurückgegeben werden, wenn das besitzende Objekt den Gültigkeitsbereich verlässt. Zur Unterstützung der einfachen Übernahme von RAII- C++ Prinzipien bietet die Standard Bibliothek drei intelligente Zeiger Typen: [Std:: unique_ptr](../standard-library/unique-ptr-class.md), [Std:: shared_ptr](../standard-library/shared-ptr-class.md)und [Std:: weak_ptr](../standard-library/weak-ptr-class.md). Ein intelligenter Zeiger übernimmt die Zuordnung und Löschung des Arbeitsspeichers, den er besitzt. Im folgenden Beispiel wird eine-Klasse mit einem Array Element veranschaulicht, das im-`make_unique()`aufgerufen wird. Die Aufrufe von **New** und **Delete** werden von der `unique_ptr`-Klasse gekapselt. Wenn ein `widget` Objekt den Gültigkeitsbereich verlässt, wird der unique_ptr Dekonstruktor aufgerufen und gibt den Arbeitsspeicher frei, der für das Array reserviert wurde.  

```cpp
#include <memory>
class widget
{
private:
    std::unique_ptr<int> data;
public:
    widget(const int size) { data = std::make_unique<int>(size); }
    void do_something() {}
};

void functionUsingWidget() {
    widget w(1000000);   // lifetime automatically tied to enclosing scope
                // constructs w, including the w.data gadget member
    // ...
    w.do_something();
    // ...
} // automatic destruction and deallocation for w and w.data

```

Verwenden Sie nach Möglichkeit einen intelligenten Zeiger, wenn Sie Heap Speicher zuordnen. Wenn Sie die Operatoren "New" und "Delete" explizit verwenden müssen, befolgen Sie das Prinzip von RAII. Weitere Informationen finden Sie unter [Objekt Lebensdauer und Ressourcenverwaltung (RAII)](object-lifetime-and-resource-management-modern-cpp.md).

## <a name="stdstring-and-stdstring_view"></a>Std:: String und Std:: string_view

Zeichen folgen im C-Stil sind eine weitere wichtige Quelle für Fehler. Mithilfe von " [Std:: String" und "Std:: wstring](../standard-library/basic-string-class.md) " können Sie praktisch alle Fehler beseitigen, die mit Zeichen folgen im C-Stil verknüpft sind, und die Vorteile der Element Funktionen zum Suchen, anfügen, voranstellen usw. nutzen. Beide sind für die Geschwindigkeit stark optimiert. Wenn Sie eine Zeichenfolge an eine Funktion übergeben, die nur schreibgeschützten Zugriff erfordert, können Sie in c++ 17 [Std:: string_view](../standard-library/basic-string-view-class.md) für einen noch größeren Leistungsvorteil verwenden.

## <a name="stdvector-and-other-standard-library-containers"></a>Std:: Vector und andere Standard Bibliotheks Container

Die Standard Bibliotheks Container befolgen alle das Prinzip von RAII, stellen Iteratoren für den sicheren Durchlauf von Elementen bereit, sind hochoptimiert für die Leistung und wurden gründlich auf Richtigkeit getestet. Wenn Sie diese Container verwenden, können Sie das Potenzial von Fehlern oder Ineffizienzen vermeiden, die in benutzerdefinierten Datenstrukturen eingeführt werden könnten. Verwenden Sie in der Standardeinstellung [Vector](../standard-library/vector-class.md) als bevorzugten sequenziellen C++Container in. Dies entspricht `List<T>` in .NET-Sprachen.

```cpp
vector<string> apples;
apples.push_back("Granny Smith");
```

Verwenden Sie [map](../standard-library/map-class.md) (nicht `unordered_map`) als standardmäßigen assoziativen Container. Verwenden Sie [Set](../standard-library/set-class.md), [multimap](../standard-library/multimap-class.md)und [Multiset](../standard-library/multiset-class.md) für degenerierte und mehrere Fälle.

```cpp
map<string, string> apple_color;
// ...
apple_color["Granny Smith"] = "Green";
```

Wenn eine Leistungsoptimierung erforderlich ist, erwägen Sie folgende Verwendungen:

- Der [Arraytyp beim](../standard-library/array-class-stl.md) einbetten ist wichtig, z. b. als Klassenmember.

- Ungeordnete assoziative Container, z. b. [unordered_map](../standard-library/unordered-map-class.md). Diese verfügen über einen niedrigeren pro-Element-Aufwand und eine Konstante Zeit Suche, Sie können jedoch schwieriger und effizient verwendet werden.

- Sortiertes `vector`. Weitere Informationen finden Sie unter [Algorithmen](../cpp/algorithms-modern-cpp.md).

Verwenden Sie keine Arrays im C-Stil. Verwenden Sie für ältere APIs, die direkten Zugriff auf die Daten benötigen, Zugriffsmethoden wie z. b. `f(vec.data(), vec.size());`. Weitere Informationen zu Containern finden [ C++ Sie unter Standard Bibliothek Container](../standard-library/stl-containers.md).

## <a name="standard-library-algorithms"></a>Algorithmen der Standard Bibliothek

Bevor Sie davon ausgehen, dass Sie einen benutzerdefinierten Algorithmus für Ihr Programm schreiben müssen, über C++ prüfen Sie zunächst die [Algorithmen](../standard-library/algorithm.md)der Standard Bibliothek. Die Standard Bibliothek enthält ein ständig wachsendes Spektrum an Algorithmen für viele gängige Vorgänge wie das suchen, sortieren, Filtern und randomialisieren. Die mathematische Bibliothek ist umfangreich. Ab c++ 17 werden parallele Versionen von vielen Algorithmen bereitgestellt.

Im Folgenden sind einige wichtige Beispiele aufgeführt:

- **for_each**, der standardmäßige Traversale-Algorithmus (zusammen mit Bereichs basierten for-Schleifen). 

- **Transformation**für nicht direkte Änderungen von Container Elementen

- **find_if**, der Standard Suchalgorithmus.

- **Sortieren**, **lower_bound**und die anderen standardmäßigen Sortier-und Suchalgorithmen.

Verwenden Sie zum Schreiben eines Comparators Strict **<** , und verwenden Sie *benannte Lambdas* , wenn dies möglich ist.

```cpp
auto comp = [](const widget& w1, const widget& w2)
     { return w1.weight() < w2.weight(); }

sort( v.begin(), v.end(), comp );

auto i = lower_bound( v.begin(), v.end(), comp );
```

## <a name="auto-instead-of-explicit-type-names"></a>Auto anstelle von expliziten Typnamen

C++ 11 hat das Schlüsselwort " [Auto](auto-cpp.md) " zur Verwendung in Variablen-, Funktions-und Vorlagen Deklarationen eingeführt. **Auto** weist den Compiler an, den Typ des Objekts abzuleiten, damit Sie ihn nicht explizit eingeben müssen. " **Auto** " ist besonders nützlich, wenn der dedulierte Typ eine in einer Vorlage vorgenommene Vorlage ist:

```cpp
map<int,list<string>>::iterator i = m.begin(); // C-style
auto i = m.begin(); // modern C++
```

## <a name="range-based-for-loops"></a>Bereichsbasierte For-Schleifen

Die Iterationen im C-Stil für Arrays und Container sind anfällig für das Indizieren von Fehlern und auch mühsam. Um diese Fehler zu vermeiden und den Code lesbarer zu machen, verwenden Sie Bereichs basierte for-Schleifen mit Standard Bibliotheks Containern und unformatierten Arrays. Weitere Informationen finden Sie unter [Range-based for-Anweisung](../cpp/range-based-for-statement-cpp.md).

```cpp
#include <iostream>
#include <vector>

int main()
{
    std::vector<int> v {1,2,3};

    // C-style
    for(int i = 0; i < v.size(); ++i)
    {
        std::cout << v[i];
    }

    // Modern C++:
    for(auto& num : v)
    {
        std::cout << num;
    }
}
```

## <a name="constexpr-expressions-instead-of-macros"></a>constexpr-Ausdrücke anstelle von Makros

Makros in C und C++ sind Token, die vom Präprozessor vor der Kompilierung verarbeitet werden. Jede Instanz eines Makro Tokens wird durch den definierten Wert oder Ausdruck ersetzt, bevor die Datei kompiliert wird. Makros werden häufig bei der Programmierung im C-Stil verwendet, um konstante Werte für die Kompilierzeit zu definieren. Makros sind jedoch fehleranfällig und schwer zu debuggen. In modernen C++Erweiterungen sollten Sie [constexpr](constexpr-cpp.md) -Variablen für Kompilierzeit Konstanten bevorzugen:

```cpp
#define SIZE 10 / C-style
constexpr int size = 10; // modern C++
```

### <a name="uniform-initialization"></a>Einheitliche Initialisierung

In modernen C++können Sie die Initialisierung von Klammern für beliebige Typen verwenden. Diese Form der Initialisierung ist besonders praktisch, wenn Arrays, Vektoren oder andere Container initialisiert werden. Im folgenden Beispiel wird `v2` mit drei Instanzen von `S`initialisiert. `v3` wird mit drei Instanzen von initialisiert `S` die selbst mit geschweiften Klammern initialisiert werden. Der Compiler leitet den Typ jedes Elements auf der Grundlage des deklarierten Typs `v3`ab.

```cpp
#include <vector>

struct S
{
    std::string name;
    float num;
    S(std::string s, float f) : name(s), num(f) {}
};

int main()
{
    // C-style initialization
    std::vector<S> v;
    S s1("Norah", 2.7);
    S s2("Frank", 3.5);
    S s3("Jeri", 85.9);

    v.push_back(s1);
    v.push_back(s2);
    v.push_back(s3);

    // Modern C++:
    std::vector<S> v2 {s1, s2, s3};

    // or...
    std::vector<S> v3{ {"Norah", 2.7}, {"Frank", 3.5}, {"Jeri", 85.9} };

}
```

Weitere Informationen finden Sie unter geschweifter [Klammer Initialisierung](initializing-classes-and-structs-without-constructors-cpp.md).

## <a name="move-semantics"></a>Verschieben der Semantik

Modern C++ bietet Verschiebungs *Semantik* , sodass unnötige Speicher Kopien vermieden werden können, die in früheren Versionen der Sprache in bestimmten Situationen unvermeidlich waren. Ein *Verschiebungs Vorgang überträgt* den Besitz einer Ressource von einem Objekt zum nächsten, ohne eine Kopie zu erstellen. Bei der Implementierung einer Klasse, die eine Ressource, z. b. Heap Speicher, Datei Handles usw., besitzt, können Sie einen *bewegungskonstruktor* und Verschiebungs *Zuweisungs Operator* für die Klasse definieren. Der Compiler wählt diese speziellen Member bei der Überladungs Auflösung in Situationen aus, in denen eine Kopie nicht benötigt wird. Die Containertypen der Standard Bibliothek rufen den bewegungskonstruktor für Objekte auf, wenn eine definiert ist. Weitere Informationen finden Sie unter [bewegungskonstruktoren und Bewegungs ZuweisungsC++Operatoren ()](move-constructors-and-move-assignment-operators-cpp.md).

## <a name="lambda-expressions"></a>Lambdaausdrücke

Bei der Programmierung im C-Stil kann eine Funktion mithilfe eines *Funktions Zeigers*an eine andere Funktion übermittelt werden. Funktionszeiger sind unpraktisch zu warten und zu verstehen, da die Funktion, auf die Sie verweisen, an anderer Stelle im Quellcode definiert werden kann, weit entfernt von dem Punkt, an dem Sie aufgerufen wird. Außerdem sind Sie nicht typsicher. Modern C++ bietet Funktions Objekte, Klassen, die den [()](function-call-operator-parens.md) -Operator überschreiben, der es Ihnen ermöglicht, wie eine Funktion aufgerufen zu werden. Die einfachste Möglichkeit zum Erstellen von Funktions Objekten ist die Verwendung von Inline- [Lambda-Ausdrücken](../cpp/lambda-expressions-in-cpp.md). Im folgenden Beispiel wird gezeigt, wie ein Lambda-Ausdruck verwendet wird, um ein Funktions Objekt zu übergeben, das die `for_each`-Funktion für jedes Element im Vektor aufruft:

```cpp
    std::vector<int> v {1,2,3,4,5};
    int x = 2;
    int y = 4;
    auto result = find_if(begin(v), end(v), [=](int i) { return i > x && i < y; });
```

Der Lambda-Ausdruck `[=](int i) { return i > x && i < y; }` kann als "Funktion gelesen werden, die ein einzelnes Argument vom Typ `int` annimmt und einen booleschen Wert zurückgibt, der angibt, ob der Ausdruck true ist. Beachten Sie, dass die Variablen `x` und `y` aus dem umgebenden Kontext im Lambda-Ausdruck verwendet werden können. Der `[=]` gibt an, dass diese Variablen nach Wert *aufgezeichnet* werden. Das heißt, der Lambda Ausdruck hat seine eigenen Kopien dieser Werte.

## <a name="exceptions"></a>Ausnahmen

Als allgemeine Regel hebt modern C++ Ausnahmen anstelle von Fehlercodes als beste Möglichkeit zum melden und behandeln von Fehlerbedingungen auf. Weitere Informationen finden Sie unter [moderne C++ bewährte Methoden für Ausnahmen und Fehlerbehandlung](errors-and-exception-handling-modern-cpp.md).

## <a name="stdatomic"></a>Std:: Atomic

Verwenden Sie C++ die Standard Bibliothek [Std:: Atomic](../standard-library/atomic-structure.md) -Struktur und verwandte Typen für Kommunikationsmechanismen zwischen Threads.

## <a name="stdvariant-c17"></a>Std:: Variant (c++ 17)

Unions werden häufig bei der Programmierung im C-Stil verwendet, um Speicherplatz zu sparen, indem die Mitglieder verschiedener Typen die gleiche Speicheradresse belegen können. Allerdings sind Unions nicht typsicher und anfällig für Programmierfehler. C++ 17 führt die [Std:: Variant](../standard-library/variant-class.md) -Klasse als stabilere und sicherere Alternative zu Unions ein. Die [Std:: Visit](../standard-library/variant-functions.md#visit) -Funktion kann verwendet werden, um auf typsichere Weise auf Member eines `variant` Typs zuzugreifen.

## <a name="see-also"></a>Siehe auch

[C++-Programmiersprachenreferenz](../cpp/cpp-language-reference.md)<br/>
[Lambda-Ausdrücke](../cpp/lambda-expressions-in-cpp.md)<br/>
[C++-Standardbibliothek](../standard-library/cpp-standard-library-reference.md)<br/>
[Microsoft C++-Sprachkonformität: Tabelle](../overview/visual-cpp-language-conformance.md)