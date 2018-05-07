---
title: Multimap (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::multimap
dev_langs:
- C++
helpviewer_keywords:
- <map> header [STL/CLR]
- <cliext/map> header [STL/CLR]
- multimap class [STL/CLR]
ms.assetid: 3dfe329d-a078-462a-b050-7999ce6110ad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 168c6afec0f8f195d1315a54eff2794f7e3fd07e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="multimap-stlclr"></a>multimap (STL/CLR)
Die Vorlagenklasse beschreibt ein Objekt, das eine Elementsequenz variabler Länge steuert, die bidirektionalen Zugriff hat. Verwenden Sie den Container `multimap` Vewaltung eine Sequenz von Elementen als (fast) mit Lastenausgleich geordneten Struktur der Knoten, jeweils ein Element speichern kann. Ein Element besteht aus einem Schlüssel, für die Anordnung der Sequenz und zugeordneten Werts, der für die fuhr wechselt zusammen.  
  
 In der folgenden Beschreibung `GValue` entspricht:  
  
 `Microsoft::VisualC::StlClr::GenericPair<GKey, GMapped>`  
  
 Dabei gilt:  
  
 `GKey` entspricht dem `Key` , wenn die zweite Datei einen Ref-Typ ist, in diesem Fall wird `Key^`  
  
 `GMapped` entspricht dem `Mapped` , wenn die zweite Datei einen Ref-Typ ist, in diesem Fall wird `Mapped^`  
  
## <a name="syntax"></a>Syntax  
  
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
  
#### <a name="parameters"></a>Parameter  
 Key  
 Der Typ, der die zentrale Komponente eines Elements in der kontrollierten Sequenz.  
  
 Zugeordnet  
 Der Typ der Komponente zusätzliche eines Elements in der kontrollierten Sequenz.  
  
## <a name="members"></a>Member  
  
|Typdefinition|Beschreibung|  
|---------------------|-----------------|  
|[multimap::const_iterator (STL/CLR)](../dotnet/multimap-const-iterator-stl-clr.md)|Der Typ eines konstanten Iterators für die gesteuerte Sequenz.|  
|[multimap::const_reference (STL/CLR)](../dotnet/multimap-const-reference-stl-clr.md)|Der Typ eines konstanten Verweises auf ein Element.|  
|[multimap::const_reverse_iterator (STL/CLR)](../dotnet/multimap-const-reverse-iterator-stl-clr.md)|Der Typ eines konstanten umgekehrten Iterators für die gesteuerte Sequenz.|  
|[multimap::difference_type (STL/CLR)](../dotnet/multimap-difference-type-stl-clr.md)|Der Typ des Abstands zwischen zwei Elementen (möglicherweise mit Vorzeichen).|  
|[multimap::generic_container (STL/CLR)](../dotnet/multimap-generic-container-stl-clr.md)|Der Typ der generischen Schnittstelle für den Container.|  
|[multimap::generic_iterator (STL/CLR)](../dotnet/multimap-generic-iterator-stl-clr.md)|Der Typ eines Iterators für die generische Schnittstelle für den Container.|  
|[multimap::generic_reverse_iterator (STL/CLR)](../dotnet/multimap-generic-reverse-iterator-stl-clr.md)|Der Typ eines umgekehrten Iterators für die generische Schnittstelle für den Container.|  
|[multimap::generic_value (STL/CLR)](../dotnet/multimap-generic-value-stl-clr.md)|Der Typ eines Elements für die generische Schnittstelle für den Container.|  
|[multimap::iterator (STL/CLR)](../dotnet/multimap-iterator-stl-clr.md)|Der Typ eines Iterators für die gesteuerte Sequenz.|  
|[multimap::key_compare (STL/CLR)](../dotnet/multimap-key-compare-stl-clr.md)|Der Delegat für zwei Schlüssel.|  
|[multimap::key_type (STL/CLR)](../dotnet/multimap-key-type-stl-clr.md)|Der Typ eines Sortierschlüssels.|  
|[multimap::mapped_type (STL/CLR)](../dotnet/multimap-mapped-type-stl-clr.md)|Der Typ des zugeordneten Werts, der jedem Schlüssel zugeordnet.|  
|[multimap::reference (STL/CLR)](../dotnet/multimap-reference-stl-clr.md)|Der Typ eines Verweises auf ein Element.|  
|[multimap::reverse_iterator (STL/CLR)](../dotnet/multimap-reverse-iterator-stl-clr.md)|Der Typ eines umgekehrten Iterators für die gesteuerte Sequenz.|  
|[multimap::size_type (STL/CLR)](../dotnet/multimap-size-type-stl-clr.md)|Der Typ eines Abstands zwischen zwei Elementen (negativ).|  
|[multimap::value_compare (STL/CLR)](../dotnet/multimap-value-compare-stl-clr.md)|Der Delegat für zwei Elementwerte.|  
|[multimap::value_type (STL/CLR)](../dotnet/multimap-value-type-stl-clr.md)|Der Typ eines Elements.|  
  
|Memberfunktion|Beschreibung|  
|---------------------|-----------------|  
|[multimap::begin (STL/CLR)](../dotnet/multimap-begin-stl-clr.md)|Legt den Anfang der kontrollierten Sequenz fest.|  
|[multimap::clear (STL/CLR)](../dotnet/multimap-clear-stl-clr.md)|Entfernt alle Elemente.|  
|[multimap::count (STL/CLR)](../dotnet/multimap-count-stl-clr.md)|Zählt die Elemente, die einem angegebenen Schlüssel entsprechen.|  
|[multimap::empty (STL/CLR)](../dotnet/multimap-empty-stl-clr.md)|Testet, ob keine Elemente vorhanden sind.|  
|[multimap::end (STL/CLR)](../dotnet/multimap-end-stl-clr.md)|Legt das Ende der kontrollierten Sequenz fest.|  
|[multimap::equal_range (STL/CLR)](../dotnet/multimap-equal-range-stl-clr.md)|Sucht den Bereich, der einem angegebenen Schlüssel entspricht.|  
|[multimap::erase (STL/CLR)](../dotnet/multimap-erase-stl-clr.md)|Entfernt Elemente an den angegebenen Positionen.|  
|[multimap::find (STL/CLR)](../dotnet/multimap-find-stl-clr.md)|Sucht ein Element, das einem angegebenen Schlüssel entspricht.|  
|[multimap::insert (STL/CLR)](../dotnet/multimap-insert-stl-clr.md)|Fügt Elemente hinzu.|  
|[multimap::key_comp (STL/CLR)](../dotnet/multimap-key-comp-stl-clr.md)|Kopiert der Delegat für zwei Schlüssel.|  
|[multimap::lower_bound (STL/CLR)](../dotnet/multimap-lower-bound-stl-clr.md)|Sucht den Anfang des Bereichs, die einem angegebenen Schlüssel entspricht.|  
|[multimap::make_value (STL/CLR)](../dotnet/multimap-make-value-stl-clr.md)|Erstellt ein Wertobjekt.|  
|[multimap::multimap (STL/CLR)](../dotnet/multimap-multimap-stl-clr.md)|Erstellt ein container-Objekt.|  
|[multimap::rbegin (STL/CLR)](../dotnet/multimap-rbegin-stl-clr.md)|Legt den Anfang der umgekehrten kontrollierten Sequenz fest.|  
|[multimap::rend (STL/CLR)](../dotnet/multimap-rend-stl-clr.md)|Legt das Ende der umgekehrten kontrollierten Sequenz fest.|  
|[multimap::size (STL/CLR)](../dotnet/multimap-size-stl-clr.md)|Ermittelt die Anzahl von Elementen.|  
|[multimap::swap (STL/CLR)](../dotnet/multimap-swap-stl-clr.md)|Vertauscht den Inhalt von zwei Containern.|  
|[multimap::to_array (STL/CLR)](../dotnet/multimap-to-array-stl-clr.md)|Kopiert die gesteuerte Sequenz in ein neues Array.|  
|[multimap::upper_bound (STL/CLR)](../dotnet/multimap-upper-bound-stl-clr.md)|Sucht nach Ende des Bereichs, die einem angegebenen Schlüssel entspricht.|  
|[multimap::value_comp (STL/CLR)](../dotnet/multimap-value-comp-stl-clr.md)|Der Delegat für zwei Elementwerte wird kopiert.|  
  
|Operator|Beschreibung|  
|--------------|-----------------|  
|[multimap::operator= (STL/CLR)](../dotnet/multimap-operator-assign-stl-clr.md)|Ersetzt die kontrollierte Sequenz.|  
|[operator!= (multimap) (STL/CLR)](../dotnet/operator-inequality-multimap-stl-clr.md)|Bestimmt, ob eine `multimap` Objekt ist nicht gleich einem anderen `multimap` Objekt.|  
|[operator< (multimap) (STL/CLR)](../dotnet/operator-less-than-multimap-stl-clr.md)|Bestimmt, ob eine `multimap` Objekt ist kleiner als ein anderes `multimap` Objekt.|  
|[operator<= (multimap) (STL/CLR)](../dotnet/operator-less-or-equal-multimap-stl-clr.md)|Bestimmt, ob eine `multimap` Objekt ist kleiner als oder gleich einem anderen `multimap` Objekt.|  
|[operator== (multimap) (STL/CLR)](../dotnet/operator-equality-multimap-stl-clr.md)|Bestimmt, ob eine `multimap` -Objekt gleich einem anderen `multimap` Objekt.|  
|[operator> (multimap) (STL/CLR)](../dotnet/operator-greater-than-multimap-stl-clr.md)|Bestimmt, ob eine `multimap` -Quellobjekt ist größer als ein anderes `multimap` Objekt.|  
|[operator>= (multimap) (STL/CLR)](../dotnet/operator-greater-or-equal-multimap-stl-clr.md)|Bestimmt, ob eine `multimap` Objekt ist größer als oder gleich einem anderen `multimap` Objekt.|  
  
## <a name="interfaces"></a>Schnittstellen  
  
|Interface|Beschreibung|  
|---------------|-----------------|  
|<xref:System.ICloneable>|Duplizieren Sie ein Objekt.|  
|<xref:System.Collections.IEnumerable>|Durch die Elemente der Sequenz.|  
|<xref:System.Collections.ICollection>|Behalten Sie die Gruppe von Elementen.|  
|<xref:System.Collections.Generic.IEnumerable%601>|Durch die Elemente der typisierte Sequenz.|  
|<xref:System.Collections.Generic.ICollection%601>|Behalten Sie die Gruppe von typisierten Elementen.|  
|ITree\<Schlüssel, Wert >|Verwalten von generischen Container.|  
  
## <a name="remarks"></a>Hinweise  
 Das Objekt weist und Speicherplatz für die Sequenz, die als einzelne Knoten Steuersoftware frei. Er fügt Elemente in einen (fast) ausgewogenen Baum, den darin geordnete die Links zwischen Knoten sind, nie durch Kopieren den Inhalt eines Knotens zu einem anderen ändern. Bedeutet, dass Sie einfügen können, und Elemente beliebig ohne beunruhigende verbleibenden Elemente entfernen.  
  
 Das Objekt sortiert die Sequenz, die sie durch Aufrufen einer gespeicherten Delegatobjekt des Typs steuert [multimap:: key_compare (STL/CLR)](../dotnet/multimap-key-compare-stl-clr.md). Sie können das gespeicherte Delegatobjekt angeben, beim Erstellen der mehrfachzuordnung. Wenn Sie keine Delegatobjekt angeben, wird der Standardwert ist der Vergleich `operator<(key_type, key_type)`. Sie Zugriff auf diesem gespeicherten Objekt durch Aufrufen der Memberfunktion [multimap:: key_comp (STL/CLR)](../dotnet/multimap-key-comp-stl-clr.md)`()`.  
  
 Solche ein Delegatobjekt muss eine strikte schwache Sortierung anwenden auf Schlüssel vom Typ [multimap:: KEY_TYPE (STL/CLR)](../dotnet/multimap-key-type-stl-clr.md). Bedeutet, dass für zwei beliebige Tasten `X` und `Y`:  
  
 `key_comp()(X, Y)` Gibt der gleiche booleschen führen bei jedem Aufruf.  
  
 Wenn `key_comp()(X, Y)` ist "true", klicken Sie dann `key_comp()(Y, X)` muss "false" sein.  
  
 Wenn `key_comp()(X, Y)` ist "true", klicken Sie dann `X` herrscht die verbreitete vor bestellt werden `Y`.  
  
 Wenn `!key_comp()(X, Y) && !key_comp()(Y, X)` ist "true", klicken Sie dann `X` und `Y` gelten als die entsprechende Reihenfolge aufweisen.  
  
 Für ein bestimmtes Element `X` vorausgeht, die `Y` in der gesteuerten Sequenz `key_comp()(Y, X)` lautet "false". (Für das Standardobjekt Delegaten verringern Schlüssel nie im Wert.) Im Gegensatz zur Vorlagenklasse [Zuordnung (STL/CLR)](../dotnet/map-stl-clr.md), ein Objekt der Vorlagenklasse `multimap` erfordert nicht, dass der Schlüssel für alle Elemente eindeutig sind. (Mindestens zwei Tasten können die entsprechende Reihenfolge aufweisen.)  
  
 Jedes Element enthält ein separater Schlüssel und einen zugeordneten Wert. Die Sequenz wird so dargestellt, die Such-, Einfüge- und Entfernung eines beliebigen Elements mit einer Reihen von Vorgängen proportional zum Logarithmus der Anzahl von Elementen in der Sequenz (logarithmischer Zeit) ermöglicht. Darüber hinaus führt das Einfügen eines Elements nicht dazu, dass Iteratoren ungültig werden, und durch das Entfernen eines Elements werden nur solche Iteratoren ungültig, die auf das entfernte Element gezeigt haben.  
  
 Eine mehrfachzuordnung unterstützt bidirektionale Iteratoren, was bedeutet, dass Sie schrittweise können, um benachbarte Elemente, die einen Iterator, der ein Element in der kontrollierten Sequenz angegeben. Ein spezieller Hauptknoten entspricht vom zurückgegebenen Iterator [multimap:: End (STL/CLR)](../dotnet/multimap-end-stl-clr.md)`()`. Dieser Iterator für das letzte Element in der kontrollierten Sequenz erreichen können ggf. verringert werden. Erhöhen Sie einen multimap Iterator für den Hauptknoten zu erreichen, und wird dann Vergleichen gleich `end()`. Aber Sie können nicht dereferenziert werden vom zurückgegebenen Iterator `end()`.  
  
 Beachten Sie, dass Sie können nicht auf eine multimap Element verweist direkt erhält die numerische Position--, die einen Iterator mit zufälligem Zugriff erfordert.  
  
 Ein Iterator multimap speichert ein Handle zum zugeordneten multimap Knoten, die wiederum ein Handle für den zugehörigen Container gespeichert. Sie können nur mit ihrer zugeordneten Containerobjekte Iteratoren verwenden. Multimap-Iterator bleibt gültig, solange die Knoten der zugeordneten multimap einige mehrfachzuordnung zugeordnet ist. Darüber hinaus ein gültiger Iterator ist dereferencable – können sie Zugriff haben und den Elementwert, die er festlegt – ändern, solange er nicht gleich `end()`.  
  
 Löschen oder Entfernen eines Elements ruft der Destruktor für den gespeicherten Wert. Zerstören von dem Container löscht alle Elemente. Somit wird sichergestellt, dass ein Container, dessen Elementtyp eine Verweisklasse ist, dass keine Elemente den Container Überleben. Beachten Sie jedoch, dass ein Container von Handles ist `not` seine Elemente zu zerstören.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext/Map >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [hash_map-Element (STL/CLR)](../dotnet/hash-map-stl-clr.md)   
 [hash_multimap-Element (STL/CLR)](../dotnet/hash-multimap-stl-clr.md)   
 [hash_multiset-Element (STL/CLR)](../dotnet/hash-multiset-stl-clr.md)   
 [Hash_set (STL/CLR)](../dotnet/hash-set-stl-clr.md)   
 [Karte (STL/CLR)](../dotnet/map-stl-clr.md)   
 [Multiset (STL/CLR)](../dotnet/multiset-stl-clr.md)   
 [Legen Sie (STL/CLR)](../dotnet/set-stl-clr.md)   
 [Referenz zur STL/CLR-Bibliothek](../dotnet/stl-clr-library-reference.md)