---
title: "Objektlebenszeit und Ressourcenverwaltung (Modern C++)"
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
ms.assetid: 8aa0e1a1-e04d-46b1-acca-1d548490700f
caps.latest.revision: 18
caps.handback.revision: "18"
ms.author: "mblome"
manager: "ghogen"
---
# Objektlebenszeit und Ressourcenverwaltung (Modern C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Anders als verwaltete Sprachen C\+\+ verfügt nicht Garbage Collection \(GC\), die automatisch NO \- lang\-verwendete Speicherressourcen freigibt, während ein Programm ausgeführt wird.  In C\+\+ wird mithilfe der Ressourcenverwaltungs\- direkt verknüpft, um Lebensdauer gesammelt.  Dieses Dokument beschreibt die Faktoren, die Objektlebensdauer in C\+\+ beeinflussen und wie es verwaltet.  
  
 C\+\+ verfügt nicht GC, hauptsächlich da nicht NichtArbeitsspeicherressourcen behandelt.  Nur deterministische Destruktoren wie die C\+\+ können Arbeitsspeicher\- und NichtArbeitsspeicherressourcen gleichmäßig behandeln.  GC verfügt auch andere Probleme, z höheren Mehraufwand im Arbeitsspeicher und CPU\-Auslastung IN Stelle.  Aber Universalität ist ein grundlegendes Problem, das nicht von Optimierungen kluge gemindert werden kann.  
  
## Konzepte  
 Eine wichtige Aufgabe in der ObjektLebensdauerverwaltung ist der Kapselung\-werauch immer mit einem Objekt muss nicht wissen, welche Ressourcen die Objekt besitzt oder wie die loswird oder sogar, ob es dabei Ressourcen vorhanden besitzt.  müssen Sie das Objekt nur zerstören.  Die C\+\+\-Kernsprache wurde entwickelt, um in umgekehrter Reihenfolge sicherzustellen, dass Objekte zum richtigen Zeiten d. h zerstört werden z Blöcke beendet werden, von der Konstruktion.  Wenn ein Objekt zerstört wird, werden seine Wurzeln und Member in einer bestimmten Bestellung zerstört.  Die Sprache zerstört Objekte automatisch, es sei denn, Sie spezielle Aufgaben wie, die die Schritte Heapreservierung oder Platzierung neu sind.  Beispielsweise wie [intelligenten Zeiger](../cpp/smart-pointers-modern-cpp.md)`unique_ptr` und `shared_ptr` und Standardvorlagenbibliotheks \(stl\)\- Container, wie `vector`, `new`\/`delete` sowie `new[]`\/`delete[]` in Objekten kapseln, die Destruktoren besitzen.  Daher ist es so wichtig, intelligenterer Verweise und STL\-Container zu verwenden.  
  
 Ein anderes wichtiges Konzept in der Verwaltung der Lebensdauer: Destruktoren.  Destruktoren Ressourcenversion kapseln.  \(Die am häufigsten verwendete Zeichen ist RRID, ist Ressourcen\-Version Zerstörung.\)  Eine Ressource ist etwas, wodurch Sie "MouseEnter" abrufen und die später geben müssen.  Arbeitsspeicher ist die häufigste Ressource, es gibt jedoch auch Dateien, Sockets, Texturen und andere NichtArbeitsspeicherressourcen. Eine Ressource "besitzen" bedeutet dass Sie sie verwenden können wenn Sie es benötigen jedoch Sie sie freigeben müssen auch wenn sie fertig gestellt ist.  Wenn ein Objekt zerstört wird, ihr Destruktor gibt die Ressourcen frei, die er besaß.  
  
 Das endgültige Konzept ist das DAG \(verwiesen azyklisches Diagramm\).  Die Struktur des Besitzes in einem Programm bildet ein DAG.  Kein Objekt kann unmöglichen aber zudem grundsätzlich bedeutungslosen selbst\-dessen besitzen nicht nur.  Die beiden Objekte machen Kapitalbeteiligung eines dritten Objekts ein.  Einige Arten Links sind in einem DAG wie möglich: Ein ist ein Member von B \(B ist A\), C\-Speicher `vector<D>` \(C besitzt jedes D\-Element\), E\-Speicher `shared_ptr<F>` \(E gibt Besitz von F, möglicherweise mit andere Objekte\) auf, B.  Solange keine Zyklen gibt und jeder Link im DAG durch ein Objekt dargestellt wird, das einen Destruktor \(anstelle eines unbearbeiteten Zeigers, des Handles oder anderen Mechanismus\) hat, dann sind Ressourcenverluste nicht möglich, da die Sprache sie verhindert.  Ressourcen werden, sobald sie nicht mehr benötigt werden, ohne einen Garbage Collector\-Betrieb freigegeben.  Die Lebensdauernachverfolgung ist für MehraufwandFREE StackPanel, Basiszahlen, Member und verwandte Argumente, und billig für `shared_ptr`.  
  
### Heap\-basierte Lebensdauer  
 Für Heapobjektlebensdauer dem [intelligenten Zeiger](../cpp/smart-pointers-modern-cpp.md).  Verwenden Sie `shared_ptr` und `make_shared` als Standardzeiger und \-Zuweisung.  Verwenden Sie `weak_ptr`, um nach zu unterbrechen, führen Sie die Zwischenspeicherung und beobachten Sie Objekte, ohne dass über ihre Lebensdauer zu beeinflussen oder anzunehmen.  
  
```cpp  
void func() {  
  
auto p = make_shared<widget>(); // no leak, and exception safe  
...  
p->draw();   
  
} // no delete required, out-of-scope triggers smart pointer destructor  
  
```  
  
 Verwenden Sie `unique_ptr` für eindeutigen Besitz beispielsweise im *pimpl* Vorgehensweise. \(Siehe [pimpl für Compilierungszeitkapselung](../cpp/pimpl-for-compile-time-encapsulation-modern-cpp.md).\) Erstellen Sie `unique_ptr` das Hauptziel von allen expliziten `new` Ausdrücken erstellt.  
  
```cpp  
unique_ptr<widget> p(new widget());  
```  
  
 Sie können unformatierte Zeiger für Nichtbesitz und Beobachtung verwenden.  Ein nicht\-besitzender Zeiger baumelt, aber er kann nicht freigegeben.  
  
```cpp  
class node {  
  ...  
  vector<unique_ptr<node>> children; // node owns children  
  node* parent; // node observes parent, which is not a concern  
  ...  
};  
node::node() : parent(...) { children.emplace_back(new node(...) ); }  
  
```  
  
 Wenn Leistungsoptimierung erforderlich ist, müssen Sie möglicherweise verwenden *Well\-gekapselt,* Zeiger und explizite Aufrufe besitzend, um zu löschen.  Ein Beispiel ist, wenn Sie Ihre eigene Datenstruktur auf niedriger Ebene implementieren.  
  
### Stapelbasierte Lebensdauer  
 In modernem C\+\+ ist *stapelbasierter Bereich* eine leistungsstarke Methode, robusten Code zu schreiben, da sie automatische *Stapellebensdauer* kombiniert und *Datenmemberlebensdauer* mit hoher EffizienzLebensdauernachverfolgung im Grunde vom Mehraufwand frei ist.  Heapobjektlebensdauer erfordert sorgfältige manuelle Verwaltung und kann die Quelle von Ressourcenverlusten und \-unwirtschaftlichkeiten sein, besonders wenn Sie mit unformatierten Zeigern arbeiten.  Codebeispiel, der stapelbasierten Bereich werden:  
  
```cpp  
class widget {  
private:  
  gadget g;   // lifetime automatically tied to enclosing object  
public:  
  void draw();  
};  
  
void functionUsingWidget () {  
  widget w;   // lifetime automatically tied to enclosing scope  
              // constructs w, including the w.g gadget member  
  …  
  w.draw();  
  …  
} // automatic destruction and deallocation for w and w.g  
  // automatic exception safety,   
  // as if "finally { w.dispose(); w.g.dispose(); }"  
  
```  
  
 Verwenden von statischen Lebensdauer kaum \(statisches globales, Funktions\- lokales statisches\) da Probleme auftreten können.  Was geschieht, wenn der Konstruktor eines globalen Objekts eine Ausnahme auslöst?  In der Regel verursacht die App auf eine Weise, die schwer kann zu debuggen.  Konstruktionsreihenfolge ist für statische Lebensdauerobjekte problematisch, und ist nicht parallelitätssicher.  ist nicht nur der Objektkonstruktion ein Problem, Zerstörungsreihenfolge kann komplex sein, insbesondere der Polymorphie betroffen ist.  Auch wenn das Objekt oder Variable nicht polymorph ist und keine komplexen Konstruktions\-\/Zerstörungsreihenfolge aufweist, gibt es noch das Problem der threadsicheren Parallelität.  Eine Multithread\-DLL App kann die Daten in statischen Objekten ohne lokalen Threadspeicher, Ressourcensperren und andere spezielle Vorsichtsmaßnahmen zu haben sicher ändern.  
  
## Siehe auch  
 [Willkommen zurück bei C\+\+](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C\+\+\-Sprachreferenz](../cpp/cpp-language-reference.md)   
 [C\+\+\-Standardbibliothek](../standard-library/cpp-standard-library-reference.md)