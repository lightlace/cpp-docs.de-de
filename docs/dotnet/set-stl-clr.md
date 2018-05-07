---
title: Legen Sie (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::set
dev_langs:
- C++
helpviewer_keywords:
- <cliext/set> header [STL/CLR]
- <set> header [STL/CLR]
- set class [STL/CLR]
ms.assetid: 27d3628c-741a-43a7-bef1-5085536f679e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: d6a7ebf4d15d85cb43a6f7101c70e444067a3f7b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="set-stlclr"></a>set (STL/CLR)
Die Vorlagenklasse beschreibt ein Objekt, das eine Elementsequenz variabler Länge steuert, die bidirektionalen Zugriff hat. Verwenden Sie den Container `set` Vewaltung eine Sequenz von Elementen als (fast) mit Lastenausgleich geordneten Struktur der Knoten, jeweils ein Element speichern kann.  
  
 In der folgenden Beschreibung `GValue` ist identisch mit `GKey`, die wiederum ist identisch mit `Key` , wenn die zweite Datei einen Ref-Typ ist, in diesem Fall wird `Key^`.  
  
## <a name="syntax"></a>Syntax  
  
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
  
#### <a name="parameters"></a>Parameter  
 Key  
 Der Typ, der die zentrale Komponente eines Elements in der kontrollierten Sequenz.  
  
## <a name="members"></a>Member  
  
|Typdefinition|Beschreibung|  
|---------------------|-----------------|  
|[set::const_iterator (STL/CLR)](../dotnet/set-const-iterator-stl-clr.md)|Der Typ eines konstanten Iterators für die gesteuerte Sequenz.|  
|[set::const_reference (STL/CLR)](../dotnet/set-const-reference-stl-clr.md)|Der Typ eines konstanten Verweises auf ein Element.|  
|[set::const_reverse_iterator (STL/CLR)](../dotnet/set-const-reverse-iterator-stl-clr.md)|Der Typ eines konstanten umgekehrten Iterators für die gesteuerte Sequenz.|  
|[set::difference_type (STL/CLR)](../dotnet/set-difference-type-stl-clr.md)|Der Typ des Abstands zwischen zwei Elementen (möglicherweise mit Vorzeichen).|  
|[set::generic_container (STL/CLR)](../dotnet/set-generic-container-stl-clr.md)|Der Typ der generischen Schnittstelle für den Container.|  
|[set::generic_iterator (STL/CLR)](../dotnet/set-generic-iterator-stl-clr.md)|Der Typ eines Iterators für die generische Schnittstelle für den Container.|  
|[set::generic_reverse_iterator (STL/CLR)](../dotnet/set-generic-reverse-iterator-stl-clr.md)|Der Typ eines umgekehrten Iterators für die generische Schnittstelle für den Container.|  
|[set::generic_value (STL/CLR)](../dotnet/set-generic-value-stl-clr.md)|Der Typ eines Elements für die generische Schnittstelle für den Container.|  
|[set::iterator (STL/CLR)](../dotnet/set-iterator-stl-clr.md)|Der Typ eines Iterators für die gesteuerte Sequenz.|  
|[set::key_compare (STL/CLR)](../dotnet/set-key-compare-stl-clr.md)|Der Delegat für zwei Schlüssel.|  
|[set::key_type (STL/CLR)](../dotnet/set-key-type-stl-clr.md)|Der Typ eines Sortierschlüssels.|  
|[set::reference (STL/CLR)](../dotnet/set-reference-stl-clr.md)|Der Typ eines Verweises auf ein Element.|  
|[set::reverse_iterator (STL/CLR)](../dotnet/set-reverse-iterator-stl-clr.md)|Der Typ eines umgekehrten Iterators für die gesteuerte Sequenz.|  
|[set::size_type (STL/CLR)](../dotnet/set-size-type-stl-clr.md)|Der Typ eines Abstands zwischen zwei Elementen (negativ).|  
|[set::value_compare (STL/CLR)](../dotnet/set-value-compare-stl-clr.md)|Der Delegat für zwei Elementwerte.|  
|[set::value_type (STL/CLR)](../dotnet/set-value-type-stl-clr.md)|Der Typ eines Elements.|  
  
|Memberfunktion|Beschreibung|  
|---------------------|-----------------|  
|[set::begin (STL/CLR)](../dotnet/set-begin-stl-clr.md)|Legt den Anfang der kontrollierten Sequenz fest.|  
|[set::clear (STL/CLR)](../dotnet/set-clear-stl-clr.md)|Entfernt alle Elemente.|  
|[set::count (STL/CLR)](../dotnet/set-count-stl-clr.md)|Zählt die Elemente, die einem angegebenen Schlüssel entsprechen.|  
|[set::empty (STL/CLR)](../dotnet/set-empty-stl-clr.md)|Testet, ob keine Elemente vorhanden sind.|  
|[set::end (STL/CLR)](../dotnet/set-end-stl-clr.md)|Legt das Ende der kontrollierten Sequenz fest.|  
|[set::equal_range (STL/CLR)](../dotnet/set-equal-range-stl-clr.md)|Sucht den Bereich, der einem angegebenen Schlüssel entspricht.|  
|[set::erase (STL/CLR)](../dotnet/set-erase-stl-clr.md)|Entfernt Elemente an den angegebenen Positionen.|  
|[set::find (STL/CLR)](../dotnet/set-find-stl-clr.md)|Sucht ein Element, das einem angegebenen Schlüssel entspricht.|  
|[set::insert (STL/CLR)](../dotnet/set-insert-stl-clr.md)|Fügt Elemente hinzu.|  
|[set::key_comp (STL/CLR)](../dotnet/set-key-comp-stl-clr.md)|Kopiert der Delegat für zwei Schlüssel.|  
|[set::lower_bound (STL/CLR)](../dotnet/set-lower-bound-stl-clr.md)|Sucht den Anfang des Bereichs, die einem angegebenen Schlüssel entspricht.|  
|[set::make_value (STL/CLR)](../dotnet/set-make-value-stl-clr.md)|Erstellt ein Wertobjekt.|  
|[set::rbegin (STL/CLR)](../dotnet/set-rbegin-stl-clr.md)|Legt den Anfang der umgekehrten kontrollierten Sequenz fest.|  
|[set::rend (STL/CLR)](../dotnet/set-rend-stl-clr.md)|Legt das Ende der umgekehrten kontrollierten Sequenz fest.|  
|[set::set (STL/CLR)](../dotnet/set-set-stl-clr.md)|Erstellt ein container-Objekt.|  
|[set::size (STL/CLR)](../dotnet/set-size-stl-clr.md)|Ermittelt die Anzahl von Elementen.|  
|[set::swap (STL/CLR)](../dotnet/set-swap-stl-clr.md)|Vertauscht den Inhalt von zwei Containern.|  
|[set::to_array (STL/CLR)](../dotnet/set-to-array-stl-clr.md)|Kopiert die gesteuerte Sequenz in ein neues Array.|  
|[set::upper_bound (STL/CLR)](../dotnet/set-upper-bound-stl-clr.md)|Sucht nach Ende des Bereichs, die einem angegebenen Schlüssel entspricht.|  
|[set::value_comp (STL/CLR)](../dotnet/set-value-comp-stl-clr.md)|Der Delegat für zwei Elementwerte wird kopiert.|  
  
|Operator|Beschreibung|  
|--------------|-----------------|  
|[set::operator= (STL/CLR)](../dotnet/set-operator-assign-stl-clr.md)|Ersetzt die kontrollierte Sequenz.|  
|[operator!= (set) (STL/CLR)](../dotnet/operator-inequality-set-stl-clr.md)|Bestimmt, ob eine `set` Objekt ist nicht gleich einem anderen `set` Objekt.|  
|[operator< (set) (STL/CLR)](../dotnet/operator-less-than-set-stl-clr.md)|Bestimmt, ob eine `set` Objekt ist kleiner als ein anderes `set` Objekt.|  
|[operator<= (set) (STL/CLR)](../dotnet/operator-less-or-equal-set-stl-clr.md)|Bestimmt, ob eine `set` Objekt ist kleiner als oder gleich einem anderen `set` Objekt.|  
|[operator== (set) (STL/CLR)](../dotnet/operator-equality-set-stl-clr.md)|Bestimmt, ob eine `set` -Objekt gleich einem anderen `set` Objekt.|  
|[operator> (set) (STL/CLR)](../dotnet/operator-greater-than-set-stl-clr.md)|Bestimmt, ob eine `set` -Quellobjekt ist größer als ein anderes `set` Objekt.|  
|[operator>= (set) (STL/CLR)](../dotnet/operator-greater-or-equal-set-stl-clr.md)|Bestimmt, ob eine `set` Objekt ist größer als oder gleich einem anderen `set` Objekt.|  
  
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
  
 Das Objekt sortiert die Sequenz, die sie durch Aufrufen einer gespeicherten Delegatobjekt des Typs steuert [Set:: key_compare (STL/CLR)](../dotnet/set-key-compare-stl-clr.md). Sie können das gespeicherte Delegatobjekt angeben, beim Erstellen des Satzes. Wenn Sie keine Delegatobjekt angeben, wird der Standardwert ist der Vergleich `operator<(key_type, key_type)`. Sie Zugriff auf diesem gespeicherten Objekt durch Aufrufen der Memberfunktion [Set:: key_comp (STL/CLR)](../dotnet/set-key-comp-stl-clr.md)`()`.  
  
 Solche ein Delegatobjekt muss eine strikte schwache Sortierung anwenden auf Schlüssel vom Typ [Set:: KEY_TYPE (STL/CLR)](../dotnet/set-key-type-stl-clr.md). Bedeutet, dass für zwei beliebige Tasten `X` und `Y`:  
  
 `key_comp()(X, Y)` Gibt der gleiche booleschen führen bei jedem Aufruf.  
  
 Wenn `key_comp()(X, Y)` ist "true", klicken Sie dann `key_comp()(Y, X)` muss "false" sein.  
  
 Wenn `key_comp()(X, Y)` ist "true", klicken Sie dann `X` herrscht die verbreitete vor bestellt werden `Y`.  
  
 Wenn `!key_comp()(X, Y) && !key_comp()(Y, X)` ist "true", klicken Sie dann `X` und `Y` gelten als die entsprechende Reihenfolge aufweisen.  
  
 Für ein bestimmtes Element `X` vorausgeht, die `Y` in der gesteuerten Sequenz `key_comp()(Y, X)` lautet "false". (Für das Standardobjekt Delegaten verringern Schlüssel nie im Wert.) Im Gegensatz zur Vorlagenklasse [festgelegt](../dotnet/set-stl-clr.md), ein Objekt der Vorlagenklasse `set` erfordert nicht, dass der Schlüssel für alle Elemente eindeutig sind. (Mindestens zwei Tasten können die entsprechende Reihenfolge aufweisen.)  
  
 Jedes Element dient als ein Ey und einen Wert. Die Sequenz wird so dargestellt, die Such-, Einfüge- und Entfernung eines beliebigen Elements mit einer Reihen von Vorgängen proportional zum Logarithmus der Anzahl von Elementen in der Sequenz (logarithmischer Zeit) ermöglicht. Darüber hinaus führt das Einfügen eines Elements nicht dazu, dass Iteratoren ungültig werden, und durch das Entfernen eines Elements werden nur solche Iteratoren ungültig, die auf das entfernte Element gezeigt haben.  
  
 Einen Satz unterstützt bidirektionale Iteratoren, was bedeutet, dass Sie schrittweise können, um benachbarte Elemente, die einen Iterator, der ein Element in der kontrollierten Sequenz angegeben. Ein spezieller Hauptknoten entspricht vom zurückgegebenen Iterator [Set:: End (STL/CLR)](../dotnet/set-end-stl-clr.md)`()`. Dieser Iterator für das letzte Element in der kontrollierten Sequenz erreichen können ggf. verringert werden. Erhöhen Sie einen Set-Iterator für den Hauptknoten zu erreichen, und wird dann Vergleichen gleich `end()`. Aber Sie können nicht dereferenziert werden vom zurückgegebenen Iterator `end()`.  
  
 Beachten Sie, dass Sie verweisen können, um eine Set-Element, das direkt erhält die numerische Position--, die einen Iterator mit zufälligem Zugriff erfordert.  
  
 Ein Iterator Satz speichert ein Handle zum Knoten zugeordnet, der wiederum ein Handle für den zugehörigen Container gespeichert. Sie können nur mit ihrer zugeordneten Containerobjekte Iteratoren verwenden. Ein Iterator Satz bleibt gültig, solange die Knoten der zugeordneten Gruppe einige Satz zugeordnet ist. Darüber hinaus ein gültiger Iterator ist dereferencable – können sie Zugriff haben und den Elementwert, die er festlegt – ändern, solange er nicht gleich `end()`.  
  
 Löschen oder Entfernen eines Elements ruft der Destruktor für den gespeicherten Wert. Zerstören von dem Container löscht alle Elemente. Somit wird sichergestellt, dass ein Container, dessen Elementtyp eine Verweisklasse ist, dass keine Elemente den Container Überleben. Beachten Sie jedoch, dass ein Container von Handles ist `not` seine Elemente zu zerstören.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext/Set >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [hash_map-Element (STL/CLR)](../dotnet/hash-map-stl-clr.md)   
 [Hash_set (STL/CLR)](../dotnet/hash-set-stl-clr.md)   
 [Hash_set (STL/CLR)](../dotnet/hash-set-stl-clr.md)   
 [Hash_set (STL/CLR)](../dotnet/hash-set-stl-clr.md)   
 [Karte (STL/CLR)](../dotnet/map-stl-clr.md)   
 [set](../dotnet/set-stl-clr.md)   
 [set](../dotnet/set-stl-clr.md)   
 [Referenz zur STL/CLR-Bibliothek](../dotnet/stl-clr-library-reference.md)