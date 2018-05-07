---
title: Karte (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::map
dev_langs:
- C++
helpviewer_keywords:
- <map> header [STL/CLR]
- map class [STL/CLR]
- <cliext/map> header [STL/CLR]
ms.assetid: 8b0a7764-b5e4-4175-a802-82b72eb8662a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: cda679ed01e5266f0605639df45940d8f17e506d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="map-stlclr"></a>map (STL/CLR)
Die Vorlagenklasse beschreibt ein Objekt, das eine Elementsequenz variabler Länge steuert, die bidirektionalen Zugriff hat. Verwenden Sie den Container `map` Vewaltung eine Sequenz von Elementen als (fast) mit Lastenausgleich geordneten Struktur der Knoten, jeweils ein Element speichern kann. Ein Element besteht aus einem Schlüssel, für die Anordnung der Sequenz und zugeordneten Werts, der für die fuhr wechselt zusammen.  
  
 In der folgenden Beschreibung `GValue` entspricht:  
  
 `Microsoft::VisualC::StlClr::GenericPair<GKey, GMapped>`  
  
 Dabei gilt:  
  
 `GKey` entspricht dem `Key` , wenn die zweite Datei einen Ref-Typ ist, in diesem Fall wird `Key^`  
  
 `GMapped` entspricht dem `Mapped` , wenn die zweite Datei einen Ref-Typ ist, in diesem Fall wird `Mapped^`  
  
## <a name="syntax"></a>Syntax  
  
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
  
#### <a name="parameters"></a>Parameter  
 Key  
 Der Typ, der die zentrale Komponente eines Elements in der kontrollierten Sequenz.  
  
 Zugeordnet  
 Der Typ der Komponente zusätzliche eines Elements in der kontrollierten Sequenz.  
  
## <a name="members"></a>Member  
  
|Typdefinition|Beschreibung|  
|---------------------|-----------------|  
|[map::const_iterator (STL/CLR)](../dotnet/map-const-iterator-stl-clr.md)|Der Typ eines konstanten Iterators für die gesteuerte Sequenz.|  
|[map::const_reference (STL/CLR)](../dotnet/map-const-reference-stl-clr.md)|Der Typ eines konstanten Verweises auf ein Element.|  
|[map::const_reverse_iterator (STL/CLR)](../dotnet/map-const-reverse-iterator-stl-clr.md)|Der Typ eines konstanten umgekehrten Iterators für die gesteuerte Sequenz.|  
|[map::difference_type (STL/CLR)](../dotnet/map-difference-type-stl-clr.md)|Der Typ des Abstands zwischen zwei Elementen (möglicherweise mit Vorzeichen).|  
|[map::generic_container (STL/CLR)](../dotnet/map-generic-container-stl-clr.md)|Der Typ der generischen Schnittstelle für den Container.|  
|[map::generic_iterator (STL/CLR)](../dotnet/map-generic-iterator-stl-clr.md)|Der Typ eines Iterators für die generische Schnittstelle für den Container.|  
|[map::generic_reverse_iterator (STL/CLR)](../dotnet/map-generic-reverse-iterator-stl-clr.md)|Der Typ eines umgekehrten Iterators für die generische Schnittstelle für den Container.|  
|[map::generic_value (STL/CLR)](../dotnet/map-generic-value-stl-clr.md)|Der Typ eines Elements für die generische Schnittstelle für den Container.|  
|[map::iterator (STL/CLR)](../dotnet/map-iterator-stl-clr.md)|Der Typ eines Iterators für die gesteuerte Sequenz.|  
|[map::key_compare (STL/CLR)](../dotnet/map-key-compare-stl-clr.md)|Der Delegat für zwei Schlüssel.|  
|[map::key_type (STL/CLR)](../dotnet/map-key-type-stl-clr.md)|Der Typ eines Sortierschlüssels.|  
|[map::mapped_type (STL/CLR)](../dotnet/map-mapped-type-stl-clr.md)|Der Typ des zugeordneten Werts, der jedem Schlüssel zugeordnet.|  
|[map::reference (STL/CLR)](../dotnet/map-reference-stl-clr.md)|Der Typ eines Verweises auf ein Element.|  
|[map::reverse_iterator (STL/CLR)](../dotnet/map-reverse-iterator-stl-clr.md)|Der Typ eines umgekehrten Iterators für die gesteuerte Sequenz.|  
|[map::size_type (STL/CLR)](../dotnet/map-size-type-stl-clr.md)|Der Typ eines Abstands zwischen zwei Elementen (negativ).|  
|[map::value_compare (STL/CLR)](../dotnet/map-value-compare-stl-clr.md)|Der Delegat für zwei Elementwerte.|  
|[map::value_type (STL/CLR)](../dotnet/map-value-type-stl-clr.md)|Der Typ eines Elements.|  
  
|Memberfunktion|Beschreibung|  
|---------------------|-----------------|  
|[map::begin (STL/CLR)](../dotnet/map-begin-stl-clr.md)|Legt den Anfang der kontrollierten Sequenz fest.|  
|[map::clear (STL/CLR)](../dotnet/map-clear-stl-clr.md)|Entfernt alle Elemente.|  
|[map::count (STL/CLR)](../dotnet/map-count-stl-clr.md)|Zählt die Elemente, die einem angegebenen Schlüssel entsprechen.|  
|[map::empty (STL/CLR)](../dotnet/map-empty-stl-clr.md)|Testet, ob keine Elemente vorhanden sind.|  
|[map::end (STL/CLR)](../dotnet/map-end-stl-clr.md)|Legt das Ende der kontrollierten Sequenz fest.|  
|[map::equal_range (STL/CLR)](../dotnet/map-equal-range-stl-clr.md)|Sucht den Bereich, der einem angegebenen Schlüssel entspricht.|  
|[map::erase (STL/CLR)](../dotnet/map-erase-stl-clr.md)|Entfernt Elemente an den angegebenen Positionen.|  
|[map::find (STL/CLR)](../dotnet/map-find-stl-clr.md)|Sucht ein Element, das einem angegebenen Schlüssel entspricht.|  
|[map::insert (STL/CLR)](../dotnet/map-insert-stl-clr.md)|Fügt Elemente hinzu.|  
|[map::key_comp (STL/CLR)](../dotnet/map-key-comp-stl-clr.md)|Kopiert der Delegat für zwei Schlüssel.|  
|[map::lower_bound (STL/CLR)](../dotnet/map-lower-bound-stl-clr.md)|Sucht den Anfang des Bereichs, die einem angegebenen Schlüssel entspricht.|  
|[map::make_value (STL/CLR)](../dotnet/map-make-value-stl-clr.md)|Erstellt ein Wertobjekt.|  
|[map::map (STL/CLR)](../dotnet/map-map-stl-clr.md)|Erstellt ein container-Objekt.|  
|[map::rbegin (STL/CLR)](../dotnet/map-rbegin-stl-clr.md)|Legt den Anfang der umgekehrten kontrollierten Sequenz fest.|  
|[map::rend (STL/CLR)](../dotnet/map-rend-stl-clr.md)|Legt das Ende der umgekehrten kontrollierten Sequenz fest.|  
|[map::size (STL/CLR)](../dotnet/map-size-stl-clr.md)|Ermittelt die Anzahl von Elementen.|  
|[map::swap (STL/CLR)](../dotnet/map-swap-stl-clr.md)|Vertauscht den Inhalt von zwei Containern.|  
|[map::to_array (STL/CLR)](../dotnet/map-to-array-stl-clr.md)|Kopiert die gesteuerte Sequenz in ein neues Array.|  
|[map::upper_bound (STL/CLR)](../dotnet/map-upper-bound-stl-clr.md)|Sucht nach Ende des Bereichs, die einem angegebenen Schlüssel entspricht.|  
|[map::value_comp (STL/CLR)](../dotnet/map-value-comp-stl-clr.md)|Der Delegat für zwei Elementwerte wird kopiert.|  
  
|Operator|Beschreibung|  
|--------------|-----------------|  
|[map::operator= (STL/CLR)](../dotnet/map-operator-assign-stl-clr.md)|Ersetzt die kontrollierte Sequenz.|  
|[map::operator(STL/CLR)](../dotnet/map-operator-stl-clr.md)|Ein Schlüssel auf den zugehörigen zugeordneten Wert zugeordnet wird.|  
|[operator!= (map) (STL/CLR)](../dotnet/operator-inequality-map-stl-clr.md)|Bestimmt, ob eine `map` Objekt ist nicht gleich einem anderen `map` Objekt.|  
|[operator< (map) (STL/CLR)](../dotnet/operator-less-than-map-stl-clr.md)|Bestimmt, ob eine `map` Objekt ist kleiner als ein anderes `map` Objekt.|  
|[operator<= (map) (STL/CLR)](../dotnet/operator-less-or-equal-map-stl-clr.md)|Bestimmt, ob eine `map` Objekt ist kleiner als oder gleich einem anderen `map` Objekt.|  
|[operator== (map) (STL/CLR)](../dotnet/operator-equality-map-stl-clr.md)|Bestimmt, ob eine `map` -Objekt gleich einem anderen `map` Objekt.|  
|[operator> (map) (STL/CLR)](../dotnet/operator-greater-than-map-stl-clr.md)|Bestimmt, ob eine `map` -Quellobjekt ist größer als ein anderes `map` Objekt.|  
|[operator>= (map) (STL/CLR)](../dotnet/operator-greater-or-equal-map-stl-clr.md)|Bestimmt, ob eine `map` Objekt ist größer als oder gleich einem anderen `map` Objekt.|  
  
## <a name="interfaces"></a>Schnittstellen  
  
|Interface|Beschreibung|  
|---------------|-----------------|  
|<xref:System.ICloneable>|Duplizieren Sie ein Objekt.|  
|<xref:System.Collections.IEnumerable>|Durch die Elemente der Sequenz.|  
|<xref:System.Collections.ICollection>|Behalten Sie die Gruppe von Elementen.|  
|<xref:System.Collections.Generic.IEnumerable%601>|Durch die Elemente der typisierte Sequenz.|  
|<xref:System.Collections.Generic.ICollection%601>|Behalten Sie die Gruppe von typisierten Elementen.|  
|<xref:System.Collections.Generic.IDictionary%602>|Verwalten Sie die Gruppe von {Schlüssel, Wert} Paare.|  
|ITree < Schlüssel, Wert >|Verwalten von generischen Container.|  
  
## <a name="remarks"></a>Hinweise  
 Das Objekt weist und Speicherplatz für die Sequenz, die als einzelne Knoten Steuersoftware frei. Er fügt Elemente in einen (fast) ausgewogenen Baum, den darin geordnete die Links zwischen Knoten sind, nie durch Kopieren den Inhalt eines Knotens zu einem anderen ändern. Bedeutet, dass Sie einfügen können, und Elemente beliebig ohne beunruhigende verbleibenden Elemente entfernen.  
  
 Das Objekt sortiert die Sequenz, die sie durch Aufrufen einer gespeicherten Delegatobjekt des Typs steuert [Map:: key_compare (STL/CLR)](../dotnet/map-key-compare-stl-clr.md). Sie können das gespeicherte Delegatobjekt angeben, beim Erstellen der Zuordnung. Wenn Sie keine Delegatobjekt angeben, wird der Standardwert ist der Vergleich `operator<(key_type, key_type)`. Sie Zugriff auf diesem gespeicherten Objekt durch Aufrufen der Memberfunktion [Map:: key_comp (STL/CLR)](../dotnet/map-key-comp-stl-clr.md)`()`.  
  
 Solche ein Delegatobjekt muss eine strikte schwache Sortierung anwenden auf Schlüssel vom Typ [Map:: KEY_TYPE (STL/CLR)](../dotnet/map-key-type-stl-clr.md). Bedeutet, dass für zwei beliebige Tasten `X` und `Y`:  
  
 `key_comp()(X, Y)` Gibt der gleiche booleschen führen bei jedem Aufruf.  
  
 Wenn `key_comp()(X, Y)` ist "true", klicken Sie dann `key_comp()(Y, X)` muss "false" sein.  
  
 Wenn `key_comp()(X, Y)` ist "true", klicken Sie dann `X` herrscht die verbreitete vor bestellt werden `Y`.  
  
 Wenn `!key_comp()(X, Y) && !key_comp()(Y, X)` ist "true", klicken Sie dann `X` und `Y` gelten als die entsprechende Reihenfolge aufweisen.  
  
 Für ein bestimmtes Element `X` vorausgeht, die `Y` in der gesteuerten Sequenz `key_comp()(Y, X)` lautet "false". (Für das Standardobjekt Delegaten verringern Schlüssel nie im Wert.) Im Gegensatz zur Vorlagenklasse [Zuordnung](../dotnet/map-stl-clr.md), ein Objekt der Vorlagenklasse `map` erfordert nicht, dass der Schlüssel für alle Elemente eindeutig sind. (Mindestens zwei Tasten können die entsprechende Reihenfolge aufweisen.)  
  
 Jedes Element enthält ein separater Schlüssel und einen zugeordneten Wert. Die Sequenz wird so dargestellt, die Such-, Einfüge- und Entfernung eines beliebigen Elements mit einer Reihen von Vorgängen proportional zum Logarithmus der Anzahl von Elementen in der Sequenz (logarithmischer Zeit) ermöglicht. Darüber hinaus führt das Einfügen eines Elements nicht dazu, dass Iteratoren ungültig werden, und durch das Entfernen eines Elements werden nur solche Iteratoren ungültig, die auf das entfernte Element gezeigt haben.  
  
 Eine Karte unterstützt bidirektionale Iteratoren, dies bedeutet, dass Sie schrittweise können, um benachbarte Elemente, die einen Iterator, der ein Element in der kontrollierten Sequenz angegeben. Ein spezieller Hauptknoten entspricht vom zurückgegebenen Iterator [Map:: End (STL/CLR)](../dotnet/map-end-stl-clr.md)`()`. Dieser Iterator für das letzte Element in der kontrollierten Sequenz erreichen können ggf. verringert werden. Erhöhen Sie einen Karte-Iterator für den Hauptknoten zu erreichen, und wird dann Vergleichen gleich `end()`. Aber Sie können nicht dereferenziert werden vom zurückgegebenen Iterator `end()`.  
  
 Beachten Sie, dass Sie verweisen können, um ein kartenelement direkt erhält die numerische Position--, die einen Iterator mit zufälligem Zugriff erfordert.  
  
 Ein Iterator Zuordnung speichert ein Handle zum Knoten zugeordnete Zuordnung, die wiederum ein Handle für den zugehörigen Container gespeichert. Sie können nur mit ihrer zugeordneten Containerobjekte Iteratoren verwenden. Ein Iterator Zuordnung bleibt gültig, solange der zugeordnete Knoten einer Zuordnung zugeordnet ist. Darüber hinaus ein gültiger Iterator ist dereferencable – können sie Zugriff haben und den Elementwert, die er festlegt – ändern, solange er nicht gleich `end()`.  
  
 Löschen oder Entfernen eines Elements ruft der Destruktor für den gespeicherten Wert. Zerstören von dem Container löscht alle Elemente. Somit wird sichergestellt, dass ein Container, dessen Elementtyp eine Verweisklasse ist, dass keine Elemente den Container Überleben. Beachten Sie jedoch, dass ein Container von Handles ist `not` seine Elemente zu zerstören.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext/Map >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [hash_map-Element (STL/CLR)](../dotnet/hash-map-stl-clr.md)   
 [hash_map-Element (STL/CLR)](../dotnet/hash-map-stl-clr.md)   
 [hash_multiset-Element (STL/CLR)](../dotnet/hash-multiset-stl-clr.md)   
 [Hash_set (STL/CLR)](../dotnet/hash-set-stl-clr.md)   
 [Zuordnung](../dotnet/map-stl-clr.md)   
 [Multiset (STL/CLR)](../dotnet/multiset-stl-clr.md)   
 [Legen Sie (STL/CLR)](../dotnet/set-stl-clr.md)   
 [Referenz zur STL/CLR-Bibliothek](../dotnet/stl-clr-library-reference.md)