---
title: "multiset (STL/CLR)"
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
  - "cliext::multiset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<cliext/set>-Header [STL/CLR]"
  - "<set>-Header [STL/CLR]"
  - "multiset-Klasse [STL/CLR]"
ms.assetid: 7c46e2b4-cd88-49b7-a9e6-63ad5ae7feb5
caps.latest.revision: 18
caps.handback.revision: "18"
ms.author: "mblome"
manager: "ghogen"
---
# multiset (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Vorlagenklasse beschreibt ein Objekt, das eine VARYINGLängen\-Folge von Elementen steuert, die bidirektionalen Zugriff hat.  Mit dem Container `multiset`, um eine Sequenz von Elementen als WIQ\-Datei zu verwalten \(fast\) ausglichen geordneter Struktur von Knoten, jedem speichernden Element.  
  
 In der unten stehenden Beschreibung, `GValue` ist das `GKey` identisch, das wiederum das `Key` identisch ist, es sei denn, das zweite ein Referenz\-Typ ist, in diesem Fall `Key^` dar.  
  
## Syntax  
  
```  
template<typename Key>  
    ref class multiset  
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
|[multiset::const\_iterator](../dotnet/multiset-const-iterator-stl-clr.md)|Der Typ eines konstanten Iterators für die gesteuerte Sequenz.|  
|[multiset::const\_reference](../dotnet/multiset-const-reference-stl-clr.md)|Der Typ eines konstanten Verweises auf ein Element.|  
|[multiset::const\_reverse\_iterator](../dotnet/multiset-const-reverse-iterator-stl-clr.md)|Der Typ eines konstanten umgekehrten Iterators für die gesteuerte Sequenz.|  
|[multiset::difference\_type](../dotnet/multiset-difference-type-stl-clr.md)|Der Typ der Abstand eine \(möglicherweise mit Vorzeichen\) zwischen zwei Elementen.|  
|[multiset::generic\_container](../dotnet/multiset-generic-container-stl-clr.md)|Der Typ der generischen Schnittstelle für den Container.|  
|[multiset::generic\_iterator](../dotnet/multiset-generic-iterator-stl-clr.md)|Der Typ eines Iterators für die generische Schnittstelle für den Container.|  
|[multiset::generic\_reverse\_iterator](../dotnet/multiset-generic-reverse-iterator-stl-clr.md)|Der Typ eines umgekehrten Iterators für die generische Schnittstelle für den Container.|  
|[multiset::generic\_value](../dotnet/multiset-generic-value-stl-clr.md)|Der Typ des Elements für die generische Schnittstelle für den Container.|  
|[multiset::iterator](../dotnet/multiset-iterator-stl-clr.md)|Der Typ eines Iterators für die gesteuerte Sequenz.|  
|[multiset::key\_compare](../dotnet/multiset-key-compare-stl-clr.md)|Der Reihenfolgendelegat für zwei Schlüssel.|  
|[multiset::key\_type](../dotnet/multiset-key-type-stl-clr.md)|Der Typ eines Sortierschlüssels.|  
|[multiset::reference](../dotnet/multiset-reference-stl-clr.md)|Der Typ eines Verweises auf ein Element.|  
|[multiset::reverse\_iterator](../dotnet/multiset-reverse-iterator-stl-clr.md)|Der Typ eines umgekehrten Iterators für die gesteuerte Sequenz.|  
|[multiset::size\_type](../dotnet/multiset-size-type-stl-clr.md)|Der Typ \(nicht negative a\) Abstands zwischen zwei Elementen.|  
|[multiset::value\_compare](../dotnet/multiset-value-compare-stl-clr.md)|Der Reihenfolgendelegat für zwei Elementwerte.|  
|[multiset::value\_type](../dotnet/multiset-value-type-stl-clr.md)|Der Typ eines Elements.|  
  
|Memberfunktion|**Beschreibung**|  
|--------------------|----------------------|  
|[multiset::begin](../dotnet/multiset-begin-stl-clr.md)|Legt den Anfang der kontrollierten Sequenz fest.|  
|[multiset::clear](../dotnet/multiset-clear-stl-clr.md)|Entfernt alle Elemente.|  
|[multiset::count](../dotnet/multiset-count-stl-clr.md)|Zählt die Elemente, die einen angegebenen Schlüssel übereinstimmen.|  
|[multiset::empty](../dotnet/multiset-empty-stl-clr.md)|Testet, dass keine Elemente vorhanden sind.|  
|[multiset::end](../dotnet/multiset-end-stl-clr.md)|Legt das Ende der kontrollierten Sequenz fest.|  
|[multiset::equal\_range](../dotnet/multiset-equal-range-stl-clr.md)|Suchen reichen die mit einem bestimmten Schlüssel.|  
|[multiset::erase](../dotnet/multiset-erase-stl-clr.md)|Entfernt Elemente an den angegebenen Positionen.|  
|[multiset::find](../dotnet/multiset-find-stl-clr.md)|Sucht ein Element, der einem angegebenen Schlüssel entspricht.|  
|[multiset::insert](../dotnet/multiset-insert-stl-clr.md)|Fügt Elemente hinzu.|  
|[multiset::key\_comp](../dotnet/multiset-key-comp-stl-clr.md)|Kopiert den Reihenfolgendelegaten für zwei Schlüssel.|  
|[multiset::lower\_bound](../dotnet/multiset-lower-bound-stl-clr.md)|Sucht Anfang des Bereichs, der einen angegebenen Schlüssel entspricht.|  
|[multiset::make\_value](../dotnet/multiset-make-value-stl-clr.md)|Erstellt ein Wertobjekt.|  
|[multiset::multiset](../dotnet/multiset-multiset-stl-clr.md)|Erstellt ein container\-Objekt.|  
|[multiset::rbegin](../dotnet/multiset-rbegin-stl-clr.md)|Legt den Anfang der umgekehrten kontrollierten Sequenz fest.|  
|[multiset::rend](../dotnet/multiset-rend-stl-clr.md)|Legt das Ende der umgekehrten kontrollierten Sequenz fest.|  
|[multiset::size](../dotnet/multiset-size-stl-clr.md)|Ermittelt die Anzahl der Elemente.|  
|[multiset::swap](../dotnet/multiset-swap-stl-clr.md)|Vertauscht den Inhalt von zwei Containern.|  
|[multiset::to\_array](../dotnet/multiset-to-array-stl-clr.md)|Kopiert die gesteuerte Sequenz zu einem neuen Array.|  
|[multiset::upper\_bound](../dotnet/multiset-upper-bound-stl-clr.md)|Suchenende des Bereichs, der einen angegebenen Schlüssel entspricht.|  
|[multiset::value\_comp](../dotnet/multiset-value-comp-stl-clr.md)|Kopiert den Reihenfolgendelegaten für zwei Elementwerte.|  
  
|Operator|**Beschreibung**|  
|--------------|----------------------|  
|[multiset::operator\=](../dotnet/multiset-operator-assign-stl-clr.md)|Ersetzt die gesteuerte Sequenz.|  
|[operator\!\= \(multiset\)](../dotnet/operator-inequality-multiset-stl-clr.md)|Bestimmt, ob ein `multiset`\-Objekt nicht gleich ein anderes `multiset`\-Objekt ist.|  
|[operator\< \(multiset\)](../dotnet/operator-less-than-multiset-stl-clr.md)|Bestimmt, ob ein `multiset`\-Objekt kleiner als ein anderes `multiset`\-Objekt ist.|  
|[operator\<\= \(multiset\)](../dotnet/operator-less-or-equal-multiset-stl-clr.md)|Bestimmt, ob ein `multiset`\-Objekt maximal ein anderes `multiset`\-Objekt ist.|  
|[operator\=\= \(multiset\)](../dotnet/operator-equality-multiset-stl-clr.md)|Bestimmt, ob ein `multiset`\-Objekt ein anderes Objekt gleich `multiset` ist.|  
|[operator\> \(multiset\)](../dotnet/operator-greater-than-multiset-stl-clr.md)|Bestimmt, ob ein `multiset`\-Objekt größer als ein anderes `multiset`\-Objekt ist.|  
|[operator\>\= \(multiset\)](../dotnet/operator-greater-or-equal-multiset-stl-clr.md)|Bestimmt, ob ein `multiset`\-Objekt größer oder gleich einem anderen `multiset`\-Objekt ist.|  
  
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
  
 Das Objekt ordnet die Sequenz, die steuert, indem ein gespeichertes Delegatobjekt des Typs [multiset::key\_compare](../dotnet/multiset-key-compare-stl-clr.md).  Sie können dem gespeicherten Delegatobjekt angeben, wenn Sie das Multiset erstellen; Wenn Sie kein Delegatobjekt angeben, gilt standardmäßig der Vergleich `operator<(key_type, key_type)`.  Sie greifen auf das gespeicherte Objekt zu, indem Sie die Memberfunktion [multiset::key\_comp](../dotnet/multiset-key-comp-stl-clr.md)`()` aufrufen.  
  
 Ein solches Delegatobjekt muss eine genaue schwache Sortierung Schlüsseln des Typs [multiset::key\_type](../dotnet/multiset-key-type-stl-clr.md) festlegen.  Das heißt, für alle zwei Schlüssel `X` und `Y`:  
  
 `key_comp()(X, Y)` gibt die gleichen Auswirkungen auf booleschen jeden Aufruf zurück.  
  
 Wenn `key_comp()(X, Y)` true ist, muss `key_comp()(Y, X)` falsch sein.  
  
 Wenn `key_comp()(X, Y)` true ist, dann wird `X` vor `Y` nach.  
  
 Wenn `!key_comp()(X, Y) && !key_comp()(Y, X)` true ist, werden `X` und `Y` gibt an, um übereinstimmende Reihenfolge zu haben.  
  
 Für jedes Element `X`, das `Y` in der Sequenz gesteuerten vorangeht, ist `key_comp()(Y, X)` falsch. \(Für das Standarddelegatobjekt, verringert wird Schlüssel nie.\) Im Gegensatz Vorlagenklasse [set](../dotnet/set-stl-clr.md), benötigt ein Objekt der Vorlagenklasse `multiset` nicht, dass Tasten für alle Elemente eindeutig sind. \(zwei oder mehrere Tasten können entsprechende Reihenfolge haben.\)  
  
 Jedes Element dient als ey und Wert.  Die Sequenz wird so dargestellt, die Ermittlung, Einfügen und Entfernen eines beliebigen Elements mit Operationen zulässt, die z Logarithmus der Anzahl der Elemente in der Sequenz proportional sind \(logarithmische Zeit\).  Außerdem ein Element Einfügen macht keine Iteratoren ungültig, und ein Element entfernen, Iteratoren ungültig macht nur die am entfernten Element zeigen.  
  
 Ein Multiset unterstützt bidirektionale Iteratoren, dass Sie zu benachbarten Elementen werden kann, dass ein Iterator angegeben werden, der ein Element in der Sequenz gesteuerten festlegt.  Ein spezieller Hauptknoten entspricht dem Iterator, der durch [multiset::end](../dotnet/multiset-end-stl-clr.md)`()` zurückgegeben wird.  Sie können diesen Iterator Dekrementieren, um das letzte Element der gesteuerten Sequenz erreicht, wenn vorhanden.  Sie können einen Multisetiterator erhöhen, um den Hauptknoten erreicht, und vergleicht er dann gleich `end()`.  Sie können jedoch den Iterator nicht möglich, der von `end()` zurückgegeben wird.  
  
 Beachten Sie, dass Sie ein Multisetelement nicht zugreifen können, das direkt die numerische Position angegeben wird \- das erfordert einen Iterator mit wahlfreier Zugriff.  
  
 Ein Multisetiterator speichert ein Handle auf dem zugeordneten Multisetknoten, der wiederum ein Handle auf dem zugeordneten Container speichert.  Sie können Iteratoren nur mit ihren zugeordneten Containerobjekten verwenden.  Ein Multisetiterator bleibt gültig, solange der zugehörige Multisetknoten mit einem Multiset zugeordnet ist.  Darüber hinaus ist ein gültiger dereferencable Iterator \- Sie können ihn verwenden, um auf den Elementwert zuzugreifen oder zu ändern, der festlegt wird \- solange er nicht gleich `end()` ist.  
  
 Ein Element Löschen oder entfernen, wird der Destruktor für den gespeicherten Wert auf.  Die Container Löschen eines Auflistungsobjekts, löscht alle Elemente.  Somit wird sichergestellt ein Container, dessen Elementtyp eine Verweisklasse, ist, dass keine Elemente den Container Beibehaltene Objekte.  Beachten Sie jedoch dem Container Handles `not` bewirkt, zerstören seine Elemente.  
  
## Anforderungen  
 **Header:** \<cliext\/Satz\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [hash\_map](../dotnet/hash-map-stl-clr.md)   
 [hash\_multiset](../dotnet/hash-multiset-stl-clr.md)   
 [hash\_multiset](../dotnet/hash-multiset-stl-clr.md)   
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [map](../dotnet/map-stl-clr.md)   
 [multiset](../dotnet/multiset-stl-clr.md)   
 [set](../dotnet/set-stl-clr.md)   
 [STL\/CLR\-Bibliothek](../dotnet/stl-clr-library-reference.md)