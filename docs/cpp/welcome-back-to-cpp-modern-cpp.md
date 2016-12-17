---
title: "Willkommen zur&#252;ck bei C++ (Modern C++)"
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
ms.assetid: 1cb1b849-ed9c-4721-a972-fd8f3dab42e2
caps.latest.revision: 23
caps.handback.revision: "23"
ms.author: "mblome"
manager: "ghogen"
---
# Willkommen zur&#252;ck bei C++ (Modern C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C\+\+ ist eine der am häufigsten verwendeten Programmiersprachen der Welt.  Gut geschriebene C\+\+\-Programme sind schnell und effizient.  Die Sprache ist flexibler als andere Sprachen, da sie verwendet werden kann, um eine breite Palette von Apps zu erstellen: lustige und aufregende Spiele, leistungsstarke wissenschaftliche Software, Gerätetreiber, eingebettete Programme und Windows\-Clientapps.  Seit mehr als 20 Jahren wird C\+\+ zum Lösen von Problemen wie dieser und vieler anderer.  Ihnen ist möglicherweise nicht bekannt, dass eine zunehmende Anzahl von C\+\+\-Programmierern sich von der uneleganten Programmierung im C\-Stil von einst abgewandt haben, hin zu einem modernen C\+\+.  
  
 Eine der ursprünglichen Anforderungen für C\+\+ war Abwärtskompatibilität mit der Programmiersprache C.  Inzwischen hat sich C\+\+ durch mehrere Iterationen, über C mit Klassen, die ursprüngliche C\+\+\-Sprachenspezifikation und schließlich die vielen folgenden Erweiterungen, weiter entwickelt.  Aufgrund dieses Erbes wird C\+\+ häufig als eine Programmiersprache mit vielen Paradigmen bezeichnet.  In C\+\+ können Sie rein prozedurale Programmierung im C\-Stil umsetzen, die unformatierte Zeiger, Arrays, auf NULL endende Zeichenfolgen, benutzerdefinierte Datenstrukturen und andere Funktionen umfasst, die möglicherweise große Leistung ermöglichen, jedoch Fehler und Komplexität erzeugen können.  Da Programmierung im C\-Stil voller Fehlerquellen wie diesen steckt, bestand eins der Ziele bei Erschaffung von C\+\+ im Erstellen typsicherer Programme, die leichter zu schreiben, zu erweitern und zu warten sind.  Bereitwillig wurden für C\+\+ schon früh solche Paradigmen wie die objektorientierte Programmierung angenommen.  Im Laufe der Jahre sind der Sprache Funktionen zusammen mit intensiv getesteten Standardbibliotheken von Datenstrukturen und Algorithmen hinzugefügt worden.  Aufgrund dieser Ergänzungen wurde der moderne C\+\+\-Stil möglich.  
  
 Modernes C\+\+ betont:  
  
-   Stapelbasierte Bereiche anstelle von Heaps oder statischen globalen Bereichen.  
  
-   Automatischer Typrückschluss antelle von expliziten Typnamen.  
  
-   Intelligente Zeiger anstelle von unformatierten Zeigern.  
  
-   `std::string` und `std::wstring`\-Typen \(siehe [\<string\>](../standard-library/string.md)\), anstelle von unformatierten `char[]`\-Arrays.  
  
-   [Standardvorlagenbibliothek](../standard-library/cpp-standard-library-header-files.md) \(STL\)\-Container wie `vector`, `list` und `map` anstelle von unformatierten Arrays oder benutzerdefinierten Containern.  Siehe [\<vector\>](../standard-library/vector.md), [\<list\>](../standard-library/list.md) und [\< Zuordnung \>](../standard-library/map.md).  
  
-   [STL\-Algorithmen](../standard-library/algorithm.md) anstelle von manuell Codierten.  
  
-   Ausnahmen zum Melden und Behandeln von Fehlerzuständen.  
  
-   Sperrenfreie Kommunikation zwischen Threads mithilfe von STL `std::atomic<>` \(siehe [\<atomic\>](../standard-library/atomic.md)\), anstelle anderer Mechanismen zur Kommunikation zwischen Threads.  
  
-   Inline [Lambda\-Funktionen](../cpp/lambda-expressions-in-cpp.md) anstelle von kleinen separat implementierten Funktionen.  
  
-   Bereichsbasiert, damit Schleifen robustere Schleifen schreiben, die mit Arrays, STL\-Containern und [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]\-Auflistungen in der Form `for ( for-range-declaration : expression )` funktionieren.  Dies ist ein Bestandteil der Kernsprachunterstützung.  Weitere Informationen finden Sie unter [Bereichsbasiert für Anweisung \(C\+\+\)](../cpp/range-based-for-statement-cpp.md).  
  
 Die Programmiersprache C\+\+ selbst hat sich auch entwickelt.  Vergleichen Sie die folgenden Codeausschnitte.  In diesem Ausschnitt wird ursprünglicher C\+\+\-Code verwendet:  
  
```cpp  
  
// circle and shape are user-defined types  
circle* p = new circle( 42 );   
vector<shape*> v = load_shapes();  
  
for( vector<circle*>::iterator i = v.begin(); i != v.end(); ++i ) {  
    if( *i && **i == *p )  
        cout << **i << “ is a match\n”;  
}  
  
for( vector<circle*>::iterator i = v.begin();  
        i != v.end(); ++i ) {  
    delete *i; // not exception safe  
}  
  
delete p;  
  
```  
  
 In diesem wird gezeigt, wie die gleiche Aufgabe in modernem C\+\+ erreicht wird:  
  
```cpp  
  
#include <memory>  
#include <vector>  
// ...  
// circle and shape are user-defined types  
auto p = make_shared<circle>( 42 );  
vector<shared_ptr<shape>> v = load_shapes();  
  
for_each( begin(v), end(v), [&](const shared_ptr<shape>& s) {  
    if( s && *s == *p )  
        cout << *s << " is a match\n";  
} );  
  
```  
  
 In modernem C\+\+ ist die Verwendung der Ausnahmebehandlung "neu\/löschen" oder "explizit" nicht erforderlich, da Sie statt dessen intelligente Zeiger nutzen können.  Wenn Sie die `auto`\-Typableitung und [Lambda\-Funktion](../cpp/lambda-expressions-in-cpp.md) verwenden, können Sie Code schneller und kompakter schreiben, und ihn besser verstehen.  Die `for_each`\-Schleife ist klarer, einfacher anzuwenden und weniger anfällig für unbeabsichtigte Fehler als eine `for`\-Schleife.  Sie können Bausteine mit minimalen Codezeilen verbinden, um die App zu schreiben.  Außerdem können Sie diesen Code ausnahme\- und arbeitsspeichersicher erstellen und haben keinen Zuordnungs\-\/Freigabe\- oder Fehlercodes zu verarbeiten.  
  
 Modernes C\+\+ enthält zwei Arten von Polymorphie: Kompilierzeit, durch Vorlagen, und Laufzeit, durch Vererbung und Virtualisierung.  Sie können die beiden Polymorphiearten mit großer Wirkungen kombinieren.  Bei der STL\-Vorlage `shared_ptr` werden interne virtuelle Methoden zum Erreichen der anscheinend mühelosen Typlöschung verwendet.  Doch überbeanspruchen Sie die Virtualisierung für Polymorphie nicht, wenn eine Vorlage die bessere Wahl ist.  Vorlagen können sehr leistungsstark sein.  
  
 Wenn Sie von einer anderen Sprache her zu C\+\+ kommen, insbesondere bei einer verwalteten Sprache mit größtenteils Verweistypen und nur wenigen Werttypen, wissen Sie, dass C\+\+\-Klassen standardmäßig Werttypen sind.  Sie können sie allerdings als Verweistypen angeben, um polymorphes Verhalten zu ermöglichen, das objektorientierte Programmierung unterstützt.  Eine hilfreiche Sichtweise: Bei Werttypen geht es mehr um Arbeitsspeicher und Layoutsteuerung, bei Verweistypen geht es dagegen mehr um Basisklassen und virtuelle Funktionen zur Unterstützung von Polymorphie.  Standardmäßig können Werttypen kopiert werden. Sie verfügen jeweils über einen Kopierkonstruktor und ein Kopierzuweisungsoperator.  Bei der Angabe eines Verweistyps darf die Klasse nicht kopiert werden können. Deaktivieren Sie den Kopierkonstruktor und den Kopierzuweisungsoperator und verwenden Sie einen virtuellen Destruktor, der Polymorphie unterstützt.  Bei Werttypen geht es außerdem um die Inhalte, von denen, wenn sie kopiert werden, zwei unabhängige Werte zugewiesen werden, die getrennt geändert werden können.  Bei Referenztypen geht es allerdings um Identität \(welche Art von Objekt es ist\). Aus diesem Grund werden sie manchmal als polymorphe Typen bezeichnet.  
  
 C\+\+ erlebt eine Renaissance, da die Leistungsfähigkeit wieder über Allem steht.  Sprachen wie Java und C\# sind gut, wenn Programmiererproduktivität wichtig ist, aber ihren Einschränkungen werden deutlich, wenn Leistungsfähigkeit entscheidend ist.  Bei Effizienz und hohe Leistungsfähigkeit, besonders auf Geräten, deren Hardware eingeschränkt ist, ist das moderne C\+\+ unschlagbar.  
  
 Es ist nicht nur eine moderne Sprache, auch die Entwicklungstools sind modern.  Mit [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] werden alle Teile des Entwicklungszyklus robust und effizient.  Das schließt Tools der Anwendungslebenszyklus\-Verwaltung \(ALM\), IDE\-Erweiterungen wie IntelliSense, benutzerfreundliche Toolmechanismen wie XAML und das Erstellen, Debuggen sowie viele weitere Tools ein.  
  
 Die Artikel in diesem Teil der Dokumentation bieten übergeordnete Richtlinien und bewährte Methoden für die wichtigsten Funktionen und Techniken zum Schreiben moderner C\+\+\-Programmen.  
  
-   [Unterstützung für C\+\+11\/14\/17\-Funktionen](../cpp/support-for-cpp11-14-17-features-modern-cpp.md)  
  
-   [C\+\+\-Typsystem](../cpp/cpp-type-system-modern-cpp.md)  
  
-   [Einheitliche Initialisierung und Delegierung von Konstruktoren](../cpp/uniform-initialization-and-delegating-constructors.md)  
  
-   [Objektlebenszeit und Ressourcenverwaltung](../cpp/object-lifetime-and-resource-management-modern-cpp.md)  
  
-   [Objekteigene Ressourcen \(RAII\)](../cpp/objects-own-resources-raii.md)  
  
-   [Intelligente Zeiger](../cpp/smart-pointers-modern-cpp.md)  
  
-   [pimpl für Compilierungszeitkapselung](../cpp/pimpl-for-compile-time-encapsulation-modern-cpp.md)  
  
-   [Container](../cpp/containers-modern-cpp.md)  
  
-   [Algorithmen](../cpp/algorithms-modern-cpp.md)  
  
-   [Formatieren von Zeichenfolgen und Ein\-\/Ausgaben](../cpp/string-and-i-o-formatting-modern-cpp.md)  
  
-   [Behandeln von Fehlern und Ausnahmen](../cpp/errors-and-exception-handling-modern-cpp.md)  
  
-   [Portabilität an ABI\-Grenzen](../cpp/portability-at-abi-boundaries-modern-cpp.md)  
  
 Weitere Informationen finden Sie im StackOverflow\-Artikel [Welche C\+\+\-Idiome in C\+\+11 veraltet sind](http://go.microsoft.com/fwlink/?LinkId=402836)  
  
## Siehe auch  
 [C\+\+\-Sprachreferenz](../cpp/cpp-language-reference.md)   
 [Lambda\-Ausdrücke](../cpp/lambda-expressions-in-cpp.md)   
 [C\+\+\-Standardbibliothek](../standard-library/cpp-standard-library-reference.md)