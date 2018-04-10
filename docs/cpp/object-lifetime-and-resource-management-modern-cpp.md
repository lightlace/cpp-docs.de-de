---
title: Objektlebensdauer und Ressourcenverwaltung (Modern C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
ms.assetid: 8aa0e1a1-e04d-46b1-acca-1d548490700f
caps.latest.revision: 18
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4e2b48630fab9d27bf5db442617a5184bd26de5d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="object-lifetime-and-resource-management-modern-c"></a>Objektlebenszeit und Ressourcenverwaltung (Modern C++)
Im Gegensatz zu anderen verwalteten Sprachen keinen C++ Garbagecollection (GC) an, der nicht-mehr-used Speicherressourcen automatisch freigibt, während ein Programm ausgeführt wird. In C++ ressourcenverwaltung direkt Lebensdauer eines Objekts bezieht sich auf. Dieses Dokument beschreibt die Faktoren, die Lebensdauer eines Objekts in C++ und Verwaltung zu beeinflussen.  
  
 C++ hat keinen GC in erster Linie verwendet werden, da es nicht Arbeitsspeicherressourcen nicht behandelt. Deterministische Destruktoren ähnlich denen im C++ können Arbeitsspeicher-und nicht nur gleichermaßen behandeln. GC verfügt auch über andere Probleme, z. B. höherer Aufwand in Arbeitsspeicher und CPU-Auslastung und Ort. Aber Universalität ist ein grundlegendes Problem, das über cleveren Optimierungen gemindert werden kann.  
  
## <a name="concepts"></a>Konzepte  
 Eine wichtige Sache ist in der Verwaltung der Lebensdauer eines Objekts ist die Kapselung – wissen, welche Ressourcen das Objekt besitzt, oder wie sie zu entfernen oder sogar gibt an, ob sie alle Ressourcen überhaupt besitzt keinen wem auch immer ein Objekt verwendet wird. Er muss lediglich das Objekt zu zerstören. Die C++-Kernsprache wurde entwickelt, um sicherzustellen, dass Objekte über die richtigen Zeitangaben, d. h. zerstört werden, wie Blöcke, in umgekehrter Reihenfolge der Konstruktion beendet werden. Wenn ein Objekt zerstört wird, werden seine Basen und Membern in einer bestimmten Reihenfolge zerstört.  Die Sprache zerstört automatisch Objekte, es sei denn, Sie spezielle Aktionen wie Heapzuordnung oder neue Platzierung ausgeführt werden.  Beispielsweise [intelligente Zeiger](../cpp/smart-pointers-modern-cpp.md) wie `unique_ptr` und `shared_ptr`, und C++-Standardbibliothek-Container wie `vector`, kapseln `new` / `delete` und `new[]` / `delete[]` in Objekten, die Destruktoren besitzen. Deshalb ist es ist daher wichtig, intelligente Zeiger und die C++-Standardbibliothek Container verwenden.  
  
 Ein weiteres wichtiges Konzept in Prozesslebensdauer-Verwaltung: Destruktoren. Destruktoren kapseln Version der Ressource.  (Die häufig verwendete mnemonische Zeichen ist RRID Ressource Release ist Zerstörung.)  Eine Ressource ist etwas, das Sie von "System" abrufen und später wieder zu erteilen.  Arbeitsspeicher ist die am häufigsten verwendete Ressource, aber es gibt auch Dateien, Sockets, Texturen und andere Speicherressourcen. "Besitzer" einer Ressource bedeutet, dass Sie es verwenden können, wenn Sie ihn benötigen, haben Sie aber auch, diese freizugeben, wenn Sie damit fertig sind.  Wenn ein Objekt zerstört wird, gibt der Destruktor die Ressourcen, die es beim Besitzer um frei.  
  
 Das letzte Konzept ist die DAG (gerichtetes azyklisches Diagramm).  Die Struktur des Besitzes in einem Programm bildet eine DAG. Kein Objekt kann selbst besitzen –, die sich nicht nur unmöglich, aber grundsätzlich auch ohne Bedeutung. Jedoch zwei Objekte können den Besitz Teilen eines dritten-Objekts.  Verschiedene Arten von Links sind in einer DAG, wie dies möglich: A ist Mitglied von B (B besitzt ein), C speichert eine `vector<D>` (C, besitzt jedes Element D), E speichert eine `shared_ptr<F>` (E freigegeben hat den Besitz von F, möglicherweise mit anderen Objekten), usw.  Solange keine Schleifen vorhanden sind und in die DAG standortbezogene wird durch ein Objekt dargestellt, die einen Destruktor (statt einen unformatierten Zeiger, Handle oder anderen Mechanismen) hat, und klicken Sie dann Ressourcenverluste sind nicht möglich, da die Sprache verhindert, sie dass. Ressourcen werden freigegeben, sobald sie nicht mehr benötigt werden, ohne eine Garbage Collection ausgeführt wird. Die Lebensdauer nachverfolgen ist Mehraufwand für die Stack-Bereich, Basen, Mitglieder und ähnlichen Fällen frei, und für kostengünstig `shared_ptr`.  
  
### <a name="heap-based-lifetime"></a>Heap-basierte Lebensdauer  
 Verwenden Sie für die Lebensdauer eines Objekts des Heaps, [intelligente Zeiger](../cpp/smart-pointers-modern-cpp.md). Verwendung `shared_ptr` und `make_shared` als der Standardzeiger und der Zuweisung. Verwendung `weak_ptr` Zyklen unterbrechen, führen Sie das Zwischenspeichern und beobachten von Objekten ohne Auswirkung auf oder nichts über deren Lebensdauer vorausgesetzt.  
  
```cpp  
void func() {  
  
auto p = make_shared<widget>(); // no leak, and exception safe  
...  
p->draw();   
  
} // no delete required, out-of-scope triggers smart pointer destructor  
  
```  
  
 Verwendung `unique_ptr` für eindeutigen Besitz, z. B. in der *"pimpl"* Idiom. (Siehe [Pimpl für Compilierungszeitkapselung](../cpp/pimpl-for-compile-time-encapsulation-modern-cpp.md).) Stellen Sie eine `unique_ptr` die primäre Zielgruppe für alle expliziten `new` Ausdrücke.  
  
```cpp  
unique_ptr<widget> p(new widget());  
```  
  
 Sie können die unformatierte Zeiger für nicht-Objektbesitz und Beobachtung verwenden. Ein Zeiger nicht besitzt möglicherweise dangle, aber es kann nicht zur Offenlegung von.  
  
```cpp  
class node {  
  ...  
  vector<unique_ptr<node>> children; // node owns children  
  node* parent; // node observes parent, which is not a concern  
  ...  
};  
node::node() : parent(...) { children.emplace_back(new node(...) ); }  
  
```  
  
 Bei der Optimierung der Leistung erforderlich ist, müssen Sie möglicherweise verwenden *gut gekapselten* Zeiger und der explizite Aufrufe zu löschen. Ein Beispiel ist, wenn Sie eigene auf niedriger Ebene Datenstruktur implementieren.  
  
### <a name="stack-based-lifetime"></a>Stapelbasierte Lebensdauer  
 In modernem C++ *stapelbasierte Bereiche* ist eine leistungsfähige Möglichkeit zur stabilen Code geschrieben werden, da sie automatische kombiniert *Stapel Lebensdauer* und *Datenmember Lebensdauer* mit hohe Effizienz: Nachverfolgen von Lebensdauer ist im Wesentlichen Mehraufwand. Objektlebensdauer Heap kann sorgfältiger manuelle Verwaltung erfordert und die Quelle der Ressource prüfen auf Speicherverluste und ineffiziente, insbesondere bei der Arbeit mit unformatierte Zeiger. Betrachten Sie diesen Code, der stapelbasierte Bereiche veranschaulicht:  
  
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
    // ...
    w.draw();  
    // ...
} // automatic destruction and deallocation for w and w.g  
  // automatic exception safety,   
  // as if "finally { w.dispose(); w.g.dispose(); }"  
```  
  
 Verwenden Sie statische Lebensdauer sparsam (globale statische, lokale statische Funktion), da Probleme auftreten können. Was geschieht, wenn der Konstruktor eines globalen Objekts löst eine Ausnahme aus? In der Regel wird die app Fehler in einer Weise, die schwer zu debuggen sind. Konstruktion Reihenfolge für die Lebensdauer der statischen Objekte problematisch ist, und ist nicht nebenläufigkeitssicher. Objekterstellung ist nicht nur ein Problem Zerstörungsreihenfolge kann kompliziert sein, insbesondere bei der Polymorphie beteiligt ist. Selbst wenn Ihr Objekt oder die Variable ist nicht polymorph und keine komplexen Erstellung/Zerstörung Sortierung, ist immer noch das Problem der Thread-sichere Parallelität. Eine Multithread-app kann nicht die Daten in statische Objekte ohne lokalen Threadspeicher, Ressourcensperren und andere besonderen Vorsichtsmaßnahmen sicher ändern.  
  
## <a name="see-also"></a>Siehe auch  
 [Willkommen zurück bei C++](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C++-Sprachreferenz](../cpp/cpp-language-reference.md)   
 [C++-Standardbibliothek](../standard-library/cpp-standard-library-reference.md)