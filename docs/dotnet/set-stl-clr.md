---
title: "set (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::set"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<cliext/set>-Header [STL/CLR]"
  - "<set>-Header [STL/CLR]"
  - "set-Klasse [STL/CLR]"
ms.assetid: 27d3628c-741a-43a7-bef1-5085536f679e
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# set (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Vorlagenklasse beschreibt ein Objekt, das eine VARYINGLängen\-Folge von Elementen steuert, die bidirektionalen Zugriff hat.  Mit dem Container `set`, um eine Sequenz von Elementen als WIQ\-Datei zu verwalten \(fast\) ausglichen geordneter Struktur von Knoten, jedem speichernden Element.  
  
 In der unten stehenden Beschreibung, `GValue` ist das `GKey` identisch, das wiederum das `Key` identisch ist, es sei denn, das zweite ein Referenz\-Typ ist, in diesem Fall `Key^` dar.  
  
## Syntax  
  
```  
template<typename Key>  
    ref class set  
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
  
## Member  
  
|Typdefinition|**Beschreibung**|  
|-------------------|----------------------|  
|[set::const\_iterator](../dotnet/set-const-iterator-stl-clr.md)|Der Typ eines konstanten Iterators für die gesteuerte Sequenz.|  
|[set::const\_reference](../dotnet/set-const-reference-stl-clr.md)|Der Typ eines konstanten Verweises auf ein Element.|  
|[set::const\_reverse\_iterator](../dotnet/set-const-reverse-iterator-stl-clr.md)|Der Typ eines konstanten umgekehrten Iterators für die gesteuerte Sequenz.|  
|[set::difference\_type](../dotnet/set-difference-type-stl-clr.md)|Der Typ der Abstand eine \(möglicherweise mit Vorzeichen\) zwischen zwei Elementen.|  
|[set::generic\_container](../dotnet/set-generic-container-stl-clr.md)|Der Typ der generischen Schnittstelle für den Container.|  
|[set::generic\_iterator](../dotnet/set-generic-iterator-stl-clr.md)|Der Typ eines Iterators für die generische Schnittstelle für den Container.|  
|[set::generic\_reverse\_iterator](../dotnet/set-generic-reverse-iterator-stl-clr.md)|Der Typ eines umgekehrten Iterators für die generische Schnittstelle für den Container.|  
|[set::generic\_value](../dotnet/set-generic-value-stl-clr.md)|Der Typ des Elements für die generische Schnittstelle für den Container.|  
|[set::iterator](../dotnet/set-iterator-stl-clr.md)|Der Typ eines Iterators für die gesteuerte Sequenz.|  
|[set::key\_compare](../dotnet/set-key-compare-stl-clr.md)|Der Reihenfolgendelegat für zwei Schlüssel.|  
|[set::key\_type](../dotnet/set-key-type-stl-clr.md)|Der Typ eines Sortierschlüssels.|  
|[set::reference](../dotnet/set-reference-stl-clr.md)|Der Typ eines Verweises auf ein Element.|  
|[set::reverse\_iterator](../dotnet/set-reverse-iterator-stl-clr.md)|Der Typ eines umgekehrten Iterators für die gesteuerte Sequenz.|  
|[set::size\_type](../dotnet/set-size-type-stl-clr.md)|Der Typ \(nicht negative a\) Abstands zwischen zwei Elementen.|  
|[set::value\_compare](../dotnet/set-value-compare-stl-clr.md)|Der Reihenfolgendelegat für zwei Elementwerte.|  
|[set::value\_type](../dotnet/set-value-type-stl-clr.md)|Der Typ eines Elements.|  
  
|Memberfunktion|**Beschreibung**|  
|--------------------|----------------------|  
|[set::begin](../dotnet/set-begin-stl-clr.md)|Legt den Anfang der kontrollierten Sequenz fest.|  
|[set::clear](../dotnet/set-clear-stl-clr.md)|Entfernt alle Elemente.|  
|[set::count](../dotnet/set-count-stl-clr.md)|Zählt die Elemente, die einen angegebenen Schlüssel übereinstimmen.|  
|[set::empty](../dotnet/set-empty-stl-clr.md)|Testet, dass keine Elemente vorhanden sind.|  
|[set::end](../dotnet/set-end-stl-clr.md)|Legt das Ende der kontrollierten Sequenz fest.|  
|[set::equal\_range](../dotnet/set-equal-range-stl-clr.md)|Suchen reichen die mit einem bestimmten Schlüssel.|  
|[set::erase](../dotnet/set-erase-stl-clr.md)|Entfernt Elemente an den angegebenen Positionen.|  
|[set::find](../dotnet/set-find-stl-clr.md)|Sucht ein Element, der einem angegebenen Schlüssel entspricht.|  
|[set::insert](../dotnet/set-insert-stl-clr.md)|Fügt Elemente hinzu.|  
|[set::key\_comp](../dotnet/set-key-comp-stl-clr.md)|Kopiert den Reihenfolgendelegaten für zwei Schlüssel.|  
|[set::lower\_bound](../dotnet/set-lower-bound-stl-clr.md)|Sucht Anfang des Bereichs, der einen angegebenen Schlüssel entspricht.|  
|[set::make\_value](../dotnet/set-make-value-stl-clr.md)|Erstellt ein Wertobjekt.|  
|[set::rbegin](../dotnet/set-rbegin-stl-clr.md)|Legt den Anfang der umgekehrten kontrollierten Sequenz fest.|  
|[set::rend](../dotnet/set-rend-stl-clr.md)|Legt das Ende der umgekehrten kontrollierten Sequenz fest.|  
|[set::set](../dotnet/set-set-stl-clr.md)|Erstellt ein container\-Objekt.|  
|[set::size](../dotnet/set-size-stl-clr.md)|Ermittelt die Anzahl der Elemente.|  
|[set::swap](../dotnet/set-swap-stl-clr.md)|Vertauscht den Inhalt von zwei Containern.|  
|[set::to\_array](../dotnet/set-to-array-stl-clr.md)|Kopiert die gesteuerte Sequenz zu einem neuen Array.|  
|[set::upper\_bound](../dotnet/set-upper-bound-stl-clr.md)|Suchenende des Bereichs, der einen angegebenen Schlüssel entspricht.|  
|[set::value\_comp](../dotnet/set-value-comp-stl-clr.md)|Kopiert den Reihenfolgendelegaten für zwei Elementwerte.|  
  
|Operator|**Beschreibung**|  
|--------------|----------------------|  
|[set::operator\=](../dotnet/set-operator-assign-stl-clr.md)|Ersetzt die gesteuerte Sequenz.|  
|[operator\!\= \(set\)](../dotnet/operator-inequality-set-stl-clr.md)|Bestimmt, ob ein `set`\-Objekt nicht gleich ein anderes `set`\-Objekt ist.|  
|[operator\< \(set\)](../dotnet/operator-less-than-set-stl-clr.md)|Bestimmt, ob ein `set`\-Objekt kleiner als ein anderes `set`\-Objekt ist.|  
|[operator\<\= \(set\)](../dotnet/operator-less-or-equal-set-stl-clr.md)|Bestimmt, ob ein `set`\-Objekt maximal ein anderes `set`\-Objekt ist.|  
|[operator\=\= \(set\)](../dotnet/operator-equality-set-stl-clr.md)|Bestimmt, ob ein `set`\-Objekt ein anderes Objekt gleich `set` ist.|  
|[operator\> \(set\)](../dotnet/operator-greater-than-set-stl-clr.md)|Bestimmt, ob ein `set`\-Objekt größer als ein anderes `set`\-Objekt ist.|  
|[operator\>\= \(set\)](../dotnet/operator-greater-or-equal-set-stl-clr.md)|Bestimmt, ob ein `set`\-Objekt größer oder gleich einem anderen `set`\-Objekt ist.|  
  
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
  
 Das Objekt ordnet die Sequenz, die steuert, indem ein gespeichertes Delegatobjekt des Typs [set::key\_compare](../dotnet/set-key-compare-stl-clr.md).  Sie können dem gespeicherten Delegatobjekt angeben, wenn Sie den Satz erstellen; Wenn Sie kein Delegatobjekt angeben, gilt standardmäßig der Vergleich `operator<(key_type, key_type)`.  Sie greifen auf das gespeicherte Objekt zu, indem Sie die Memberfunktion [set::key\_comp](../dotnet/set-key-comp-stl-clr.md)`()` aufrufen.  
  
 Ein solches Delegatobjekt muss eine genaue schwache Sortierung Schlüsseln des Typs [set::key\_type](../dotnet/set-key-type-stl-clr.md) festlegen.  Das heißt, für alle zwei Schlüssel `X` und `Y`:  
  
 `key_comp()(X, Y)` gibt die gleichen Auswirkungen auf booleschen jeden Aufruf zurück.  
  
 Wenn `key_comp()(X, Y)` true ist, muss `key_comp()(Y, X)` falsch sein.  
  
 Wenn `key_comp()(X, Y)` true ist, dann wird `X` vor `Y` nach.  
  
 Wenn `!key_comp()(X, Y) && !key_comp()(Y, X)` true ist, werden `X` und `Y` gibt an, um übereinstimmende Reihenfolge zu haben.  
  
 Für jedes Element `X`, das `Y` in der Sequenz gesteuerten vorangeht, ist `key_comp()(Y, X)` falsch. \(Für das Standarddelegatobjekt, verringert wird Schlüssel nie.\) Im Gegensatz Vorlagenklasse [set](../dotnet/set-stl-clr.md), benötigt ein Objekt der Vorlagenklasse `set` nicht, dass Tasten für alle Elemente eindeutig sind. \(zwei oder mehrere Tasten können entsprechende Reihenfolge haben.\)  
  
 Jedes Element dient als ey und Wert.  Die Sequenz wird so dargestellt, die Ermittlung, Einfügen und Entfernen eines beliebigen Elements mit Operationen zulässt, die z Logarithmus der Anzahl der Elemente in der Sequenz proportional sind \(logarithmische Zeit\).  Außerdem ein Element Einfügen macht keine Iteratoren ungültig, und ein Element entfernen, Iteratoren ungültig macht nur die am entfernten Element zeigen.  
  
 Ein Satz unterstützt bidirektionale Iteratoren, dass Sie zu benachbarten Elementen werden kann, dass ein Iterator angegeben werden, der ein Element in der Sequenz gesteuerten festlegt.  Ein spezieller Hauptknoten entspricht dem Iterator, der durch [set::end](../dotnet/set-end-stl-clr.md)`()` zurückgegeben wird.  Sie können diesen Iterator Dekrementieren, um das letzte Element der gesteuerten Sequenz erreicht, wenn vorhanden.  Sie können einen festgelegten Iterator erhöhen, um den Hauptknoten erreicht, und vergleicht er dann gleich `end()`.  Sie können jedoch den Iterator nicht möglich, der von `end()` zurückgegeben wird.  
  
 Beachten Sie, dass Sie sowohl ein Element zugreifen können, das direkt die numerische Position angegeben wird \- das erfordert einen Iterator mit wahlfreier Zugriff.  
  
 Ein festgelegter Iterator speichert ein Handle auf dem zugeordneten festgelegten Knoten, der wiederum ein Handle auf dem zugeordneten Container speichert.  Sie können Iteratoren nur mit ihren zugeordneten Containerobjekten verwenden.  Ein festgelegter Iterator bleibt gültig, solange der zugehörige Knoten mit festgelegter einen Satz zugeordnet ist.  Darüber hinaus ist ein gültiger dereferencable Iterator \- Sie können ihn verwenden, um auf den Elementwert zuzugreifen oder zu ändern, der festlegt wird \- solange er nicht gleich `end()` ist.  
  
 Ein Element Löschen oder entfernen, wird der Destruktor für den gespeicherten Wert auf.  Die Container Löschen eines Auflistungsobjekts, löscht alle Elemente.  Somit wird sichergestellt ein Container, dessen Elementtyp eine Verweisklasse, ist, dass keine Elemente den Container Beibehaltene Objekte.  Beachten Sie jedoch dem Container Handles `not` bewirkt, zerstören seine Elemente.  
  
## Anforderungen  
 **Header:** \<cliext\/Satz\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [hash\_map](../dotnet/hash-map-stl-clr.md)   
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [map](../dotnet/map-stl-clr.md)   
 [set](../dotnet/set-stl-clr.md)   
 [set](../dotnet/set-stl-clr.md)   
 [STL\/CLR\-Bibliothek](../dotnet/stl-clr-library-reference.md)