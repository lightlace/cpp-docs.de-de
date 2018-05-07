---
title: Hash_set (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_set
dev_langs:
- C++
helpviewer_keywords:
- <cliext/hash_set> header [STL/CLR]
- hash_set class [STL/CLR]
- <hash_set> header [STL/CLR]
ms.assetid: d110e356-ba3e-4e52-9e2d-d997bf975c96
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 63b43a116848ff67deb9c62c04849aa5afc6dbc1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="hashset-stlclr"></a>hash_set (STL/CLR)
Die Vorlagenklasse beschreibt ein Objekt, das eine Elementsequenz variabler Länge steuert, die bidirektionalen Zugriff hat. Verwenden Sie den Container `hash_set` zum Verwalten einer Sequenz von Elementen als Hashtabelle verknüpft jeder Tabelleneintrag speichern eine bidirektionale Liste der Knoten, und jeder Knoten ein Element speichern kann. Der Wert jedes Element wird als Schlüssel für die Anordnung der Sequenz verwendet.  
  
 In der folgenden Beschreibung `GValue` ist identisch mit `GKey`, die wiederum ist identisch mit `Key` , wenn die zweite Datei einen Ref-Typ ist, in diesem Fall wird `Key^`.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<typename Key>  
    ref class hash_set  
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
  
#### <a name="parameters"></a>Parameter  
 Key  
 Der Typ, der die zentrale Komponente eines Elements in der kontrollierten Sequenz.  
  
## <a name="members"></a>Member  
  
|Typdefinition|Beschreibung|  
|---------------------|-----------------|  
|[hash_set::const_iterator (STL/CLR)](../dotnet/hash-set-const-iterator-stl-clr.md)|Der Typ eines konstanten Iterators für die gesteuerte Sequenz.|  
|[hash_set::const_reference (STL/CLR)](../dotnet/hash-set-const-reference-stl-clr.md)|Der Typ eines konstanten Verweises auf ein Element.|  
|[hash_set::const_reverse_iterator (STL/CLR)](../dotnet/hash-set-const-reverse-iterator-stl-clr.md)|Der Typ eines konstanten umgekehrten Iterators für die gesteuerte Sequenz.|  
|[hash_set::difference_type (STL/CLR)](../dotnet/hash-set-difference-type-stl-clr.md)|Der Typ des Abstands zwischen zwei Elementen (möglicherweise mit Vorzeichen).|  
|[hash_set::generic_container (STL/CLR)](../dotnet/hash-set-generic-container-stl-clr.md)|Der Typ der generischen Schnittstelle für den Container.|  
|[hash_set::generic_iterator (STL/CLR)](../dotnet/hash-set-generic-iterator-stl-clr.md)|Der Typ eines Iterators für die generische Schnittstelle für den Container.|  
|[hash_set::generic_reverse_iterator (STL/CLR)](../dotnet/hash-set-generic-reverse-iterator-stl-clr.md)|Der Typ eines umgekehrten Iterators für die generische Schnittstelle für den Container.|  
|[hash_set::generic_value (STL/CLR)](../dotnet/hash-set-generic-value-stl-clr.md)|Der Typ eines Elements für die generische Schnittstelle für den Container.|  
|[hash_set::hasher (STL/CLR)](../dotnet/hash-set-hasher-stl-clr.md)|Der Hashalgorithmus Delegat für einen Schlüssel.|  
|[hash_set::iterator (STL/CLR)](../dotnet/hash-set-iterator-stl-clr.md)|Der Typ eines Iterators für die gesteuerte Sequenz.|  
|[hash_set::key_compare (STL/CLR)](../dotnet/hash-set-key-compare-stl-clr.md)|Der Delegat für zwei Schlüssel.|  
|[hash_set::key_type (STL/CLR)](../dotnet/hash-set-key-type-stl-clr.md)|Der Typ eines Sortierschlüssels.|  
|[hash_set::reference (STL/CLR)](../dotnet/hash-set-reference-stl-clr.md)|Der Typ eines Verweises auf ein Element.|  
|[hash_set::reverse_iterator (STL/CLR)](../dotnet/hash-set-reverse-iterator-stl-clr.md)|Der Typ eines umgekehrten Iterators für die gesteuerte Sequenz.|  
|[hash_set::size_type (STL/CLR)](../dotnet/hash-set-size-type-stl-clr.md)|Der Typ eines Abstands zwischen zwei Elementen (negativ).|  
|[hash_set::value_compare (STL/CLR)](../dotnet/hash-set-value-compare-stl-clr.md)|Der Delegat für zwei Elementwerte.|  
|[hash_set::value_type (STL/CLR)](../dotnet/hash-set-value-type-stl-clr.md)|Der Typ eines Elements.|  
  
|Memberfunktion|Beschreibung|  
|---------------------|-----------------|  
|[hash_set::begin (STL/CLR)](../dotnet/hash-set-begin-stl-clr.md)|Legt den Anfang der kontrollierten Sequenz fest.|  
|[hash_set::bucket_count (STL/CLR)](../dotnet/hash-set-bucket-count-stl-clr.md)|Zählt die Anzahl der Buckets an.|  
|[hash_set::clear (STL/CLR)](../dotnet/hash-set-clear-stl-clr.md)|Entfernt alle Elemente.|  
|[hash_set::count (STL/CLR)](../dotnet/hash-set-count-stl-clr.md)|Zählt die Elemente, die einem angegebenen Schlüssel entsprechen.|  
|[hash_set::empty (STL/CLR)](../dotnet/hash-set-empty-stl-clr.md)|Testet, ob keine Elemente vorhanden sind.|  
|[hash_set::end (STL/CLR)](../dotnet/hash-set-end-stl-clr.md)|Legt das Ende der kontrollierten Sequenz fest.|  
|[hash_set::equal_range (STL/CLR)](../dotnet/hash-set-equal-range-stl-clr.md)|Sucht den Bereich, der einem angegebenen Schlüssel entspricht.|  
|[hash_set::erase (STL/CLR)](../dotnet/hash-set-erase-stl-clr.md)|Entfernt Elemente an den angegebenen Positionen.|  
|[hash_set::find (STL/CLR)](../dotnet/hash-set-find-stl-clr.md)|Sucht ein Element, das einem angegebenen Schlüssel entspricht.|  
|[hash_set::hash_delegate (STL/CLR)](../dotnet/hash-set-hash-delegate-stl-clr.md)|Kopiert den hashing Delegaten für einen Schlüssel an.|  
|[hash_set::hash_set (STL/CLR)](../dotnet/hash-set-hash-set-stl-clr.md)|Erstellt ein container-Objekt.|  
|[hash_set::insert (STL/CLR)](../dotnet/hash-set-insert-stl-clr.md)|Fügt Elemente hinzu.|  
|[hash_set::key_comp (STL/CLR)](../dotnet/hash-set-key-comp-stl-clr.md)|Kopiert der Delegat für zwei Schlüssel.|  
|[hash_set::load_factor (STL/CLR)](../dotnet/hash-set-load-factor-stl-clr.md)|Zählt die durchschnittliche Anzahl von Elementen pro Bucket.|  
|[hash_set::lower_bound (STL/CLR)](../dotnet/hash-set-lower-bound-stl-clr.md)|Sucht den Anfang des Bereichs, die einem angegebenen Schlüssel entspricht.|  
|[hash_set::make_value (STL/CLR)](../dotnet/hash-set-make-value-stl-clr.md)|Erstellt ein Wertobjekt.|  
|[hash_set::max_load_factor (STL/CLR)](../dotnet/hash-set-max-load-factor-stl-clr.md)|Ruft die maximale Anzahl von Elementen pro Bucket ab oder legt sie fest.|  
|[hash_set::rbegin (STL/CLR)](../dotnet/hash-set-rbegin-stl-clr.md)|Legt den Anfang der umgekehrten kontrollierten Sequenz fest.|  
|[hash_set::rehash (STL/CLR)](../dotnet/hash-set-rehash-stl-clr.md)|Erstellt die Hashtabelle neu.|  
|[hash_set::rend (STL/CLR)](../dotnet/hash-set-rend-stl-clr.md)|Legt das Ende der umgekehrten kontrollierten Sequenz fest.|  
|[hash_set::size (STL/CLR)](../dotnet/hash-set-size-stl-clr.md)|Ermittelt die Anzahl von Elementen.|  
|[hash_set::swap (STL/CLR)](../dotnet/hash-set-swap-stl-clr.md)|Vertauscht den Inhalt von zwei Containern.|  
|[hash_set::to_array (STL/CLR)](../dotnet/hash-set-to-array-stl-clr.md)|Kopiert die gesteuerte Sequenz in ein neues Array.|  
|[hash_set::upper_bound (STL/CLR)](../dotnet/hash-set-upper-bound-stl-clr.md)|Sucht nach Ende des Bereichs, die einem angegebenen Schlüssel entspricht.|  
|[hash_set::value_comp (STL/CLR)](../dotnet/hash-set-value-comp-stl-clr.md)|Der Delegat für zwei Elementwerte wird kopiert.|  
  
|Operator|Beschreibung|  
|--------------|-----------------|  
|[hash_set::operator= (STL/CLR)](../dotnet/hash-set-operator-assign-stl-clr.md)|Ersetzt die kontrollierte Sequenz.|  
  
## <a name="interfaces"></a>Schnittstellen  
  
|Interface|Beschreibung|  
|---------------|-----------------|  
|<xref:System.ICloneable>|Duplizieren Sie ein Objekt.|  
|<xref:System.Collections.IEnumerable>|Durch die Elemente der Sequenz.|  
|<xref:System.Collections.ICollection>|Behalten Sie die Gruppe von Elementen.|  
|<xref:System.Collections.Generic.IEnumerable%601>|Durch die Elemente der typisierte Sequenz.|  
|<xref:System.Collections.Generic.ICollection%601>|Behalten Sie die Gruppe von typisierten Elementen.|  
|IHash\<Schlüssel, Wert >|Verwalten von generischen Container.|  
  
## <a name="remarks"></a>Hinweise  
 Das Objekt weist und Speicherplatz für die Sequenz, die als einzelner Knoten in einer verknüpften Liste des bidirektionalen Steuersoftware frei. Um den Zugriff zu beschleunigen, gibt das Objekt auch ein variabler Länge Array von Zeigern in der Liste (die Hashtabelle), effektive Verwaltung der gesamten Liste als Sequenz von Unterlisten, verwaltet oder buckets. Er fügt Elemente in einem Bucket, die darin geordnete die Links zwischen Knoten sind, nie durch Kopieren den Inhalt eines Knotens zu einem anderen ändern. Bedeutet, dass Sie einfügen können, und Elemente beliebig ohne beunruhigende verbleibenden Elemente entfernen.  
  
 Das Objekt ordnet jedem Bucket Steuersoftware durch Aufrufen einer gespeicherten Delegatobjekt des Typs [hash_set:: key_compare (STL/CLR)](../dotnet/hash-set-key-compare-stl-clr.md). Sie können das gespeicherte Delegatobjekt angeben, beim Erstellen von Hash_set; Wenn Sie keine Delegatobjekt angeben, wird der Standardwert ist der Vergleich `operator<=(key_type, key_type)`.  
  
 Sie greifen auf das gespeicherte Delegatobjekt durch Aufrufen der Memberfunktion [hash_set:: key_comp (STL/CLR)](../dotnet/hash-set-key-comp-stl-clr.md)`()`. Solche ein Delegatobjekt muss die entsprechende Reihenfolge zwischen Schlüssel vom Typ definieren [hash_set:: KEY_TYPE (STL/CLR)](../dotnet/hash-set-key-type-stl-clr.md). Bedeutet, dass für zwei beliebige Tasten `X` und `Y`:  
  
 `key_comp()(X, Y)` Gibt der gleiche booleschen führen bei jedem Aufruf.  
  
 Wenn `key_comp()(X, Y) && key_comp()(Y, X)` ist "true", klicken Sie dann `X` und `Y` gelten als die entsprechende Reihenfolge aufweisen.  
  
 Jede Reihenfolge Regel, die sich wie verhält `operator<=(key_type, key_type)`, `operator>=(key_type, key_type)` oder `operator==(key_type, key_type)` Eqivalent Sortierung definiert.  
  
 Beachten Sie, dass der Container nur wird sichergestellt, dass Elemente, deren Schlüssel die entsprechende Reihenfolge aufweisen (und welche Hash auf den gleichen Wert für ganze Zahl) in einem Bucket nebeneinander angeordnet sind. Im Gegensatz zur Vorlagenklasse [Hash_multiset (STL/CLR)](../dotnet/hash-multiset-stl-clr.md), ein Objekt der Vorlagenklasse `hash_set` wird sichergestellt, dass der Schlüssel für alle Elemente eindeutig sind. (Keine zwei Schlüssel verfügen, die entsprechende Reihenfolge.)  
  
 Das Objekt bestimmt, welche Bucket einen bestimmten Reihenfolge Schlüssel enthalten soll, durch den Aufruf einer gespeicherten Delegatobjekt des Typs [hash_set::hasher (STL/CLR)](../dotnet/hash-set-hasher-stl-clr.md). Sie Zugriff auf diesem gespeicherten Objekt durch Aufrufen der Memberfunktion [hash_set::hash_delegate (STL/CLR)](../dotnet/hash-set-hash-delegate-stl-clr.md) `()` um einen ganzzahligen Wert zu erhalten, die den Schlüsselwert abhängt. Sie können das gespeicherte Delegatobjekt angeben, beim Erstellen von Hash_set; Wenn Sie keine Delegatobjekt angeben, wird der Standardwert ist die Funktion `System::Object::hash_value(key_type)`. Bedeutet, dass für sämtliche Schlüssel `X` und `Y`:  
  
 `hash_delegate()(X)` Gibt den gleichen Ganzzahlergebnis bei jedem Aufruf zurück.  
  
 Wenn `X` und `Y` haben Sie die entsprechende Reihenfolge, klicken Sie dann `hash_delegate()(X)` sollte dasselbe Ergebnis als ganze Zahl zurückgeben `hash_delegate()(Y)`.  
  
 Jedes Element dient als Schlüssel und Wert. Die Sequenz wird so dargestellt, die ermöglicht Such-, Einfüge- und Entfernung eines beliebigen Elements mit einer Reihen von Vorgängen, die unabhängig von der Anzahl der Elemente in der Sequenz (Konstante Zeit)--mindestens das beste aus Fällen wird. Darüber hinaus führt das Einfügen eines Elements nicht dazu, dass Iteratoren ungültig werden, und durch das Entfernen eines Elements werden nur solche Iteratoren ungültig, die auf das entfernte Element gezeigt haben.  
  
 Wenn die Hashwerte nicht gleichmäßig verteilt sind, kann jedoch eine Hashtabelle degenerierte. Im Extremfall – für eine Hashfunktion, die immer den gleichen Wert--zurückgibt werden Such-, Einfüge- und Entfernvorgänge proportional zur Anzahl der Elemente in der Sequenz (lineare Zeit). Der Container versucht wird, wählen Sie eine angemessene Hashfunktion, die mittlere Bucketgröße und Hashtabelle Größe (gesamte Anzahl der Buckets), aber Sie können einige oder alle diese Optionen außer Kraft setzen. Anzeigen, z. B. die Funktionen [hash_set::max_load_factor (STL/CLR)](../dotnet/hash-set-max-load-factor-stl-clr.md) und [hash_set::rehash (STL/CLR)](../dotnet/hash-set-rehash-stl-clr.md).  
  
 Ein hash_set-Element unterstützt bidirektionale Iteratoren, was bedeutet, dass Sie schrittweise können, um benachbarte Elemente, die einen Iterator, der ein Element in der kontrollierten Sequenz angegeben. Ein spezieller Hauptknoten entspricht vom zurückgegebenen Iterator [hash_set:: End (STL/CLR)](../dotnet/hash-set-end-stl-clr.md)`()`. Dieser Iterator für das letzte Element in der kontrollierten Sequenz erreichen können ggf. verringert werden. Sie können einen Hash_set-Iterator für den Hauptknoten erreichen erhöhen und wird dann Vergleichen gleich `end()`. Aber Sie können nicht dereferenziert werden vom zurückgegebenen Iterator `end()`.  
  
 Beachten Sie, dass Sie auf ein Hash_set-Element, das direkt erhält die numerische Position--, die einen Iterator mit zufälligem Zugriff erfordert verweisen können.  
  
 Ein Iterator Hash_set speichert ein Handle zum Knoten zugeordnete Hash_set, der wiederum ein Handle für den zugehörigen Container speichert. Sie können nur mit ihrer zugeordneten Containerobjekte Iteratoren verwenden. Ein Iterator Hash_set bleibt gültig, solange die Knoten der zugeordneten Hash_set einige Hash_set zugeordnet ist. Darüber hinaus ein gültiger Iterator ist dereferencable – können sie Zugriff haben und den Elementwert, die er festlegt – ändern, solange er nicht gleich `end()`.  
  
 Löschen oder Entfernen eines Elements ruft der Destruktor für den gespeicherten Wert. Zerstören von dem Container löscht alle Elemente. Somit wird sichergestellt, dass ein Container, dessen Elementtyp eine Verweisklasse ist, dass keine Elemente den Container Überleben. Beachten Sie jedoch, dass ein Container von Handles ist `not` seine Elemente zu zerstören.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext Hash_set/>  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [hash_map-Element (STL/CLR)](../dotnet/hash-map-stl-clr.md)   
 [hash_set](../dotnet/hash-set-stl-clr.md)   
 [hash_set](../dotnet/hash-set-stl-clr.md)   
 [Karte (STL/CLR)](../dotnet/map-stl-clr.md)   
 [Legen Sie (STL/CLR)](../dotnet/set-stl-clr.md)   
 [Legen Sie (STL/CLR)](../dotnet/set-stl-clr.md)   
 [Legen Sie (STL/CLR)](../dotnet/set-stl-clr.md)   
 [Referenz zur STL/CLR-Bibliothek](../dotnet/stl-clr-library-reference.md)