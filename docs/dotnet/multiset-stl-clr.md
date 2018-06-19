---
title: Multiset (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::multiset
dev_langs:
- C++
helpviewer_keywords:
- <cliext/set> header [STL/CLR]
- <set> header [STL/CLR]
- multiset class [STL/CLR]
ms.assetid: 7c46e2b4-cd88-49b7-a9e6-63ad5ae7feb5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 3e01ec2d9c426d6b95b12fe0db9e5a2e328ae1cc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33138482"
---
# <a name="multiset-stlclr"></a>multiset (STL/CLR)
Die Vorlagenklasse beschreibt ein Objekt, das eine Elementsequenz variabler Länge steuert, die bidirektionalen Zugriff hat. Verwenden Sie den Container `multiset` Vewaltung eine Sequenz von Elementen als (fast) mit Lastenausgleich geordneten Struktur der Knoten, jeweils ein Element speichern kann.  
  
 In der folgenden Beschreibung `GValue` ist identisch mit `GKey`, die wiederum ist identisch mit `Key` , wenn die zweite Datei einen Ref-Typ ist, in diesem Fall wird `Key^`.  
  
## <a name="syntax"></a>Syntax  
  
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
  
#### <a name="parameters"></a>Parameter  
 Key  
 Der Typ, der die zentrale Komponente eines Elements in der kontrollierten Sequenz.  
  
## <a name="members"></a>Member  
  
|Typdefinition|Beschreibung|  
|---------------------|-----------------|  
|[multiset::const_iterator (STL/CLR)](../dotnet/multiset-const-iterator-stl-clr.md)|Der Typ eines konstanten Iterators für die gesteuerte Sequenz.|  
|[multiset::const_reference (STL/CLR)](../dotnet/multiset-const-reference-stl-clr.md)|Der Typ eines konstanten Verweises auf ein Element.|  
|[multiset::const_reverse_iterator (STL/CLR)](../dotnet/multiset-const-reverse-iterator-stl-clr.md)|Der Typ eines konstanten umgekehrten Iterators für die gesteuerte Sequenz.|  
|[multiset::difference_type (STL/CLR)](../dotnet/multiset-difference-type-stl-clr.md)|Der Typ des Abstands zwischen zwei Elementen (möglicherweise mit Vorzeichen).|  
|[multiset::generic_container (STL/CLR)](../dotnet/multiset-generic-container-stl-clr.md)|Der Typ der generischen Schnittstelle für den Container.|  
|[multiset::generic_iterator (STL/CLR)](../dotnet/multiset-generic-iterator-stl-clr.md)|Der Typ eines Iterators für die generische Schnittstelle für den Container.|  
|[multiset::generic_reverse_iterator (STL/CLR)](../dotnet/multiset-generic-reverse-iterator-stl-clr.md)|Der Typ eines umgekehrten Iterators für die generische Schnittstelle für den Container.|  
|[multiset::generic_value (STL/CLR)](../dotnet/multiset-generic-value-stl-clr.md)|Der Typ eines Elements für die generische Schnittstelle für den Container.|  
|[multiset::iterator (STL/CLR)](../dotnet/multiset-iterator-stl-clr.md)|Der Typ eines Iterators für die gesteuerte Sequenz.|  
|[multiset::key_compare (STL/CLR)](../dotnet/multiset-key-compare-stl-clr.md)|Der Delegat für zwei Schlüssel.|  
|[multiset::key_type (STL/CLR)](../dotnet/multiset-key-type-stl-clr.md)|Der Typ eines Sortierschlüssels.|  
|[multiset::reference (STL/CLR)](../dotnet/multiset-reference-stl-clr.md)|Der Typ eines Verweises auf ein Element.|  
|[multiset::reverse_iterator (STL/CLR)](../dotnet/multiset-reverse-iterator-stl-clr.md)|Der Typ eines umgekehrten Iterators für die gesteuerte Sequenz.|  
|[multiset::size_type (STL/CLR)](../dotnet/multiset-size-type-stl-clr.md)|Der Typ eines Abstands zwischen zwei Elementen (negativ).|  
|[multiset::value_compare (STL/CLR)](../dotnet/multiset-value-compare-stl-clr.md)|Der Delegat für zwei Elementwerte.|  
|[multiset::value_type (STL/CLR)](../dotnet/multiset-value-type-stl-clr.md)|Der Typ eines Elements.|  
  
|Memberfunktion|Beschreibung|  
|---------------------|-----------------|  
|[multiset::begin (STL/CLR)](../dotnet/multiset-begin-stl-clr.md)|Legt den Anfang der kontrollierten Sequenz fest.|  
|[multiset::clear (STL/CLR)](../dotnet/multiset-clear-stl-clr.md)|Entfernt alle Elemente.|  
|[multiset::count (STL/CLR)](../dotnet/multiset-count-stl-clr.md)|Zählt die Elemente, die einem angegebenen Schlüssel entsprechen.|  
|[multiset::empty (STL/CLR)](../dotnet/multiset-empty-stl-clr.md)|Testet, ob keine Elemente vorhanden sind.|  
|[multiset::end (STL/CLR)](../dotnet/multiset-end-stl-clr.md)|Legt das Ende der kontrollierten Sequenz fest.|  
|[multiset::equal_range (STL/CLR)](../dotnet/multiset-equal-range-stl-clr.md)|Sucht den Bereich, der einem angegebenen Schlüssel entspricht.|  
|[multiset::erase (STL/CLR)](../dotnet/multiset-erase-stl-clr.md)|Entfernt Elemente an den angegebenen Positionen.|  
|[multiset::find (STL/CLR)](../dotnet/multiset-find-stl-clr.md)|Sucht ein Element, das einem angegebenen Schlüssel entspricht.|  
|[multiset::insert (STL/CLR)](../dotnet/multiset-insert-stl-clr.md)|Fügt Elemente hinzu.|  
|[multiset::key_comp (STL/CLR)](../dotnet/multiset-key-comp-stl-clr.md)|Kopiert der Delegat für zwei Schlüssel.|  
|[multiset::lower_bound (STL/CLR)](../dotnet/multiset-lower-bound-stl-clr.md)|Sucht den Anfang des Bereichs, die einem angegebenen Schlüssel entspricht.|  
|[multiset::make_value (STL/CLR)](../dotnet/multiset-make-value-stl-clr.md)|Erstellt ein Wertobjekt.|  
|[multiset::multiset (STL/CLR)](../dotnet/multiset-multiset-stl-clr.md)|Erstellt ein container-Objekt.|  
|[multiset::rbegin (STL/CLR)](../dotnet/multiset-rbegin-stl-clr.md)|Legt den Anfang der umgekehrten kontrollierten Sequenz fest.|  
|[multiset::rend (STL/CLR)](../dotnet/multiset-rend-stl-clr.md)|Legt das Ende der umgekehrten kontrollierten Sequenz fest.|  
|[multiset::size (STL/CLR)](../dotnet/multiset-size-stl-clr.md)|Ermittelt die Anzahl von Elementen.|  
|[multiset::swap (STL/CLR)](../dotnet/multiset-swap-stl-clr.md)|Vertauscht den Inhalt von zwei Containern.|  
|[multiset::to_array (STL/CLR)](../dotnet/multiset-to-array-stl-clr.md)|Kopiert die gesteuerte Sequenz in ein neues Array.|  
|[multiset::upper_bound (STL/CLR)](../dotnet/multiset-upper-bound-stl-clr.md)|Sucht nach Ende des Bereichs, die einem angegebenen Schlüssel entspricht.|  
|[multiset::value_comp (STL/CLR)](../dotnet/multiset-value-comp-stl-clr.md)|Der Delegat für zwei Elementwerte wird kopiert.|  
  
|Operator|Beschreibung|  
|--------------|-----------------|  
|[multiset::operator= (STL/CLR)](../dotnet/multiset-operator-assign-stl-clr.md)|Ersetzt die kontrollierte Sequenz.|  
|[operator!= (multiset) (STL/CLR)](../dotnet/operator-inequality-multiset-stl-clr.md)|Bestimmt, ob eine `multiset` Objekt ist nicht gleich einem anderen `multiset` Objekt.|  
|[operator< (multiset) (STL/CLR)](../dotnet/operator-less-than-multiset-stl-clr.md)|Bestimmt, ob eine `multiset` Objekt ist kleiner als ein anderes `multiset` Objekt.|  
|[operator<= (multiset) (STL/CLR)](../dotnet/operator-less-or-equal-multiset-stl-clr.md)|Bestimmt, ob eine `multiset` Objekt ist kleiner als oder gleich einem anderen `multiset` Objekt.|  
|[operator== (multiset) (STL/CLR)](../dotnet/operator-equality-multiset-stl-clr.md)|Bestimmt, ob eine `multiset` -Objekt gleich einem anderen `multiset` Objekt.|  
|[operator> (multiset) (STL/CLR)](../dotnet/operator-greater-than-multiset-stl-clr.md)|Bestimmt, ob eine `multiset` -Quellobjekt ist größer als ein anderes `multiset` Objekt.|  
|[operator>= (multiset) (STL/CLR)](../dotnet/operator-greater-or-equal-multiset-stl-clr.md)|Bestimmt, ob eine `multiset` Objekt ist größer als oder gleich einem anderen `multiset` Objekt.|  
  
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
  
 Das Objekt sortiert die Sequenz, die sie durch Aufrufen einer gespeicherten Delegatobjekt des Typs steuert [multiset:: key_compare (STL/CLR)](../dotnet/multiset-key-compare-stl-clr.md). Sie können das gespeicherte Delegatobjekt angeben, beim Erstellen der Multimenge; Wenn Sie keine Delegatobjekt angeben, wird der Standardwert ist der Vergleich `operator<(key_type, key_type)`. Sie Zugriff auf diesem gespeicherten Objekt durch Aufrufen der Memberfunktion [multiset:: key_comp (STL/CLR)](../dotnet/multiset-key-comp-stl-clr.md)`()`.  
  
 Solche ein Delegatobjekt muss eine strikte schwache Sortierung anwenden auf Schlüssel vom Typ [multiset:: KEY_TYPE (STL/CLR)](../dotnet/multiset-key-type-stl-clr.md). Bedeutet, dass für zwei beliebige Tasten `X` und `Y`:  
  
 `key_comp()(X, Y)` Gibt der gleiche booleschen führen bei jedem Aufruf.  
  
 Wenn `key_comp()(X, Y)` ist "true", klicken Sie dann `key_comp()(Y, X)` muss "false" sein.  
  
 Wenn `key_comp()(X, Y)` ist "true", klicken Sie dann `X` herrscht die verbreitete vor bestellt werden `Y`.  
  
 Wenn `!key_comp()(X, Y) && !key_comp()(Y, X)` ist "true", klicken Sie dann `X` und `Y` gelten als die entsprechende Reihenfolge aufweisen.  
  
 Für ein bestimmtes Element `X` vorausgeht, die `Y` in der gesteuerten Sequenz `key_comp()(Y, X)` lautet "false". (Für das Standardobjekt Delegaten verringern Schlüssel nie im Wert.) Im Gegensatz zur Vorlagenklasse [festgelegt (STL/CLR)](../dotnet/set-stl-clr.md), ein Objekt der Vorlagenklasse `multiset` erfordert nicht, dass der Schlüssel für alle Elemente eindeutig sind. (Mindestens zwei Tasten können die entsprechende Reihenfolge aufweisen.)  
  
 Jedes Element dient als ein Ey und einen Wert. Die Sequenz wird so dargestellt, die Such-, Einfüge- und Entfernung eines beliebigen Elements mit einer Reihen von Vorgängen proportional zum Logarithmus der Anzahl von Elementen in der Sequenz (logarithmischer Zeit) ermöglicht. Darüber hinaus führt das Einfügen eines Elements nicht dazu, dass Iteratoren ungültig werden, und durch das Entfernen eines Elements werden nur solche Iteratoren ungültig, die auf das entfernte Element gezeigt haben.  
  
 Eine Multimenge unterstützt bidirektionale Iteratoren, was bedeutet, dass Sie schrittweise können, um benachbarte Elemente, die einen Iterator, der ein Element in der kontrollierten Sequenz angegeben. Ein spezieller Hauptknoten entspricht vom zurückgegebenen Iterator [multiset:: End (STL/CLR)](../dotnet/multiset-end-stl-clr.md)`()`. Dieser Iterator für das letzte Element in der kontrollierten Sequenz erreichen können ggf. verringert werden. Erhöhen Sie einen multiset Iterator für den Hauptknoten zu erreichen, und wird dann Vergleichen gleich `end()`. Aber Sie können nicht dereferenziert werden vom zurückgegebenen Iterator `end()`.  
  
 Beachten Sie, dass Sie auf ein multiset Element direkt erhält die numerische Position--, die einen Iterator mit zufälligem Zugriff erfordert verweisen können.  
  
 Ein Iterator multiset speichert ein Handle zum zugehörigen multiset Knoten, die wiederum ein Handle für den zugehörigen Container gespeichert. Sie können nur mit ihrer zugeordneten Containerobjekte Iteratoren verwenden. Ein multiset Iterator bleibt gültig, solange die Knoten der zugeordneten multiset einige Multimenge zugeordnet ist. Darüber hinaus ein gültiger Iterator ist dereferencable – können sie Zugriff haben und den Elementwert, die er festlegt – ändern, solange er nicht gleich `end()`.  
  
 Löschen oder Entfernen eines Elements ruft der Destruktor für den gespeicherten Wert. Zerstören von dem Container löscht alle Elemente. Somit wird sichergestellt, dass ein Container, dessen Elementtyp eine Verweisklasse ist, dass keine Elemente den Container Überleben. Beachten Sie jedoch, dass ein Container von Handles ist `not` seine Elemente zu zerstören.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext/Set >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [hash_map-Element (STL/CLR)](../dotnet/hash-map-stl-clr.md)   
 [hash_multiset-Element (STL/CLR)](../dotnet/hash-multiset-stl-clr.md)   
 [hash_multiset-Element (STL/CLR)](../dotnet/hash-multiset-stl-clr.md)   
 [Hash_set (STL/CLR)](../dotnet/hash-set-stl-clr.md)   
 [Karte (STL/CLR)](../dotnet/map-stl-clr.md)   
 [multiset](../dotnet/multiset-stl-clr.md)   
 [Legen Sie (STL/CLR)](../dotnet/set-stl-clr.md)   
 [Referenz zur STL/CLR-Bibliothek](../dotnet/stl-clr-library-reference.md)