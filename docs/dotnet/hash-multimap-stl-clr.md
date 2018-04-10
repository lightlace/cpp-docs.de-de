---
title: hash_multimap-Element (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- cliext::hash_multimap
dev_langs:
- C++
helpviewer_keywords:
- hash_multimap class [STL/CLR]
- <cliext/hash_map> header [STL/CLR]
- <hash_map> header [STL/CLR]
ms.assetid: cd78687b-8a05-48e0-9d22-8b8194ae3b0b
caps.latest.revision: 19
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: b6927b25d627874f5a3d649099a4ed5e099bc6cb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="hashmultimap-stlclr"></a>hash_multimap (STL/CLR)
Die Vorlagenklasse beschreibt ein Objekt, das eine Elementsequenz variabler Länge steuert, die bidirektionalen Zugriff hat. Verwenden Sie den Container `hash_multimap` zum Verwalten einer Sequenz von Elementen als Hashtabelle verknüpft jeder Tabelleneintrag speichern eine bidirektionale Liste der Knoten, und jeder Knoten ein Element speichern kann. Ein Element besteht aus einem Schlüssel, für die Anordnung der Sequenz und zugeordneten Werts, der für die fuhr wechselt zusammen.  
  
 In der folgenden Beschreibung `GValue` entspricht:  
  
 `Microsoft::VisualC::StlClr::GenericPair<GKey, GMapped>`  
  
 Dabei gilt:  
  
 `GKey`entspricht dem `Key` , wenn die zweite Datei einen Ref-Typ ist, in diesem Fall wird`Key^`  
  
 `GMapped`entspricht dem `Mapped` , wenn die zweite Datei einen Ref-Typ ist, in diesem Fall wird`Mapped^`  
  
## <a name="syntax"></a>Syntax  
  
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
  
#### <a name="parameters"></a>Parameter  
 Key  
 Der Typ, der die zentrale Komponente eines Elements in der kontrollierten Sequenz.  
  
 Zugeordnet  
 Der Typ der Komponente zusätzliche eines Elements in der kontrollierten Sequenz.  
  
## <a name="members"></a>Member  
  
|Typdefinition|Beschreibung|  
|---------------------|-----------------|  
|[hash_multimap::const_iterator (STL/CLR)](../dotnet/hash-multimap-const-iterator-stl-clr.md)|Der Typ eines konstanten Iterators für die gesteuerte Sequenz.|  
|[hash_multimap::const_reference (STL/CLR)](../dotnet/hash-multimap-const-reference-stl-clr.md)|Der Typ eines konstanten Verweises auf ein Element.|  
|[hash_multimap::const_reverse_iterator (STL/CLR)](../dotnet/hash-multimap-const-reverse-iterator-stl-clr.md)|Der Typ eines konstanten umgekehrten Iterators für die gesteuerte Sequenz.|  
|[hash_multimap::difference_type (STL/CLR)](../dotnet/hash-multimap-difference-type-stl-clr.md)|Der Typ des Abstands zwischen zwei Elementen (möglicherweise mit Vorzeichen).|  
|[hash_multimap::generic_container (STL/CLR)](../dotnet/hash-multimap-generic-container-stl-clr.md)|Der Typ der generischen Schnittstelle für den Container.|  
|[hash_multimap::generic_iterator (STL/CLR)](../dotnet/hash-multimap-generic-iterator-stl-clr.md)|Der Typ eines Iterators für die generische Schnittstelle für den Container.|  
|[hash_multimap::generic_reverse_iterator (STL/CLR)](../dotnet/hash-multimap-generic-reverse-iterator-stl-clr.md)|Der Typ eines umgekehrten Iterators für die generische Schnittstelle für den Container.|  
|[hash_multimap::generic_value (STL/CLR)](../dotnet/hash-multimap-generic-value-stl-clr.md)|Der Typ eines Elements für die generische Schnittstelle für den Container.|  
|[hash_multimap::hasher (STL/CLR)](../dotnet/hash-multimap-hasher-stl-clr.md)|Der Hashalgorithmus Delegat für einen Schlüssel.|  
|[hash_multimap::iterator (STL/CLR)](../dotnet/hash-multimap-iterator-stl-clr.md)|Der Typ eines Iterators für die gesteuerte Sequenz.|  
|[hash_multimap::key_compare (STL/CLR)](../dotnet/hash-multimap-key-compare-stl-clr.md)|Der Delegat für zwei Schlüssel.|  
|[hash_multimap::key_type (STL/CLR)](../dotnet/hash-multimap-key-type-stl-clr.md)|Der Typ eines Sortierschlüssels.|  
|[hash_multimap::mapped_type (STL/CLR)](../dotnet/hash-multimap-mapped-type-stl-clr.md)|Der Typ des zugeordneten Werts, der jedem Schlüssel zugeordnet.|  
|[hash_multimap::reference (STL/CLR)](../dotnet/hash-multimap-reference-stl-clr.md)|Der Typ eines Verweises auf ein Element.|  
|[hash_multimap::reverse_iterator (STL/CLR)](../dotnet/hash-multimap-reverse-iterator-stl-clr.md)|Der Typ eines umgekehrten Iterators für die gesteuerte Sequenz.|  
|[hash_multimap::size_type (STL/CLR)](../dotnet/hash-multimap-size-type-stl-clr.md)|Der Typ eines Abstands zwischen zwei Elementen (negativ).|  
|[hash_multimap::value_compare (STL/CLR)](../dotnet/hash-multimap-value-compare-stl-clr.md)|Der Delegat für zwei Elementwerte.|  
|[hash_multimap::value_type (STL/CLR)](../dotnet/hash-multimap-value-type-stl-clr.md)|Der Typ eines Elements.|  
  
|Memberfunktion|Beschreibung|  
|---------------------|-----------------|  
|[hash_multimap::begin (STL/CLR)](../dotnet/hash-multimap-begin-stl-clr.md)|Legt den Anfang der kontrollierten Sequenz fest.|  
|[hash_multimap::bucket_count (STL/CLR)](../dotnet/hash-multimap-bucket-count-stl-clr.md)|Zählt die Anzahl der Buckets an.|  
|[hash_multimap::clear (STL/CLR)](../dotnet/hash-multimap-clear-stl-clr.md)|Entfernt alle Elemente.|  
|[hash_multimap::count (STL/CLR)](../dotnet/hash-multimap-count-stl-clr.md)|Zählt die Elemente, die einem angegebenen Schlüssel entsprechen.|  
|[hash_multimap::empty (STL/CLR)](../dotnet/hash-multimap-empty-stl-clr.md)|Testet, ob keine Elemente vorhanden sind.|  
|[hash_multimap::end (STL/CLR)](../dotnet/hash-multimap-end-stl-clr.md)|Legt das Ende der kontrollierten Sequenz fest.|  
|[hash_multimap::equal_range (STL/CLR)](../dotnet/hash-multimap-equal-range-stl-clr.md)|Sucht den Bereich, der einem angegebenen Schlüssel entspricht.|  
|[hash_multimap::erase (STL/CLR)](../dotnet/hash-multimap-erase-stl-clr.md)|Entfernt Elemente an den angegebenen Positionen.|  
|[hash_multimap::find (STL/CLR)](../dotnet/hash-multimap-find-stl-clr.md)|Sucht ein Element, das einem angegebenen Schlüssel entspricht.|  
|[hash_multimap::hash_delegate (STL/CLR)](../dotnet/hash-multimap-hash-delegate-stl-clr.md)|Kopiert den hashing Delegaten für einen Schlüssel an.|  
|[hash_multimap::hash_multimap (STL/CLR)](../dotnet/hash-multimap-hash-multimap-stl-clr.md)|Erstellt ein container-Objekt.|  
|[hash_multimap::insert (STL/CLR)](../dotnet/hash-multimap-insert-stl-clr.md)|Fügt Elemente hinzu.|  
|[hash_multimap::key_comp (STL/CLR)](../dotnet/hash-multimap-key-comp-stl-clr.md)|Kopiert der Delegat für zwei Schlüssel.|  
|[hash_multimap::load_factor (STL/CLR)](../dotnet/hash-multimap-load-factor-stl-clr.md)|Zählt die durchschnittliche Anzahl von Elementen pro Bucket.|  
|[hash_multimap::lower_bound (STL/CLR)](../dotnet/hash-multimap-lower-bound-stl-clr.md)|Sucht den Anfang des Bereichs, die einem angegebenen Schlüssel entspricht.|  
|[hash_multimap::make_value (STL/CLR)](../dotnet/hash-multimap-make-value-stl-clr.md)|Erstellt ein Wertobjekt.|  
|[hash_multimap::max_load_factor (STL/CLR)](../dotnet/hash-multimap-max-load-factor-stl-clr.md)|Ruft die maximale Anzahl von Elementen pro Bucket ab oder legt sie fest.|  
|[hash_multimap::rbegin (STL/CLR)](../dotnet/hash-multimap-rbegin-stl-clr.md)|Legt den Anfang der umgekehrten kontrollierten Sequenz fest.|  
|[hash_multimap::rehash (STL/CLR)](../dotnet/hash-multimap-rehash-stl-clr.md)|Erstellt die Hashtabelle neu.|  
|[hash_multimap::rend (STL/CLR)](../dotnet/hash-multimap-rend-stl-clr.md)|Legt das Ende der umgekehrten kontrollierten Sequenz fest.|  
|[hash_multimap::size (STL/CLR)](../dotnet/hash-multimap-size-stl-clr.md)|Ermittelt die Anzahl von Elementen.|  
|[hash_multimap::swap (STL/CLR)](../dotnet/hash-multimap-swap-stl-clr.md)|Vertauscht den Inhalt von zwei Containern.|  
|[hash_multimap::to_array (STL/CLR)](../dotnet/hash-multimap-to-array-stl-clr.md)|Kopiert die gesteuerte Sequenz in ein neues Array.|  
|[hash_multimap::upper_bound (STL/CLR)](../dotnet/hash-multimap-upper-bound-stl-clr.md)|Sucht nach Ende des Bereichs, die einem angegebenen Schlüssel entspricht.|  
|[hash_multimap::value_comp (STL/CLR)](../dotnet/hash-multimap-value-comp-stl-clr.md)|Der Delegat für zwei Elementwerte wird kopiert.|  
  
|Operator|Beschreibung|  
|--------------|-----------------|  
|[hash_multimap::operator= (STL/CLR)](../dotnet/hash-multimap-operator-assign-stl-clr.md)|Ersetzt die kontrollierte Sequenz.|  
  
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
  
 `key_comp()(X, Y)`Gibt der gleiche booleschen führen bei jedem Aufruf.  
  
 Wenn `key_comp()(X, Y) && key_comp()(Y, X)` ist "true", klicken Sie dann `X` und `Y` gelten als die entsprechende Reihenfolge aufweisen.  
  
 Jede Reihenfolge Regel, die sich wie verhält `operator<=(key_type, key_type)`, `operator>=(key_type, key_type)` oder `operator==(key_type, key_type)` Eqivalent Sortierung definiert.  
  
 Beachten Sie, dass der Container nur wird sichergestellt, dass Elemente, deren Schlüssel die entsprechende Reihenfolge aufweisen (und welche Hash auf den gleichen Wert für ganze Zahl) in einem Bucket nebeneinander angeordnet sind. Im Gegensatz zur Vorlagenklasse [Hash_map (STL/CLR)](../dotnet/hash-map-stl-clr.md), ein Objekt der Vorlagenklasse `hash_multimap` erfordert nicht, dass der Schlüssel für alle Elemente eindeutig sind. (Mindestens zwei Tasten können die entsprechende Reihenfolge aufweisen.)  
  
 Das Objekt bestimmt, welche Bucket einen bestimmten Reihenfolge Schlüssel enthalten soll, durch den Aufruf einer gespeicherten Delegatobjekt des Typs [hash_set::hasher (STL/CLR)](../dotnet/hash-set-hasher-stl-clr.md). Sie Zugriff auf diesem gespeicherten Objekt durch Aufrufen der Memberfunktion [hash_set::hash_delegate (STL/CLR)](../dotnet/hash-set-hash-delegate-stl-clr.md) `()` um einen ganzzahligen Wert zu erhalten, die den Schlüsselwert abhängt. Sie können das gespeicherte Delegatobjekt angeben, beim Erstellen von Hash_set; Wenn Sie keine Delegatobjekt angeben, wird der Standardwert ist die Funktion `System::Object::hash_value(key_type)`. Bedeutet, dass für sämtliche Schlüssel `X` und `Y`:  
  
 `hash_delegate()(X)`Gibt den gleichen Ganzzahlergebnis bei jedem Aufruf zurück.  
  
 Wenn `X` und `Y` haben Sie die entsprechende Reihenfolge, klicken Sie dann `hash_delegate()(X)` sollte dasselbe Ergebnis als ganze Zahl zurückgeben `hash_delegate()(Y)`.  
  
 Jedes Element enthält ein separater Schlüssel und einen zugeordneten Wert. Die Sequenz wird so dargestellt, die ermöglicht Such-, Einfüge- und Entfernung eines beliebigen Elements mit einer Reihen von Vorgängen, die unabhängig von der Anzahl der Elemente in der Sequenz (Konstante Zeit)--mindestens das beste aus Fällen wird. Darüber hinaus führt das Einfügen eines Elements nicht dazu, dass Iteratoren ungültig werden, und durch das Entfernen eines Elements werden nur solche Iteratoren ungültig, die auf das entfernte Element gezeigt haben.  
  
 Wenn die Hashwerte nicht gleichmäßig verteilt sind, kann jedoch eine Hashtabelle degenerierte. Im Extremfall – für eine Hashfunktion, die immer den gleichen Wert--zurückgibt werden Such-, Einfüge- und Entfernvorgänge proportional zur Anzahl der Elemente in der Sequenz (lineare Zeit). Der Container versucht wird, wählen Sie eine angemessene Hashfunktion, die mittlere Bucketgröße und Hashtabelle Größe (gesamte Anzahl der Buckets), aber Sie können einige oder alle diese Optionen außer Kraft setzen. Anzeigen, z. B. die Funktionen [hash_set::max_load_factor (STL/CLR)](../dotnet/hash-set-max-load-factor-stl-clr.md) und [hash_set::rehash (STL/CLR)](../dotnet/hash-set-rehash-stl-clr.md).  
  
 Ein hash_multimap-Element unterstützt bidirektionale Iteratoren, was bedeutet, dass Sie schrittweise können, um benachbarte Elemente, die einen Iterator, der ein Element in der kontrollierten Sequenz angegeben. Ein spezieller Hauptknoten entspricht vom zurückgegebenen Iterator [hash_multimap:: End (STL/CLR)](../dotnet/hash-multimap-end-stl-clr.md)`()`. Dieser Iterator für das letzte Element in der kontrollierten Sequenz erreichen können ggf. verringert werden. Sie können einen Hash_multimap-Iterator für den Hauptknoten erreichen erhöhen und wird dann Vergleichen gleich `end()`. Aber Sie können nicht dereferenziert werden vom zurückgegebenen Iterator `end()`.  
  
 Beachten Sie, dass Sie auf ein Hash_multimap-Element, das direkt erhält die numerische Position--, die einen Iterator mit zufälligem Zugriff erfordert verweisen können.  
  
 Ein Iterator Hash_multimap speichert ein Handle zum Knoten zugeordnete hash_multimap-Element, der wiederum ein Handle für den zugehörigen Container speichert. Sie können nur mit ihrer zugeordneten Containerobjekte Iteratoren verwenden. Ein Hash_multimap-Iterator bleibt gültig, solange die Knoten der zugeordneten Hash_multimap einige hash_multimap-Element zugeordnet ist. Darüber hinaus ein gültiger Iterator ist dereferencable – können sie Zugriff haben und den Elementwert, die er festlegt – ändern, solange er nicht gleich `end()`.  
  
 Löschen oder Entfernen eines Elements ruft der Destruktor für den gespeicherten Wert. Zerstören von dem Container löscht alle Elemente. Somit wird sichergestellt, dass ein Container, dessen Elementtyp eine Verweisklasse ist, dass keine Elemente den Container Überleben. Beachten Sie jedoch, dass ein Container von Handles ist `not` seine Elemente zu zerstören.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext Hash_map/>  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [hash_map-Element (STL/CLR)](../dotnet/hash-map-stl-clr.md)   
 [hash_multiset-Element (STL/CLR)](../dotnet/hash-multiset-stl-clr.md)   
 [Hash_set (STL/CLR)](../dotnet/hash-set-stl-clr.md)   
 [Karte (STL/CLR)](../dotnet/map-stl-clr.md)   
 [Multimap (STL/CLR)](../dotnet/multimap-stl-clr.md)   
 [Multiset (STL/CLR)](../dotnet/multiset-stl-clr.md)   
 [Legen Sie (STL/CLR)](../dotnet/set-stl-clr.md)   
 [Referenz zur STL/CLR-Bibliothek](../dotnet/stl-clr-library-reference.md)