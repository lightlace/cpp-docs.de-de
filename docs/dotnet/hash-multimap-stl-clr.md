---
title: "hash_multimap (STL/CLR)"
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
  - "cliext::hash_multimap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<cliext/hash_map>-Header [STL/CLR]"
  - "<hash_map>-Header [STL/CLR]"
  - "hash_multimap-Klasse [STL/CLR]"
ms.assetid: cd78687b-8a05-48e0-9d22-8b8194ae3b0b
caps.latest.revision: 19
caps.handback.revision: "19"
ms.author: "mblome"
manager: "ghogen"
---
# hash_multimap (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Vorlagenklasse beschreibt ein Objekt, das eine VARYINGLängen\-Folge von Elementen steuert, die bidirektionalen Zugriff hat.  Mit dem Container `hash_multimap`, um eine Sequenz von Elementen als Hashtabelle, jedes Tabellenelement eine bidirektionale verknüpfte Liste von Knoten Speichern, und jeden Knoten zu verwalten ein Element Speichern.  Ein Element besteht eine Schlüssel, für Sortierungen der Sequenz und einen zugeordneten Wert, der entlang der Fahrt anstrebt.  
  
 In der unten stehenden Beschreibung, ist `GValue` identisch:  
  
 `Microsoft::VisualC::StlClr::GenericPair<GKey, GMapped>`  
  
 Hierbei ist:  
  
 `GKey` entspricht `Key`, außer, das zweite ein Referenz\-Typ ist, in diesem Fall wird `Key^` ist  
  
 `GMapped` entspricht `Mapped`, außer, das zweite ein Referenz\-Typ ist, in diesem Fall wird `Mapped^` ist  
  
## Syntax  
  
```  
template<typename Key,  
    typename Mapped>  
    ref class hash_multimap  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        System::Collections::Generic::IList<GValue>,  
        Microsoft::VisualC::StlClr::IHash<Gkey, GValue>  
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
|[hash\_multimap::const\_iterator](../dotnet/hash-multimap-const-iterator-stl-clr.md)|Der Typ eines konstanten Iterators für die gesteuerte Sequenz.|  
|[hash\_multimap::const\_reference](../dotnet/hash-multimap-const-reference-stl-clr.md)|Der Typ eines konstanten Verweises auf ein Element.|  
|[hash\_multimap::const\_reverse\_iterator](../dotnet/hash-multimap-const-reverse-iterator-stl-clr.md)|Der Typ eines konstanten umgekehrten Iterators für die gesteuerte Sequenz.|  
|[hash\_multimap::difference\_type](../dotnet/hash-multimap-difference-type-stl-clr.md)|Der Typ der Abstand eine \(möglicherweise mit Vorzeichen\) zwischen zwei Elementen.|  
|[hash\_multimap::generic\_container](../dotnet/hash-multimap-generic-container-stl-clr.md)|Der Typ der generischen Schnittstelle für den Container.|  
|[hash\_multimap::generic\_iterator](../dotnet/hash-multimap-generic-iterator-stl-clr.md)|Der Typ eines Iterators für die generische Schnittstelle für den Container.|  
|[hash\_multimap::generic\_reverse\_iterator](../dotnet/hash-multimap-generic-reverse-iterator-stl-clr.md)|Der Typ eines umgekehrten Iterators für die generische Schnittstelle für den Container.|  
|[hash\_multimap::generic\_value](../dotnet/hash-multimap-generic-value-stl-clr.md)|Der Typ des Elements für die generische Schnittstelle für den Container.|  
|[hash\_multimap::hasher](../dotnet/hash-multimap-hasher-stl-clr.md)|Der Hashverfahrensdelegat für einen Schlüssel.|  
|[hash\_multimap::iterator](../dotnet/hash-multimap-iterator-stl-clr.md)|Der Typ eines Iterators für die gesteuerte Sequenz.|  
|[hash\_multimap::key\_compare](../dotnet/hash-multimap-key-compare-stl-clr.md)|Der Reihenfolgendelegat für zwei Schlüssel.|  
|[hash\_multimap::key\_type](../dotnet/hash-multimap-key-type-stl-clr.md)|Der Typ eines Sortierschlüssels.|  
|[hash\_multimap::mapped\_type](../dotnet/hash-multimap-mapped-type-stl-clr.md)|Der Typ des zugehörigen Werts jeder zugeordneten Schlüssel zu.|  
|[hash\_multimap::reference](../dotnet/hash-multimap-reference-stl-clr.md)|Der Typ eines Verweises auf ein Element.|  
|[hash\_multimap::reverse\_iterator](../dotnet/hash-multimap-reverse-iterator-stl-clr.md)|Der Typ eines umgekehrten Iterators für die gesteuerte Sequenz.|  
|[hash\_multimap::size\_type](../dotnet/hash-multimap-size-type-stl-clr.md)|Der Typ \(nicht negative a\) Abstands zwischen zwei Elementen.|  
|[hash\_multimap::value\_compare](../dotnet/hash-multimap-value-compare-stl-clr.md)|Der Reihenfolgendelegat für zwei Elementwerte.|  
|[hash\_multimap::value\_type](../dotnet/hash-multimap-value-type-stl-clr.md)|Der Typ eines Elements.|  
  
|Memberfunktion|**Beschreibung**|  
|--------------------|----------------------|  
|[hash\_multimap::begin](../dotnet/hash-multimap-begin-stl-clr.md)|Legt den Anfang der kontrollierten Sequenz fest.|  
|[hash\_multimap::bucket\_count](../dotnet/hash-multimap-bucket-count-stl-clr.md)|Zählt die Anzahl Buckets.|  
|[hash\_multimap::clear](../dotnet/hash-multimap-clear-stl-clr.md)|Entfernt alle Elemente.|  
|[hash\_multimap::count](../dotnet/hash-multimap-count-stl-clr.md)|Zählt die Elemente, die einen angegebenen Schlüssel übereinstimmen.|  
|[hash\_multimap::empty](../dotnet/hash-multimap-empty-stl-clr.md)|Testet, dass keine Elemente vorhanden sind.|  
|[hash\_multimap::end](../dotnet/hash-multimap-end-stl-clr.md)|Legt das Ende der kontrollierten Sequenz fest.|  
|[hash\_multimap::equal\_range](../dotnet/hash-multimap-equal-range-stl-clr.md)|Suchen reichen die mit einem bestimmten Schlüssel.|  
|[hash\_multimap::erase](../dotnet/hash-multimap-erase-stl-clr.md)|Entfernt Elemente an den angegebenen Positionen.|  
|[hash\_multimap::find](../dotnet/hash-multimap-find-stl-clr.md)|Sucht ein Element, der einem angegebenen Schlüssel entspricht.|  
|[hash\_multimap::hash\_delegate](../dotnet/hash-multimap-hash-delegate-stl-clr.md)|Kopiert den Hashverfahrensdelegaten für einen Schlüssel.|  
|[hash\_multimap::hash\_multimap](../dotnet/hash-multimap-hash-multimap-stl-clr.md)|Erstellt ein container\-Objekt.|  
|[hash\_multimap::insert](../dotnet/hash-multimap-insert-stl-clr.md)|Fügt Elemente hinzu.|  
|[hash\_multimap::key\_comp](../dotnet/hash-multimap-key-comp-stl-clr.md)|Kopiert den Reihenfolgendelegaten für zwei Schlüssel.|  
|[hash\_multimap::load\_factor](../dotnet/hash-multimap-load-factor-stl-clr.md)|Zählt die durchschnittliche Anzahl Elemente pro Bucket.|  
|[hash\_multimap::lower\_bound](../dotnet/hash-multimap-lower-bound-stl-clr.md)|Sucht Anfang des Bereichs, der einen angegebenen Schlüssel entspricht.|  
|[hash\_multimap::make\_value](../dotnet/hash-multimap-make-value-stl-clr.md)|Erstellt ein Wertobjekt.|  
|[hash\_multimap::max\_load\_factor](../dotnet/hash-multimap-max-load-factor-stl-clr.md)|Ruft die maximale Elemente pro Bucket fest.|  
|[hash\_multimap::rbegin](../dotnet/hash-multimap-rbegin-stl-clr.md)|Legt den Anfang der umgekehrten kontrollierten Sequenz fest.|  
|[hash\_multimap::rehash](../dotnet/hash-multimap-rehash-stl-clr.md)|Erstellt die Hashtabelle neu.|  
|[hash\_multimap::rend](../dotnet/hash-multimap-rend-stl-clr.md)|Legt das Ende der umgekehrten kontrollierten Sequenz fest.|  
|[hash\_multimap::size](../dotnet/hash-multimap-size-stl-clr.md)|Ermittelt die Anzahl der Elemente.|  
|[hash\_multimap::swap](../dotnet/hash-multimap-swap-stl-clr.md)|Vertauscht den Inhalt von zwei Containern.|  
|[hash\_multimap::to\_array](../dotnet/hash-multimap-to-array-stl-clr.md)|Kopiert die gesteuerte Sequenz zu einem neuen Array.|  
|[hash\_multimap::upper\_bound](../dotnet/hash-multimap-upper-bound-stl-clr.md)|Suchenende des Bereichs, der einen angegebenen Schlüssel entspricht.|  
|[hash\_multimap::value\_comp](../dotnet/hash-multimap-value-comp-stl-clr.md)|Kopiert den Reihenfolgendelegaten für zwei Elementwerte.|  
  
|Operator|**Beschreibung**|  
|--------------|----------------------|  
|[hash\_multimap::operator\=](../dotnet/hash-multimap-operator-assign-stl-clr.md)|Ersetzt die gesteuerte Sequenz.|  
  
## Schnittstellen  
  
|Schnittstelle|**Beschreibung**|  
|-------------------|----------------------|  
|<xref:System.ICloneable>|Ein Objekt duplizieren.|  
|<xref:System.Collections.IEnumerable>|Sequenz durch Elemente.|  
|<xref:System.Collections.ICollection>|Unbegrenztes Beibehalten Elementgruppe bei.|  
|<xref:System.Collections.Generic.IEnumerable`1>|Sequenz von typisierten Elemente.|  
|<xref:System.Collections.Generic.ICollection`1>|Unbegrenztes Beibehalten Gruppe typisierten Elemente bei.|  
|IHashKey \<, Value\>|Warten Sie generischen Container.|  
  
## Hinweise  
 Das Objekt belegt und gibt die Sequenz für Speicher frei, die er als einzelne Knoten in einer bidirektionalen verknüpften Liste steuert.  Um Zugriff zu beschleunigen, verwaltet das Objekt auch ein VARYINGLängen\-Array Zeiger in der Liste \(die Hashtabelle\) bei und effektiv verwaltet die ganze Liste als Sequenz von Unterlisten oder die Buckets.  Es werden Elemente in Bucket, den es Relevanz enthält, indem die Links zwischen Knoten ändert, nie ein, indem der Inhalt von einem Knoten zum anderen kopiert.  Das bedeutet, dass Sie Elemente beunruhigende ohne verbleibende Elemente frei einfügen und löschen können.  
  
 Das Objekt ordnet jeden Bucket, die steuert, indem ein gespeichertes Delegatobjekt des Typs [hash\_set::key\_compare](../dotnet/hash-set-key-compare-stl-clr.md).  Sie können dem gespeicherten Delegatobjekt angeben, wenn Sie das hash\_set erstellen; Wenn Sie kein Delegatobjekt angeben, gilt standardmäßig der Vergleich `operator<=(key_type, key_type)`.  
  
 Sie greifen auf das gespeicherte Delegatobjekt zu, indem Sie die Memberfunktion [hash\_set::key\_comp](../dotnet/hash-set-key-comp-stl-clr.md)`()` aufrufen.  Ein solches Delegatobjekt muss entsprechende Reihenfolge zwischen Schlüsseln des Typs [hash\_set::key\_type](../dotnet/hash-set-key-type-stl-clr.md) definieren.  Das heißt, für alle zwei Schlüssel `X` und `Y`:  
  
 `key_comp()(X, Y)` gibt die gleichen Auswirkungen auf booleschen jeden Aufruf zurück.  
  
 Wenn `key_comp()(X, Y) && key_comp()(Y, X)` true ist, werden `X` und `Y` gibt an, um übereinstimmende Reihenfolge zu haben.  
  
 Jede Reihenfolgenregel, die wie `operator<=(key_type, key_type)`, `operator>=(key_type, key_type)` oder `operator==(key_type, key_type)` verhält, definiert eqivalent Reihenfolge.  
  
 Beachten Sie, dass der Container wird sichergestellt, dass nur Elemente, deren Schlüssel entsprechende Reihenfolge verfügen \(und die denselben Hashwert bilden ganzzahligen\), innerhalb eines Buckets aneinandergrenzen.  Im Gegensatz Vorlagenklasse [hash\_map](../dotnet/hash-map-stl-clr.md), benötigt ein Objekt der Vorlagenklasse `hash_multimap` nicht, dass Tasten für alle Elemente eindeutig sind. \(zwei oder mehrere Tasten können entsprechende Reihenfolge haben.\)  
  
 Das Objekt bestimmt, den Bucket eine angegebene Reihenfolgentaste enthalten soll, indem er ein Delegatobjekt gespeichertes des Typs [hash\_set::hasher](../dotnet/hash-set-hasher-stl-clr.md).  Sie greifen auf das gespeicherte Objekt zu, indem Sie die Memberfunktion [hash\_set::hash\_delegate](../dotnet/hash-set-hash-delegate-stl-clr.md)`()` aufrufen, um einen ganzzahligen Wert zu erhalten, der vom Schlüsselwert abhängt.  Sie können dem gespeicherten Delegatobjekt angeben, wenn Sie das hash\_set erstellen; Wenn Sie kein Delegatobjekt angeben, ist der Standardwert die Funktion `System::Object::hash_value(key_type)`.  Das heißt, für beliebige Schlüssel `X` und `Y`:  
  
 `hash_delegate()(X)` gibt der ganzzahligen gleichen Auswirkungen auf jeden Aufruf zurück.  
  
 Wenn `X` und `Y` entsprechende Reihenfolge haben, sollte `hash_delegate()(X)` den ganzzahligen gleichen Ergebnis wie `hash_delegate()(Y)` zurückgeben.  
  
 Jedes Element enthält eine eigene Schlüssel und einen zugeordneten Wert.  Die Sequenz wird so dargestellt, die Ermittlung, Einfügen und Entfernen eines beliebigen Elements mit Operationen zulässt, das unabhängig von der Anzahl der Elemente in der Sequenz ist \(konstante Zeit\) \- mindestens im am von Situationen.  Außerdem ein Element Einfügen macht keine Iteratoren ungültig, und ein Element entfernen, Iteratoren ungültig macht nur die am entfernten Element zeigen.  
  
 Wenn gehashte Werte jedoch nicht gleichmäßig verteilt werden kann degenerieren eine Hashtabelle.  Im Extrem \- für eine Hashfunktion, die immer den gleichen Wert zurückgibt \- Suche, Einfüge\- und \- Abrufvorgänge zur Anzahl der Elemente in der Sequenz proportional \(linear Zeit\).  Der Container ermittelt, eine angemessene Hashfunktion, eine Durchschnittbucketgröße und eine Hash\-Tabelle Größe \(Gesamtzahl Buckets\) auszuwählen, Sie können jedoch beliebige oder alle diese Optionen überschreiben.  Siehe, beispielsweise, die [hash\_set::max\_load\_factor](../dotnet/hash-set-max-load-factor-stl-clr.md) und [hash\_set::rehash](../dotnet/hash-set-rehash-stl-clr.md).  
  
 Ein hash\_multimap unterstützt bidirektionale Iteratoren, dass Sie zu benachbarten Elementen werden kann, dass ein Iterator angegeben werden, der ein Element in der Sequenz gesteuerten festlegt.  Ein spezieller Hauptknoten entspricht dem Iterator, der durch [hash\_multimap::end](../dotnet/hash-multimap-end-stl-clr.md)`()` zurückgegeben wird.  Sie können diesen Iterator Dekrementieren, um das letzte Element der gesteuerten Sequenz erreicht, wenn vorhanden.  Sie können einen hash\_multimap Iterator erhöhen, um den Hauptknoten erreicht, und vergleicht er dann gleich `end()`.  Sie können jedoch den Iterator nicht möglich, der von `end()` zurückgegeben wird.  
  
 Beachten Sie, dass Sie ein hash\_multimap Element zugreifen können, das direkt die numerische Position angegeben wird \- das erfordert einen Iterator mit wahlfreier Zugriff.  
  
 Ein hash\_multimap Iterator speichert ein Handle auf dem zugeordneten hash\_multimap Knoten, der wiederum ein Handle auf dem zugeordneten Container speichert.  Sie können Iteratoren nur mit ihren zugeordneten Containerobjekten verwenden.  Ein hash\_multimap Iterator bleibt gültig, solange der zugehörige hash\_multimap Knoten mit einigen hash\_multimap zugeordnet ist.  Darüber hinaus ist ein gültiger dereferencable Iterator \- Sie können ihn verwenden, um auf den Elementwert zuzugreifen oder zu ändern, der festlegt wird \- solange er nicht gleich `end()` ist.  
  
 Ein Element Löschen oder entfernen, wird der Destruktor für den gespeicherten Wert auf.  Die Container Löschen eines Auflistungsobjekts, löscht alle Elemente.  Somit wird sichergestellt ein Container, dessen Elementtyp eine Verweisklasse, ist, dass keine Elemente den Container Beibehaltene Objekte.  Beachten Sie jedoch dem Container Handles `not` bewirkt, zerstören seine Elemente.  
  
## Anforderungen  
 **Header:** \<cliext\/hash\_map\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [hash\_map](../dotnet/hash-map-stl-clr.md)   
 [hash\_multiset](../dotnet/hash-multiset-stl-clr.md)   
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [map](../dotnet/map-stl-clr.md)   
 [multimap](../dotnet/multimap-stl-clr.md)   
 [multiset](../dotnet/multiset-stl-clr.md)   
 [set](../dotnet/set-stl-clr.md)   
 [STL\/CLR\-Bibliothek](../dotnet/stl-clr-library-reference.md)