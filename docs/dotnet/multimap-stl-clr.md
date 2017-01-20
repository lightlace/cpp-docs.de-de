---
title: "multimap (STL/CLR)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "cliext::multimap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<cliext/map>-Header [STL/CLR]"
  - "<map>-Header [STL/CLR]"
  - "multimap-Klasse [STL/CLR]"
ms.assetid: 3dfe329d-a078-462a-b050-7999ce6110ad
caps.latest.revision: 17
caps.handback.revision: "17"
ms.author: "mblome"
manager: "ghogen"
---
# multimap (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Vorlagenklasse beschreibt ein Objekt, das eine VARYINGLängen\-Folge von Elementen steuert, die bidirektionalen Zugriff hat.  Mit dem Container `multimap`, um eine Sequenz von Elementen als WIQ\-Datei zu verwalten \(fast\) ausglichen geordneter Struktur von Knoten, jedem speichernden Element.  Ein Element besteht eine Schlüssel, für Sortierungen der Sequenz und einen zugeordneten Wert, der entlang der Fahrt anstrebt.  
  
 In der unten stehenden Beschreibung, ist `GValue` identisch:  
  
 `Microsoft::VisualC::StlClr::GenericPair<GKey, GMapped>`  
  
 Hierbei ist:  
  
 `GKey` entspricht `Key`, außer, das zweite ein Referenz\-Typ ist, in diesem Fall wird `Key^` ist  
  
 `GMapped` entspricht `Mapped`, außer, das zweite ein Referenz\-Typ ist, in diesem Fall wird `Mapped^` ist  
  
## Syntax  
  
```  
template<typename Key,  
    typename Mapped>  
    ref class multimap  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        System::Collections::Generic::IList<GValue>,  
        Microsoft::VisualC::StlClr::ITree<Gkey, GValue>  
    { ..... };  
```  
  
#### Parameter  
 Key  
 Der Typ der Schlüsselkomponente eines Elements in der kontrollierten Sequenz.  
  
 Zugeordnet  
 Der Typ der zusätzlichen Komponente eines Elements in der Sequenz. gesteuerten  
  
## Member  
  
|Typdefinition|**Beschreibung**|  
|-------------------|----------------------|  
|[multimap::const\_iterator](../dotnet/multimap-const-iterator-stl-clr.md)|Der Typ eines konstanten Iterators für die gesteuerte Sequenz.|  
|[multimap::const\_reference](../dotnet/multimap-const-reference-stl-clr.md)|Der Typ eines konstanten Verweises auf ein Element.|  
|[multimap::const\_reverse\_iterator](../dotnet/multimap-const-reverse-iterator-stl-clr.md)|Der Typ eines konstanten umgekehrten Iterators für die gesteuerte Sequenz.|  
|[multimap::difference\_type](../dotnet/multimap-difference-type-stl-clr.md)|Der Typ der Abstand eine \(möglicherweise mit Vorzeichen\) zwischen zwei Elementen.|  
|[multimap::generic\_container](../dotnet/multimap-generic-container-stl-clr.md)|Der Typ der generischen Schnittstelle für den Container.|  
|[multimap::generic\_iterator](../dotnet/multimap-generic-iterator-stl-clr.md)|Der Typ eines Iterators für die generische Schnittstelle für den Container.|  
|[multimap::generic\_reverse\_iterator](../dotnet/multimap-generic-reverse-iterator-stl-clr.md)|Der Typ eines umgekehrten Iterators für die generische Schnittstelle für den Container.|  
|[multimap::generic\_value](../dotnet/multimap-generic-value-stl-clr.md)|Der Typ des Elements für die generische Schnittstelle für den Container.|  
|[multimap::iterator](../dotnet/multimap-iterator-stl-clr.md)|Der Typ eines Iterators für die gesteuerte Sequenz.|  
|[multimap::key\_compare](../dotnet/multimap-key-compare-stl-clr.md)|Der Reihenfolgendelegat für zwei Schlüssel.|  
|[multimap::key\_type](../dotnet/multimap-key-type-stl-clr.md)|Der Typ eines Sortierschlüssels.|  
|[multimap::mapped\_type](../dotnet/multimap-mapped-type-stl-clr.md)|Der Typ des zugehörigen Werts jeder zugeordneten Schlüssel zu.|  
|[multimap::reference](../dotnet/multimap-reference-stl-clr.md)|Der Typ eines Verweises auf ein Element.|  
|[multimap::reverse\_iterator](../dotnet/multimap-reverse-iterator-stl-clr.md)|Der Typ eines umgekehrten Iterators für die gesteuerte Sequenz.|  
|[multimap::size\_type](../dotnet/multimap-size-type-stl-clr.md)|Der Typ \(nicht negative a\) Abstands zwischen zwei Elementen.|  
|[multimap::value\_compare](../dotnet/multimap-value-compare-stl-clr.md)|Der Reihenfolgendelegat für zwei Elementwerte.|  
|[multimap::value\_type](../dotnet/multimap-value-type-stl-clr.md)|Der Typ eines Elements.|  
  
|Memberfunktion|**Beschreibung**|  
|--------------------|----------------------|  
|[multimap::begin](../dotnet/multimap-begin-stl-clr.md)|Legt den Anfang der kontrollierten Sequenz fest.|  
|[multimap::clear](../dotnet/multimap-clear-stl-clr.md)|Entfernt alle Elemente.|  
|[multimap::count](../dotnet/multimap-count-stl-clr.md)|Zählt die Elemente, die einen angegebenen Schlüssel übereinstimmen.|  
|[multimap::empty](../dotnet/multimap-empty-stl-clr.md)|Testet, dass keine Elemente vorhanden sind.|  
|[multimap::end](../dotnet/multimap-end-stl-clr.md)|Legt das Ende der kontrollierten Sequenz fest.|  
|[multimap::equal\_range](../dotnet/multimap-equal-range-stl-clr.md)|Suchen reichen die mit einem bestimmten Schlüssel.|  
|[multimap::erase](../dotnet/multimap-erase-stl-clr.md)|Entfernt Elemente an den angegebenen Positionen.|  
|[multimap::find](../dotnet/multimap-find-stl-clr.md)|Sucht ein Element, der einem angegebenen Schlüssel entspricht.|  
|[multimap::insert](../dotnet/multimap-insert-stl-clr.md)|Fügt Elemente hinzu.|  
|[multimap::key\_comp](../dotnet/multimap-key-comp-stl-clr.md)|Kopiert den Reihenfolgendelegaten für zwei Schlüssel.|  
|[multimap::lower\_bound](../dotnet/multimap-lower-bound-stl-clr.md)|Sucht Anfang des Bereichs, der einen angegebenen Schlüssel entspricht.|  
|[multimap::make\_value](../dotnet/multimap-make-value-stl-clr.md)|Erstellt ein Wertobjekt.|  
|[multimap::multimap](../dotnet/multimap-multimap-stl-clr.md)|Erstellt ein container\-Objekt.|  
|[multimap::rbegin](../dotnet/multimap-rbegin-stl-clr.md)|Legt den Anfang der umgekehrten kontrollierten Sequenz fest.|  
|[multimap::rend](../dotnet/multimap-rend-stl-clr.md)|Legt das Ende der umgekehrten kontrollierten Sequenz fest.|  
|[multimap::size](../dotnet/multimap-size-stl-clr.md)|Ermittelt die Anzahl der Elemente.|  
|[multimap::swap](../dotnet/multimap-swap-stl-clr.md)|Vertauscht den Inhalt von zwei Containern.|  
|[multimap::to\_array](../dotnet/multimap-to-array-stl-clr.md)|Kopiert die gesteuerte Sequenz zu einem neuen Array.|  
|[multimap::upper\_bound](../dotnet/multimap-upper-bound-stl-clr.md)|Suchenende des Bereichs, der einen angegebenen Schlüssel entspricht.|  
|[multimap::value\_comp](../dotnet/multimap-value-comp-stl-clr.md)|Kopiert den Reihenfolgendelegaten für zwei Elementwerte.|  
  
|Operator|**Beschreibung**|  
|--------------|----------------------|  
|[multimap::operator\=](../dotnet/multimap-operator-assign-stl-clr.md)|Ersetzt die gesteuerte Sequenz.|  
|[operator\!\= \(multimap\)](../dotnet/operator-inequality-multimap-stl-clr.md)|Bestimmt, ob ein `multimap`\-Objekt nicht gleich ein anderes `multimap`\-Objekt ist.|  
|[operator\< \(multimap\)](../dotnet/operator-less-than-multimap-stl-clr.md)|Bestimmt, ob ein `multimap`\-Objekt kleiner als ein anderes `multimap`\-Objekt ist.|  
|[operator\<\= \(multimap\)](../dotnet/operator-less-or-equal-multimap-stl-clr.md)|Bestimmt, ob ein `multimap`\-Objekt maximal ein anderes `multimap`\-Objekt ist.|  
|[operator\=\= \(multimap\)](../dotnet/operator-equality-multimap-stl-lr.md)|Bestimmt, ob ein `multimap`\-Objekt ein anderes Objekt gleich `multimap` ist.|  
|[operator\> \(multimap\)](../dotnet/operator-greater-than-multimap-stl-clr.md)|Bestimmt, ob ein `multimap`\-Objekt größer als ein anderes `multimap`\-Objekt ist.|  
|[operator\>\= \(multimap\)](../dotnet/operator-greater-or-equal-multimap-stl-clr.md)|Bestimmt, ob ein `multimap`\-Objekt größer oder gleich einem anderen `multimap`\-Objekt ist.|  
  
## Schnittstellen  
  
|Schnittstelle|**Beschreibung**|  
|-------------------|----------------------|  
|<xref:System.ICloneable>|Ein Objekt duplizieren.|  
|<xref:System.Collections.IEnumerable>|Sequenz durch Elemente.|  
|<xref:System.Collections.ICollection>|Unbegrenztes Beibehalten Elementgruppe bei.|  
|<xref:System.Collections.Generic.IEnumerable`1>|Sequenz von typisierten Elemente.|  
|<xref:System.Collections.Generic.ICollection`1>|Unbegrenztes Beibehalten Gruppe typisierten Elemente bei.|  
|ITreeKey \<, Value\>|Warten Sie generischen Container.|  
  
## Hinweise  
 Das Objekt belegt und gibt die Sequenz für Speicher frei, die er als einzelne Knoten steuert.  Es werden Elemente in ein \(fast\) ausglich Struktur, Relevanz die es enthält, indem die Links zwischen Knoten ändert, nie ein, indem der Inhalt von einem Knoten zum anderen kopiert.  Das bedeutet, dass Sie Elemente beunruhigende ohne verbleibende Elemente frei einfügen und löschen können.  
  
 Das Objekt ordnet die Sequenz, die steuert, indem ein gespeichertes Delegatobjekt des Typs [multimap::key\_compare](../dotnet/multimap-key-compare-stl-clr.md).  Sie können dem gespeicherten Delegatobjekt angeben, wenn die Multimap erstellen; Wenn Sie kein Delegatobjekt angeben, gilt standardmäßig der Vergleich `operator<(key_type, key_type)`.  Sie greifen auf das gespeicherte Objekt zu, indem Sie die Memberfunktion [multimap::key\_comp](../dotnet/multimap-key-comp-stl-clr.md)`()` aufrufen.  
  
 Ein solches Delegatobjekt muss eine genaue schwache Sortierung Schlüsseln des Typs [multimap::key\_type](../dotnet/multimap-key-type-stl-clr.md) festlegen.  Das heißt, für alle zwei Schlüssel `X` und `Y`:  
  
 `key_comp()(X, Y)` gibt die gleichen Auswirkungen auf booleschen jeden Aufruf zurück.  
  
 Wenn `key_comp()(X, Y)` true ist, muss `key_comp()(Y, X)` falsch sein.  
  
 Wenn `key_comp()(X, Y)` true ist, dann wird `X` vor `Y` nach.  
  
 Wenn `!key_comp()(X, Y) && !key_comp()(Y, X)` true ist, werden `X` und `Y` gibt an, um übereinstimmende Reihenfolge zu haben.  
  
 Für jedes Element `X`, das `Y` in der Sequenz gesteuerten vorangeht, ist `key_comp()(Y, X)` falsch. \(Für das Standarddelegatobjekt, verringert wird Schlüssel nie.\) Im Gegensatz Vorlagenklasse [map](../dotnet/map-stl-clr.md), benötigt ein Objekt der Vorlagenklasse `multimap` nicht, dass Tasten für alle Elemente eindeutig sind. \(zwei oder mehrere Tasten können entsprechende Reihenfolge haben.\)  
  
 Jedes Element enthält eine eigene Schlüssel und einen zugeordneten Wert.  Die Sequenz wird so dargestellt, die Ermittlung, Einfügen und Entfernen eines beliebigen Elements mit Operationen zulässt, die z Logarithmus der Anzahl der Elemente in der Sequenz proportional sind \(logarithmische Zeit\).  Außerdem ein Element Einfügen macht keine Iteratoren ungültig, und ein Element entfernen, Iteratoren ungültig macht nur die am entfernten Element zeigen.  
  
 Eine Multimap unterstützt bidirektionale Iteratoren, dass Sie zu benachbarten Elementen werden kann, dass ein Iterator angegeben werden, der ein Element in der Sequenz gesteuerten festlegt.  Ein spezieller Hauptknoten entspricht dem Iterator, der durch [multimap::end](../dotnet/multimap-end-stl-clr.md)`()` zurückgegeben wird.  Sie können diesen Iterator Dekrementieren, um das letzte Element der gesteuerten Sequenz erreicht, wenn vorhanden.  Sie können einen Multimapiterator erhöhen, um den Hauptknoten erreicht, und vergleicht er dann gleich `end()`.  Sie können jedoch den Iterator nicht möglich, der von `end()` zurückgegeben wird.  
  
 Beachten Sie, dass Sie ein Multimapelement nicht zugreifen können, das direkt die numerische Position angegeben wird \- das erfordert einen Iterator mit wahlfreier Zugriff.  
  
 Ein Multimapiterator speichert ein Handle auf dem zugeordneten Multimapknoten, der wiederum ein Handle auf dem zugeordneten Container speichert.  Sie können Iteratoren nur mit ihren zugeordneten Containerobjekten verwenden.  Ein Multimapiterator bleibt gültig, solange der zugehörige Multimapknoten mit einer Multimap zugeordnet ist.  Darüber hinaus ist ein gültiger dereferencable Iterator \- Sie können ihn verwenden, um auf den Elementwert zuzugreifen oder zu ändern, der festlegt wird \- solange er nicht gleich `end()` ist.  
  
 Ein Element Löschen oder entfernen, wird der Destruktor für den gespeicherten Wert auf.  Die Container Löschen eines Auflistungsobjekts, löscht alle Elemente.  Somit wird sichergestellt ein Container, dessen Elementtyp eine Verweisklasse, ist, dass keine Elemente den Container Beibehaltene Objekte.  Beachten Sie jedoch dem Container Handles `not` bewirkt, zerstören seine Elemente.  
  
## Anforderungen  
 **Header:** \<cliext\/Zuordnung\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [hash\_map](../dotnet/hash-map-stl-clr.md)   
 [hash\_multimap](../dotnet/hash-multimap-stl-clr.md)   
 [hash\_multiset](../dotnet/hash-multiset-stl-clr.md)   
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [map](../dotnet/map-stl-clr.md)   
 [multiset](../dotnet/multiset-stl-clr.md)   
 [set](../dotnet/set-stl-clr.md)   
 [STL\/CLR\-Bibliothek](../dotnet/stl-clr-library-reference.md)