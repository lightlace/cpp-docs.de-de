---
title: "map (STL/CLR)"
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
  - "cliext::map"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<cliext/map>-Header [STL/CLR]"
  - "<map>-Header [STL/CLR]"
  - "map-Klasse [STL/CLR]"
ms.assetid: 8b0a7764-b5e4-4175-a802-82b72eb8662a
caps.latest.revision: 18
caps.handback.revision: "18"
ms.author: "mblome"
manager: "ghogen"
---
# map (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Vorlagenklasse beschreibt ein Objekt, das eine VARYINGLängen\-Folge von Elementen steuert, die bidirektionalen Zugriff hat.  Mit dem Container `map`, um eine Sequenz von Elementen als WIQ\-Datei zu verwalten \(fast\) ausglichen geordneter Struktur von Knoten, jedem speichernden Element.  Ein Element besteht eine Schlüssel, für Sortierungen der Sequenz und einen zugeordneten Wert, der entlang der Fahrt anstrebt.  
  
 In der unten stehenden Beschreibung, ist `GValue` identisch:  
  
 `Microsoft::VisualC::StlClr::GenericPair<GKey, GMapped>`  
  
 Hierbei ist:  
  
 `GKey` entspricht `Key`, außer, das zweite ein Referenz\-Typ ist, in diesem Fall wird `Key^` ist  
  
 `GMapped` entspricht `Mapped`, außer, das zweite ein Referenz\-Typ ist, in diesem Fall wird `Mapped^` ist  
  
## Syntax  
  
```  
template<typename Key,  
    typename Mapped>  
    ref class map  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        System::Collections::Generic::IList<GValue>,  
        System::Collections::Generic::IDictionary<Gkey, GMapped>,  
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
|[map::const\_iterator](../dotnet/map-const-iterator-stl-clr.md)|Der Typ eines konstanten Iterators für die gesteuerte Sequenz.|  
|[map::const\_reference](../dotnet/map-const-reference-stl-clr.md)|Der Typ eines konstanten Verweises auf ein Element.|  
|[map::const\_reverse\_iterator](../dotnet/map-const-reverse-iterator-stl-clr.md)|Der Typ eines konstanten umgekehrten Iterators für die gesteuerte Sequenz.|  
|[map::difference\_type](../dotnet/map-difference-type-stl-clr.md)|Der Typ der Abstand eine \(möglicherweise mit Vorzeichen\) zwischen zwei Elementen.|  
|[map::generic\_container](../dotnet/map-generic-container-stl-clr.md)|Der Typ der generischen Schnittstelle für den Container.|  
|[map::generic\_iterator](../dotnet/map-generic-iterator-stl-clr.md)|Der Typ eines Iterators für die generische Schnittstelle für den Container.|  
|[map::generic\_reverse\_iterator](../dotnet/map-generic-reverse-iterator-stl-clr.md)|Der Typ eines umgekehrten Iterators für die generische Schnittstelle für den Container.|  
|[map::generic\_value](../dotnet/map-generic-value-stl-clr.md)|Der Typ des Elements für die generische Schnittstelle für den Container.|  
|[map::iterator](../dotnet/map-iterator-stl-clr.md)|Der Typ eines Iterators für die gesteuerte Sequenz.|  
|[map::key\_compare](../dotnet/map-key-compare-stl-clr.md)|Der Reihenfolgendelegat für zwei Schlüssel.|  
|[map::key\_type](../dotnet/map-key-type-stl-clr.md)|Der Typ eines Sortierschlüssels.|  
|[map::mapped\_type](../dotnet/map-mapped-type-stl-clr.md)|Der Typ des zugehörigen Werts jeder zugeordneten Schlüssel zu.|  
|[map::reference](../dotnet/map-reference-stl-clr.md)|Der Typ eines Verweises auf ein Element.|  
|[map::reverse\_iterator](../dotnet/map-reverse-iterator-stl-clr.md)|Der Typ eines umgekehrten Iterators für die gesteuerte Sequenz.|  
|[map::size\_type](../dotnet/map-size-type-stl-clr.md)|Der Typ \(nicht negative a\) Abstands zwischen zwei Elementen.|  
|[map::value\_compare](../dotnet/map-value-compare-stl-clr.md)|Der Reihenfolgendelegat für zwei Elementwerte.|  
|[map::value\_type](../dotnet/map-value-type-stl-clr.md)|Der Typ eines Elements.|  
  
|Memberfunktion|**Beschreibung**|  
|--------------------|----------------------|  
|[map::begin](../dotnet/map-begin-stl-clr.md)|Legt den Anfang der kontrollierten Sequenz fest.|  
|[map::clear](../dotnet/map-clear-stl-clr.md)|Entfernt alle Elemente.|  
|[map::count](../dotnet/map-count-stl-clr.md)|Zählt die Elemente, die einen angegebenen Schlüssel übereinstimmen.|  
|[map::empty](../dotnet/map-empty-stl-clr.md)|Testet, dass keine Elemente vorhanden sind.|  
|[map::end](../dotnet/map-end-stl-clr.md)|Legt das Ende der kontrollierten Sequenz fest.|  
|[map::equal\_range](../dotnet/map-equal-range-stl-clr.md)|Suchen reichen die mit einem bestimmten Schlüssel.|  
|[map::erase](../dotnet/map-erase-stl-clr.md)|Entfernt Elemente an den angegebenen Positionen.|  
|[map::find](../dotnet/map-find-stl-clr.md)|Sucht ein Element, der einem angegebenen Schlüssel entspricht.|  
|[map::insert](../dotnet/map-insert-stl-clr.md)|Fügt Elemente hinzu.|  
|[map::key\_comp](../dotnet/map-key-comp-stl-clr.md)|Kopiert den Reihenfolgendelegaten für zwei Schlüssel.|  
|[map::lower\_bound](../dotnet/map-lower-bound-stl-clr.md)|Sucht Anfang des Bereichs, der einen angegebenen Schlüssel entspricht.|  
|[map::make\_value](../dotnet/map-make-value-stl-clr.md)|Erstellt ein Wertobjekt.|  
|[map::map](../dotnet/map-map-stl-clr.md)|Erstellt ein container\-Objekt.|  
|[map::rbegin](../dotnet/map-rbegin-stl-clr.md)|Legt den Anfang der umgekehrten kontrollierten Sequenz fest.|  
|[map::rend](../dotnet/map-rend-stl-clr.md)|Legt das Ende der umgekehrten kontrollierten Sequenz fest.|  
|[map::size](../dotnet/map-size-stl-clr.md)|Ermittelt die Anzahl der Elemente.|  
|[map::swap](../dotnet/map-swap-stl-clr.md)|Vertauscht den Inhalt von zwei Containern.|  
|[map::to\_array](../dotnet/map-to-array-stl-clr.md)|Kopiert die gesteuerte Sequenz zu einem neuen Array.|  
|[map::upper\_bound](../dotnet/map-upper-bound-stl-clr.md)|Suchenende des Bereichs, der einen angegebenen Schlüssel entspricht.|  
|[map::value\_comp](../dotnet/map-value-comp-stl-clr.md)|Kopiert den Reihenfolgendelegaten für zwei Elementwerte.|  
  
|Operator|**Beschreibung**|  
|--------------|----------------------|  
|[map::operator\=](../dotnet/map-operator-assign-stl-clr.md)|Ersetzt die gesteuerte Sequenz.|  
|[map::operator](../dotnet/map-operator-stl-clr.md)|Ordnet eine Schlüssel mit dem zugeordneten zugeordneten Wert zu.|  
|[operator\!\= \(map\)](../dotnet/operator-inequality-map-stl-clr.md)|Bestimmt, ob ein `map`\-Objekt nicht gleich ein anderes `map`\-Objekt ist.|  
|[operator\< \(map\)](../dotnet/operator-less-than-map-stl-clr.md)|Bestimmt, ob ein `map`\-Objekt kleiner als ein anderes `map`\-Objekt ist.|  
|[operator\<\= \(map\)](../dotnet/operator-less-or-equal-map-stl-clr.md)|Bestimmt, ob ein `map`\-Objekt maximal ein anderes `map`\-Objekt ist.|  
|[operator\=\= \(map\)](../dotnet/operator-equality-map-stl-clr.md)|Bestimmt, ob ein `map`\-Objekt ein anderes Objekt gleich `map` ist.|  
|[operator\> \(map\)](../dotnet/operator-greater-than-map-stl-clr.md)|Bestimmt, ob ein `map`\-Objekt größer als ein anderes `map`\-Objekt ist.|  
|[operator\>\= \(map\)](../dotnet/operator-greater-or-equal-map-stl-clr.md)|Bestimmt, ob ein `map`\-Objekt größer oder gleich einem anderen `map`\-Objekt ist.|  
  
## Schnittstellen  
  
|Schnittstelle|**Beschreibung**|  
|-------------------|----------------------|  
|<xref:System.ICloneable>|Ein Objekt duplizieren.|  
|<xref:System.Collections.IEnumerable>|Sequenz durch Elemente.|  
|<xref:System.Collections.ICollection>|Unbegrenztes Beibehalten Elementgruppe bei.|  
|<xref:System.Collections.Generic.IEnumerable`1>|Sequenz von typisierten Elemente.|  
|<xref:System.Collections.Generic.ICollection`1>|Unbegrenztes Beibehalten Gruppe typisierten Elemente bei.|  
|<xref:System.Collections.Generic.IDictionary`2>|Unbegrenztes Beibehalten Gruppe {,} Paare Schlüssel Wert bei.|  
|ITreeKey \<, Value\>|Warten Sie generischen Container.|  
  
## Hinweise  
 Das Objekt belegt und gibt die Sequenz für Speicher frei, die er als einzelne Knoten steuert.  Es werden Elemente in ein \(fast\) ausglich Struktur, Relevanz die es enthält, indem die Links zwischen Knoten ändert, nie ein, indem der Inhalt von einem Knoten zum anderen kopiert.  Das bedeutet, dass Sie Elemente beunruhigende ohne verbleibende Elemente frei einfügen und löschen können.  
  
 Das Objekt ordnet die Sequenz, die steuert, indem ein gespeichertes Delegatobjekt des Typs [map::key\_compare](../dotnet/map-key-compare-stl-clr.md).  Sie können dem gespeicherten Delegatobjekt angeben, wenn die Zuordnung erstellen; Wenn Sie kein Delegatobjekt angeben, gilt standardmäßig der Vergleich `operator<(key_type, key_type)`.  Sie greifen auf das gespeicherte Objekt zu, indem Sie die Memberfunktion [map::key\_comp](../dotnet/map-key-comp-stl-clr.md)`()` aufrufen.  
  
 Ein solches Delegatobjekt muss eine genaue schwache Sortierung Schlüsseln des Typs [map::key\_type](../dotnet/map-key-type-stl-clr.md) festlegen.  Das heißt, für alle zwei Schlüssel `X` und `Y`:  
  
 `key_comp()(X, Y)` gibt die gleichen Auswirkungen auf booleschen jeden Aufruf zurück.  
  
 Wenn `key_comp()(X, Y)` true ist, muss `key_comp()(Y, X)` falsch sein.  
  
 Wenn `key_comp()(X, Y)` true ist, dann wird `X` vor `Y` nach.  
  
 Wenn `!key_comp()(X, Y) && !key_comp()(Y, X)` true ist, werden `X` und `Y` gibt an, um übereinstimmende Reihenfolge zu haben.  
  
 Für jedes Element `X`, das `Y` in der Sequenz gesteuerten vorangeht, ist `key_comp()(Y, X)` falsch. \(Für das Standarddelegatobjekt, verringert wird Schlüssel nie.\) Im Gegensatz Vorlagenklasse [map](../dotnet/map-stl-clr.md), benötigt ein Objekt der Vorlagenklasse `map` nicht, dass Tasten für alle Elemente eindeutig sind. \(zwei oder mehrere Tasten können entsprechende Reihenfolge haben.\)  
  
 Jedes Element enthält eine eigene Schlüssel und einen zugeordneten Wert.  Die Sequenz wird so dargestellt, die Ermittlung, Einfügen und Entfernen eines beliebigen Elements mit Operationen zulässt, die z Logarithmus der Anzahl der Elemente in der Sequenz proportional sind \(logarithmische Zeit\).  Außerdem ein Element Einfügen macht keine Iteratoren ungültig, und ein Element entfernen, Iteratoren ungültig macht nur die am entfernten Element zeigen.  
  
 Eine Zuordnung unterstützt bidirektionale Iteratoren, dass Sie zu benachbarten Elementen werden kann, dass ein Iterator angegeben werden, der ein Element in der Sequenz gesteuerten festlegt.  Ein spezieller Hauptknoten entspricht dem Iterator, der durch [map::end](../dotnet/map-end-stl-clr.md)`()` zurückgegeben wird.  Sie können diesen Iterator Dekrementieren, um das letzte Element der gesteuerten Sequenz erreicht, wenn vorhanden.  Sie können einen Zuordnungsiterator erhöhen, um den Hauptknoten erreicht, und vergleicht er dann gleich `end()`.  Sie können jedoch den Iterator nicht möglich, der von `end()` zurückgegeben wird.  
  
 Beachten Sie, dass Sie ein Kartenelement nicht zugreifen können, das direkt die numerische Position angegeben wird \- das erfordert einen Iterator mit wahlfreier Zugriff.  
  
 Ein Zuordnungsiterator speichert ein Handle zu dem Knoten der verbundenen Zuordnung, der wiederum ein Handle auf dem zugeordneten Container speichert.  Sie können Iteratoren nur mit ihren zugeordneten Containerobjekten verwenden.  Ein Zuordnungsiterator bleibt gültig, solange sein Knoten der verbundenen Zuordnung mit einer Zuordnung zugeordnet ist.  Darüber hinaus ist ein gültiger dereferencable Iterator \- Sie können ihn verwenden, um auf den Elementwert zuzugreifen oder zu ändern, der festlegt wird \- solange er nicht gleich `end()` ist.  
  
 Ein Element Löschen oder entfernen, wird der Destruktor für den gespeicherten Wert auf.  Die Container Löschen eines Auflistungsobjekts, löscht alle Elemente.  Somit wird sichergestellt ein Container, dessen Elementtyp eine Verweisklasse, ist, dass keine Elemente den Container Beibehaltene Objekte.  Beachten Sie jedoch dem Container Handles `not` bewirkt, zerstören seine Elemente.  
  
## Anforderungen  
 **Header:** \<cliext\/Zuordnung\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [hash\_map](../dotnet/hash-map-stl-clr.md)   
 [hash\_map](../dotnet/hash-map-stl-clr.md)   
 [hash\_multiset](../dotnet/hash-multiset-stl-clr.md)   
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [map](../dotnet/map-stl-clr.md)   
 [multiset](../dotnet/multiset-stl-clr.md)   
 [set](../dotnet/set-stl-clr.md)   
 [STL\/CLR\-Bibliothek](../dotnet/stl-clr-library-reference.md)