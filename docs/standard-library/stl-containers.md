---
title: "STL Containers"
ms.custom: na
ms.date: "12/03/2016"
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
  - "Die C++-Standardbibliothek vorlangenklassencontainer"
  - "STL-Container"
ms.assetid: 8e915ca1-19ba-4f0d-93c8-e2c3bfd638eb
caps.latest.revision: 29
caps.handback.revision: "29"
ms.author: "corob"
manager: "ghogen"
---
# STL Containers
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Standardbibliothek stellt unterschiedliche typsichere Container zum Speichern verknüpfter Objekte bereit. Container sind Klassenvorlagen; Beim Deklarieren einer Containervariablen wird der Typ der Elemente angegeben, die der Container enthalten soll. Container können mit Initialisiererlisten erstellt werden. Sie verfügen über Memberfunktionen zum Hinzufügen und Entfernen von Elementen und Ausführen anderer Vorgänge.  
  
 Sie Durchlaufen der Elemente in einem Container und Zugriff auf die einzelnen Elemente mit [Iteratoren](../standard-library/iterators.md). Iteratoren können explizit mithilfe ihrer Memberfunktionen, Operatoren sowie globalen Funktionen verwendet werden. Sie können sie auch implizit verwenden, z. B. mit einer range-for-Schleife. Iteratoren für alle STL-Containern haben eine gemeinsame Schnittstelle, aber jeder Container definiert seine eigenen speziellen Iteratoren.  
  
 Container können in drei Kategorien unterteilt werden: Sequenzcontainer, assoziative Container und Containeradapter.  
  
##  <a name="a-namesequencecontainersa-sequence-containers"></a><a name="sequence_containers"></a> Sequenzcontainer  
 Sequenzcontainer wahren die Reihenfolge der von Ihnen angegebenen eingefügten Elemente.  
  
 Ein `vector`-Container verhält sich wie ein Array, kann jedoch nach Bedarf automatisch erweitert werden. Er wird mit direktem Zugriff bzw. zusammenhängend gespeichert, und ist in der Länge hochgradig flexibel. Aus diesen und weiteren Gründen ist `vector` der bevorzugte Sequenzcontainer für die meisten Anwendungen. Verwenden Sie einen Vektor, wenn Sie sich nicht sicher sind, welchen Sequenzcontainertyp Sie verwenden sollen. Weitere Informationen finden Sie unter [vector-Klasse](vector%20Class.md).  
  
 Ein `array`-Container weist einige der Vorteile von `vector` auf, aber er ist in der Länge nicht so flexibel. Weitere Informationen finden Sie unter [array-Klasse](../standard-library/array-class-stl.md).  
  
 Ein `deque`-Container (doppelseitige Warteschlange) ermöglichen schnelles Einfügen und Löschen am Anfang und Ende des Containers. Er bietet die Vorteile von direktem Zugriff und flexibler Länge von `vector`, ist aber nicht zusammenhängend. Weitere Informationen finden Sie unter [Deque-Klasse](../standard-library/deque-class.md).  
  
 Ein `list`-Container ist eine doppelt verknüpfte Liste, die bidirektionalen Zugriff, schnelles Einfügen und Löschen im gesamten Container ermöglicht, aber direkter Zugriff auf ein Element im Container ist nicht möglich. Weitere Informationen finden Sie unter [list-Klasse](../standard-library/list-class.md).  
  
 Ein `forward_list`-Container ist eine einfach verknüpfte Liste. Er ist die Version mit Vorwärtszugriff von `list`. Weitere Informationen finden Sie unter [Forward_list-Klasse](../standard-library/forward-list-class.md).  
  
## <a name="associative-containers"></a>Assoziative Container  
 In assoziativen Containern werden Elemente in einer vordefinierten Reihenfolge eingefügt, z. B. sortiert aufsteigend. Unsortierte assoziative Container sind ebenfalls verfügbar. Assoziative Container können in zwei Teilbereiche gruppiert werden: Zuordnungen und Sätze.  
  
 `map` (manchmal auch als ein Wörterbuch bezeichnet) besteht aus einem Schlüssel-Wert-Paar. Der Schlüssel wird zum Sortieren der Reihenfolge verwendet, und der Wert wird dem Schlüssel zugeordnet. Z. B. kann `map` eindeutige Schlüssel enthalten, die jedes einzelne Wort in einem Text und die entsprechenden Werte darstellen, die die Häufigkeit darstellen, mit der jedes Wort im Text angezeigt wird. Die unsortierte Version von `map` ist `unordered_map`. Weitere Informationen finden Sie unter [map-Klasse](../standard-library/map-class.md) und [Unordered_map-Klasse](../standard-library/unordered-map-class.md).  
  
 Ein `set`-Element ist lediglich ein aufsteigender Container eindeutiger Elemente. Der Wert ist auch gleichzeitig der Schlüssel. Die unsortierte Version von `set` ist `unordered_set`. Weitere Informationen finden Sie unter [set-Klasse](../standard-library/set-class.md) und [Unordered_set-Klasse](../standard-library/unordered-set-class.md).  
  
 Sowohl `map` als auch `set` ermöglichen das Einfügen nur einer Instanz eines Schlüssels oder Elements in den Container. Wenn mehrere Instanzen der Elemente erforderlich sind, verwenden Sie `multimap` oder `multiset`. Die unsortierten Versionen sind `unordered_multimap` und `unordered_multiset`. Weitere Informationen finden Sie unter [Mehrfachzuordnungsklasse](../standard-library/multimap-class.md), [Unordered_multimap-Klasse](../standard-library/unordered-multimap-class.md), [Multimengenklasse](../standard-library/multiset-class.md), und [Unordered_multiset-Klasse](../standard-library/unordered-multiset-class.md).  
  
 Bei sortierten Zuordnungen und Sätzen werden bidirektionale Iteratoren unterstützt, und bei den unsortierten Entsprechungen werden Vorwärtsiteratoren unterstützt. Weitere Informationen finden Sie unter [Iteratoren](../standard-library/iterators.md).  
  
### <a name="heterogeneous-lookup-in-associative-containers-c14"></a>Heterogenes Nachschlagen in assoziativen Containern (C++14)  
 Die sortierten assoziativen Container (Map, Multimap, Set und Multiset) unterstützen nun das heterogene Nachschlagen, d. h. Sie müssen nicht länger genau denselben Objekttyp als Schlüssel oder Element in Memberfunktionen wie `find()` und `lower_bound()` übergeben. Stattdessen können Sie einen beliebigen Typ übergeben, für den ein überladener `operator<` definiert ist, mit dem ein Vergleich mit dem Schlüsseltyp aktiviert wird.  
  
 Heterogenes Nachschlagen wird auf Opt-in-Basis aktiviert, wenn Sie den `std::less<>`- oder `std::greater<>`-„diamond functor“-Vergleichsoperator beim Deklarieren der Containervariablen angeben, wie im Folgenden dargestellt:  
  
```  
std::set<BigObject, std::less<>> myNewSet;  
```  
  
 Bei Verwendung des Standardvergleichsoperators weist der Container dasselbe Verhalten wie in C++11 und früheren Versionen auf.  
  
 Das folgende Beispiel zeigt, wie ein `operator<` überladen werden kann, damit `std::set`-Benutzer Suchvorgänge durch Übergeben einer kurzen Zeichenfolge ausführen können, die mit jedem `BigObject::id`-Member des Objekts verglichen wird.  
  
```  
#include <set>  
#include <string>  
#include <iostream>  
#include <functional>  
  
using namespace std;  
  
class BigObject  
{  
public:  
    string id;  
    explicit BigObject(const string& s) : id(s) {}  
    bool operator< (const BigObject& other) const  
    {  
        return this->id < other.id;  
    }  
  
    // Other members....  
};  
  
inline bool operator<(const string& otherId, const BigObject& obj)  
{  
    return otherId < obj.id;  
}  
  
inline bool operator<(const BigObject& obj, const string& otherId)  
{  
    return obj.id < otherId;  
}  
  
int main()  
{  
    // Use C++14 brace-init syntax to invoke BigObject(string).  
    // The s suffix invokes string ctor. It is a C++14 user-defined  
    // literal defined in <string>  
    BigObject b1{ "42F"s };   
    BigObject b2{ "52F"s };  
    BigObject b3{ "62F"s };  
    set<BigObject, less<>> myNewSet; // C++14  
    myNewSet.insert(b1);  
    myNewSet.insert(b2);  
    myNewSet.insert(b3);  
    auto it = myNewSet.find(string("62F"));  
    if (it != myNewSet.end())  
        cout << "myNewSet element = " << it->id << endl;   
    else  
        cout << "element not found " << endl;  
  
    // Keep console open in debug mode:  
    cout << endl << "Press Enter to exit.";  
    string s;  
    getline(cin, s);  
    return 0;  
}  
  
//Output: myNewSet element = 62F  
  
```  
  
 Folgende Memberfunktionen in Map, Multimap, Set und Multiset wurden zur Unterstützung vom heterogenen Nachschlagen überlastet:  
  
1.  find  
  
2.  count  
  
3.  lower_bound  
  
4.  upper_bound  
  
5.  equal_range  
  
## <a name="container-adapters"></a>Containeradapter  
 Ein Containeradapter ist die Variante einer Sequenz oder eines assoziativen Containers, die die Schnittstelle zwecks Einfachheit und Verständlichkeit einschränkt. Bei Containeradaptern werden keine Iteratoren unterstützt.  
  
 Ein `queue`-Container folgt der FIFO-Semantik (first in, first out). Das erste Element *abgelegt*– d. h. in die Warteschlange eingefügt – ist das erste, *geholt*– d. h. aus der Warteschlange entfernt. Weitere Informationen finden Sie unter [queue-Klasse](../standard-library/queue-class.md).  
  
 Ein `priority_queue`-Container wird so organisiert, dass das Element, das über den höchsten Wert verfügt, immer zuerst in der Warteschlange steht. Weitere Informationen finden Sie unter [Priority_queue-Klasse](../standard-library/priority-queue-class.md).  
  
 Ein `stack`-Container folgt der LIFO-Semantik (last in, first out). Das letzte Element, das auf dem Stapel abgelegt wird, ist das erste entnommene Element. Weitere Informationen finden Sie unter [stack-Klasse](../standard-library/stack-class.md).  
  
 Da Containeradapter keine Iteratoren unterstützen, können sie nicht mit STL-Algorithmen verwendet werden. Weitere Informationen finden Sie unter [Algorithmen](../standard-library/algorithms.md).  
  
## <a name="requirements-for-container-elements"></a>Anforderungen für Containerelemente  
 Im Allgemeinen können Elemente, die in einen STL-Container eingefügt werden, fast jeden Objekttyp haben, wenn sie kopiert werden können. Nur verschiebbare Elemente – z. B. `vector<unique_ptr<T>>`, die mithilfe von `unique_ptr<>` erstellt werden, funktionieren, solange keine Memberfunktionen aufgerufen werden, die versuchen, sie zu kopieren.  
  
 Vom Destruktor darf keine Ausnahme ausgelöst werden.  
  
 Sortierte assoziative Container (früher im Artikel beschrieben) müssen einen öffentlich definierten Vergleichsoperator aufweisen. (Standardmäßig ist `operator<` der Operator, allerdings werden auch Typen, die nicht mit `operator<` arbeiten, unterstützt.  
  
 Einige Vorgänge in Containern könnten auch einen öffentlichen Standardkonstruktor und einen öffentlichen Äquivalenzoperator erfordern. Beispielsweise benötigen die unsortierten assoziativen Container eine Unterstützung für Gleichheit und Hashverfahren.  
  
## <a name="accessing-container-elements"></a>Zugreifen auf Containerelemente  
 Auf Containerelemente wird mithilfe von Iteratoren zugegriffen. Weitere Informationen finden Sie unter [Iteratoren](../standard-library/iterators.md).  
  
> [!NOTE]
>  Sie können auch [Bereichsbasierte for-Schleifen](../cpp/range-based-for-statement-cpp.md) um STL-Auflistungen zu durchlaufen.  
  
## <a name="comparing-containers"></a>Vergleichen von Containern  
 Alle Container überladen den Operator „==“ zum Vergleichen von zwei Containern desselben Typs, die den gleichen Elementtyp aufweisen. Können Sie zum Vergleichen eines Vektors == \< Zeichenfolge> mit einem anderen Vektor \< Zeichenfolge>, aber Sie können es verwenden, um einen Vektor vergleichen \< Zeichenfolge> zu einer Liste \< Zeichenfolge> oder einen Vektor \< Zeichenfolge> in einen Vektor \< Char * >.  In C ++ 98/03 können [Std:: Equal](../Topic/equal.md) oder [Std:: Mismatch](../Topic/mismatch.md) unterschiedlicher Containertypen und/oder Elementtypen vergleichen. Sie können auch verwenden, in C ++ 11 [is_permutation](../Topic/is_permutation.md). In all diesen Fällen gehen die Funktionen jedoch davon aus, dass die Container die gleiche Länge aufweisen. Wenn der zweite Bereich kürzer als der erste ist, kommt es zu nicht definiertem Verhalten. Wenn der zweite Bereich länger ist, sind die Ergebnisse möglicherweise trotzdem falsch, da der Vergleich nie über das Ende des ersten Bereichs hinaus fortgesetzt wird.  
  
### <a name="comparing-dissimilar-containers-c14"></a>Vergleichen unterschiedlicher Container (C++14)  
 In C ++ 14 und höher können unterschiedliche Container und/oder Elementtypen mit verglichen eines der [Std:: Equal](../Topic/equal.md), [Std:: Mismatch](../Topic/mismatch.md), oder [is_permutation](../Topic/is_permutation.md) -funktionsüberladungen, die zwei vollständige Bereiche. Mit diesen Überladungen können Sie Container mit unterschiedlicher Länge vergleichen. Diese Überladungen sind weniger für Benutzerfehler anfällig und sind beim Vergleichen von Containern mit unterschiedlicher Länge so optimiert, dass sie in konstanter Zeit FALSE zurückgeben. Daher ist es empfehlenswert, wenn (1) Sie haben einen klaren Grund nicht zu, oder (2) Sie verwenden, verwenden Sie diese Überladung einen [Std:: List](../standard-library/list-class.md) Container, der nicht aus den Bereichen Optimierungen profitiert.  
  
## <a name="see-also"></a>Siehe auch  
 [Container](../cpp/containers-modern-cpp.md)   
 [Standard Template Library](../misc/standard-template-library.md)   
 [\< Sample-Container>](../standard-library/sample-container.md)   
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)

