---
title: Willkommen zurück bei C++ (Modern C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 1cb1b849-ed9c-4721-a972-fd8f3dab42e2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 220c8f27aec52fe707e0482eb041ea71c5bd8291
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2018
ms.locfileid: "37939376"
---
# <a name="welcome-back-to-c-modern-c"></a>Willkommen zurück bei C++ (Modern C++)
C++ ist eine der am häufigsten verwendeten Programmiersprachen der Welt. Gut geschriebene C++-Programme sind schnell und effizient. Die Sprache ist flexibler als andere Sprachen, da sie verwendet werden kann, um eine breite Palette von Apps zu erstellen: lustige und aufregende Spiele, leistungsstarke wissenschaftliche Software, Gerätetreiber, eingebettete Programme und Windows-Clientapps. Seit mehr als 20 Jahren wird C++ zum Lösen von Problemen wie dieser und vieler anderer. Ihnen ist möglicherweise nicht bekannt, dass eine zunehmende Anzahl von C++-Programmierern sich von der uneleganten Programmierung im C-Stil von einst abgewandt haben, hin zu einem modernen C++.  
  
 Eine der ursprünglichen Anforderungen für C++ war Abwärtskompatibilität mit der Programmiersprache C. Inzwischen hat sich C++ durch mehrere Iterationen, über C mit Klassen, die ursprüngliche C++-Sprachenspezifikation und schließlich die vielen folgenden Erweiterungen, weiter entwickelt. Aufgrund dieses Erbes wird C++ häufig als eine Programmiersprache mit vielen Paradigmen bezeichnet. In C++ können Sie rein prozedurale Programmierung im C-Stil umsetzen, die unformatierte Zeiger, Arrays, auf NULL endende Zeichenfolgen, benutzerdefinierte Datenstrukturen und andere Funktionen umfasst, die möglicherweise große Leistung ermöglichen, jedoch Fehler und Komplexität erzeugen können.  Da Programmierung im C-Stil voller Fehlerquellen wie diesen steckt, bestand eins der Ziele bei Erschaffung von C++ im Erstellen typsicherer Programme, die leichter zu schreiben, zu erweitern und zu warten sind. Bereitwillig wurden für C++ schon früh solche Paradigmen wie die objektorientierte Programmierung angenommen. Im Laufe der Jahre sind der Sprache Funktionen zusammen mit intensiv getesteten Standardbibliotheken von Datenstrukturen und Algorithmen hinzugefügt worden. Aufgrund dieser Ergänzungen wurde der moderne C++-Stil möglich.  
  
 Modernes C++ betont:  
  
-   Stapelbasierte Bereiche anstelle von Heaps oder statischen globalen Bereichen.  
  
-   Automatischer Typrückschluss antelle von expliziten Typnamen.  
  
-   Intelligente Zeiger anstelle von unformatierten Zeigern.  
  
-   `std::string` und `std::wstring` Typen (finden Sie unter [ \<Zeichenfolge >](../standard-library/string.md)) anstelle von unformatierten `char[]` Arrays.  
  
-   [C++-Standardbibliothek](../standard-library/cpp-standard-library-header-files.md) -Container wie `vector`, `list`, und `map` anstelle von unformatierten Arrays oder benutzerdefinierten Containern. Finden Sie unter [ \<Vektor >](../standard-library/vector.md), [ \<Liste >](../standard-library/list.md), und [ \<Map >](../standard-library/map.md).  
  
-   C++-Standardbibliothek [Algorithmen](../standard-library/algorithm.md) anstelle von manuell codierten solche.  
  
-   Ausnahmen zum Melden und Behandeln von Fehlerzuständen.  
  
-   Sperrenfreie Kommunikation zwischen Threads mithilfe C++-Standardbibliothek `std::atomic<>` (finden Sie unter [ \<atomic >](../standard-library/atomic.md)) anstelle von anderen Mechanismen für die Kommunikation zwischen Threads.  
  
-   Inline [Lambda-Funktionen](../cpp/lambda-expressions-in-cpp.md) anstelle von kleinen separat implementierten Funktionen.  
  
-   Bereichsbasierte for-Schleifen robustere Schleifen schreiben, die Arbeit mit Arrays, C++-Standardbibliothek-Containern und Windows-Runtime-Auflistungen in der Form `for ( for-range-declaration : expression )`. Dies ist ein Bestandteil der Kernsprachunterstützung. Weitere Informationen finden Sie unter [bereichsbasiert für Anweisung (C++)](../cpp/range-based-for-statement-cpp.md).  
  
 Die Programmiersprache C++ selbst hat sich auch entwickelt. Vergleichen Sie die folgenden Codeausschnitte. In diesem Ausschnitt wird ursprünglicher C++-Code verwendet:  
  
```cpp  

#include <vector>

void f()
{
    // Assume circle and shape are user-defined types  
    circle* p = new circle( 42 );   
    vector<shape*> v = load_shapes();  

    for( vector<circle*>::iterator i = v.begin(); i != v.end(); ++i ) {  
        if( *i && **i == *p )  
            cout << **i << " is a match\n";  
    }  

    // CAUTION: If v's pointers own the objects, then you
    // must delete them all before v goes out of scope.
    // If v's pointers do not own the objects, and you delete
    // them here, any code that tries to dereference copies
    // of the pointers will cause null pointer exceptions.
    for( vector<circle*>::iterator i = v.begin();  
            i != v.end(); ++i ) {  
        delete *i; // not exception safe  
    }  

    // Don't forget to delete this, too.  
    delete p;  
} // end f()
```

 In diesem wird gezeigt, wie die gleiche Aufgabe in modernem C++ erreicht wird:  
  
```cpp

#include <memory>  
#include <vector>  

void f()
{
    // ...  
    auto p = make_shared<circle>( 42 );  
    vector<shared_ptr<shape>> v = load_shapes();  

    for( auto& s : v ) 
    {  
        if( s && *s == *p )
        {
            cout << *s << " is a match\n";
        }
    }
}

```

 In modernem C++ ist die Verwendung der Ausnahmebehandlung "neu/löschen" oder "explizit" nicht erforderlich, da Sie statt dessen intelligente Zeiger nutzen können. Bei Verwendung der **automatisch** typableitung und [Lambda-Funktion](../cpp/lambda-expressions-in-cpp.md), Sie können Code schneller und schreiben. soll sie festgezogen und ihn besser verstehen. Und eine bereichsbasierte **für** Schleife ist sauberer, einfacher zu verwenden und weniger anfällig für unbeabsichtigte Fehler als eine C-Stil **für** Schleife. Sie können Bausteine mit minimalen Codezeilen verbinden, um die App zu schreiben. Außerdem können Sie diesen Code ausnahme- und arbeitsspeichersicher erstellen und haben keinen Zuordnungs-/Freigabe- oder Fehlercodes zu verarbeiten.  
  
 Modernes C++ enthält zwei Arten von Polymorphie: Kompilierzeit, durch Vorlagen, und Laufzeit, durch Vererbung und Virtualisierung. Sie können die beiden Polymorphiearten mit großer Wirkungen kombinieren. Die C++-Standardbibliothek-Vorlage `shared_ptr` interne virtuelle Methoden zum Erreichen der anscheinend mühelosen typlöschung verwendet. Doch überbeanspruchen Sie die Virtualisierung für Polymorphie nicht, wenn eine Vorlage die bessere Wahl ist. Vorlagen können sehr leistungsstark sein.  
  
 Wenn Sie von einer anderen Sprache her zu C++ kommen, insbesondere bei einer verwalteten Sprache mit größtenteils Verweistypen und nur wenigen Werttypen, wissen Sie, dass C++-Klassen standardmäßig Werttypen sind. Sie können sie allerdings als Verweistypen angeben, um polymorphes Verhalten zu ermöglichen, das objektorientierte Programmierung unterstützt. Eine hilfreiche Sichtweise: Bei Werttypen geht es mehr um Arbeitsspeicher und Layoutsteuerung, bei Verweistypen geht es dagegen mehr um Basisklassen und virtuelle Funktionen zur Unterstützung von Polymorphie. Standardmäßig können Werttypen kopiert werden. Sie verfügen jeweils über einen Kopierkonstruktor und ein Kopierzuweisungsoperator. Bei der Angabe eines Verweistyps darf die Klasse nicht kopiert werden können. Deaktivieren Sie den Kopierkonstruktor und den Kopierzuweisungsoperator und verwenden Sie einen virtuellen Destruktor, der Polymorphie unterstützt. Bei Werttypen geht es außerdem um die Inhalte, von denen, wenn sie kopiert werden, zwei unabhängige Werte zugewiesen werden, die getrennt geändert werden können. Bei Referenztypen geht es allerdings um Identität (welche Art von Objekt es ist). Aus diesem Grund werden sie manchmal als polymorphe Typen bezeichnet.  
  
 C++ erlebt eine Renaissance, da die Leistungsfähigkeit wieder über Allem steht. Sprachen wie Java und C# sind gut, wenn Programmiererproduktivität wichtig ist, aber ihren Einschränkungen werden deutlich, wenn Leistungsfähigkeit entscheidend ist. Bei Effizienz und hohe Leistungsfähigkeit, besonders auf Geräten, deren Hardware eingeschränkt ist, ist das moderne C++ unschlagbar.  
  
 Es ist nicht nur eine moderne Sprache, auch die Entwicklungstools sind modern. Mit [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] werden alle Teile des Entwicklungszyklus robust und effizient. Das schließt Tools der Anwendungslebenszyklus-Verwaltung (ALM), IDE-Erweiterungen wie IntelliSense, benutzerfreundliche Toolmechanismen wie XAML und das Erstellen, Debuggen sowie viele weitere Tools ein.  
  
 Die Artikel in diesem Teil der Dokumentation bieten übergeordnete Richtlinien und bewährte Methoden für die wichtigsten Funktionen und Techniken zum Schreiben moderner C++-Programmen.  
  
-   [C++-Typsystem](../cpp/cpp-type-system-modern-cpp.md)  
  
-   [Einheitliche Initialisierung und Delegierung von Konstruktoren](../cpp/uniform-initialization-and-delegating-constructors.md)  
  
-   [Objektlebenszeit und Ressourcenverwaltung](../cpp/object-lifetime-and-resource-management-modern-cpp.md)  
  
-   [Objekteigene Ressourcen (RAII)](../cpp/objects-own-resources-raii.md)  
  
-   [Intelligente Zeiger](../cpp/smart-pointers-modern-cpp.md)  
  
-   [Pimpl für Kompilierzeitkapselung](../cpp/pimpl-for-compile-time-encapsulation-modern-cpp.md)  
  
-   [Container](../cpp/containers-modern-cpp.md)  
  
-   [Algorithmen](../cpp/algorithms-modern-cpp.md)  
  
-   [Zeichenfolgen- und e/a-Formatierung (Modern C++)](../cpp/string-and-i-o-formatting-modern-cpp.md)  
  
-   [Fehler- und Ausnahmebehandlung](../cpp/errors-and-exception-handling-modern-cpp.md)  
  
-   [Portabilität an ABI-Grenzen](../cpp/portability-at-abi-boundaries-modern-cpp.md)  
  
 Weitere Informationen finden Sie im StackOverflow-Artikel [welche C++-Idiome in C ++ 11 als veraltet markiert werden](http://go.microsoft.com/fwlink/p/?linkid=402836)  
  
## <a name="see-also"></a>Siehe auch  
 [C++ Language Reference (C++-Programmiersprachenreferenz)](../cpp/cpp-language-reference.md)   
 [Lambda-Ausdrücke](../cpp/lambda-expressions-in-cpp.md)   
 [C++-Standardbibliothek](../standard-library/cpp-standard-library-reference.md)  
 [Visual C++-Sprachkonformität](../visual-cpp-language-conformance.md)  
