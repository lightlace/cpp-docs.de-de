---
title: hash_multiset-Element (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::hash_multiset
dev_langs: C++
helpviewer_keywords:
- <cliext/hash_set> header [STL/CLR]
- hash_multiset class [STL/CLR]
- <hash_set> header [STL/CLR]
ms.assetid: 8462bd21-6829-4dd3-ac81-c42d6fdf92f0
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8b98e8d858c154e344320c759ac4a38c1cf78cbf
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="hashmultiset-stlclr"></a>hash_multiset (STL/CLR)
Die Vorlagenklasse beschreibt ein Objekt, das eine Elementsequenz variabler Länge steuert, die bidirektionalen Zugriff hat. Verwenden Sie den Container `hash_multiset` zum Verwalten einer Sequenz von Elementen als Hashtabelle verknüpft jeder Tabelleneintrag speichern eine bidirektionale Liste der Knoten, und jeder Knoten ein Element speichern kann. Der Wert jedes Element wird als Schlüssel für die Anordnung der Sequenz verwendet.  
  
 In der folgenden Beschreibung `GValue` ist identisch mit `GKey`, die wiederum ist identisch mit `Key` , wenn die zweite Datei einen Ref-Typ ist, in diesem Fall wird `Key^`.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<typename Key>  
    ref class hash_multiset  
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
  
## <a name="members"></a>Mitglieder  
  
|Typdefinition|Beschreibung|  
|---------------------|-----------------|  
|[hash_multiset::const_iterator (STL/CLR)](../dotnet/hash-multiset-const-iterator-stl-clr.md)|Der Typ eines konstanten Iterators für die gesteuerte Sequenz.|  
|[hash_multiset::const_reference (STL/CLR)](../dotnet/hash-multiset-const-reference-stl-clr.md)|Der Typ eines konstanten Verweises auf ein Element.|  
|[hash_multiset::const_reverse_iterator (STL/CLR)](../dotnet/hash-multiset-const-reverse-iterator-stl-clr.md)|Der Typ eines konstanten umgekehrten Iterators für die gesteuerte Sequenz.|  
|[hash_multiset::difference_type (STL/CLR)](../dotnet/hash-multiset-difference-type-stl-clr.md)|Der Typ des Abstands zwischen zwei Elementen (möglicherweise mit Vorzeichen).|  
|[hash_multiset::generic_container (STL/CLR)](../dotnet/hash-multiset-generic-container-stl-clr.md)|Der Typ der generischen Schnittstelle für den Container.|  
|[hash_multiset::generic_iterator (STL/CLR)](../dotnet/hash-multiset-generic-iterator-stl-clr.md)|Der Typ eines Iterators für die generische Schnittstelle für den Container.|  
|[hash_multiset::generic_reverse_iterator (STL/CLR)](../dotnet/hash-multiset-generic-reverse-iterator-stl-clr.md)|Der Typ eines umgekehrten Iterators für die generische Schnittstelle für den Container.|  
|[hash_multiset::generic_value (STL/CLR)](../dotnet/hash-multiset-generic-value-stl-clr.md)|Der Typ eines Elements für die generische Schnittstelle für den Container.|  
|[hash_multiset::hasher (STL/CLR)](../dotnet/hash-multiset-hasher-stl-clr.md)|Der Hashalgorithmus Delegat für einen Schlüssel.|  
|[hash_multiset::iterator (STL/CLR)](../dotnet/hash-multiset-iterator-stl-clr.md)|Der Typ eines Iterators für die gesteuerte Sequenz.|  
|[hash_multiset::key_compare (STL/CLR)](../dotnet/hash-multiset-key-compare-stl-clr.md)|Der Delegat für zwei Schlüssel.|  
|[hash_multiset::key_type (STL/CLR)](../dotnet/hash-multiset-key-type-stl-clr.md)|Der Typ eines Sortierschlüssels.|  
|[hash_multiset::reference (STL/CLR)](../dotnet/hash-multiset-reference-stl-clr.md)|Der Typ eines Verweises auf ein Element.|  
|[hash_multiset::reverse_iterator (STL/CLR)](../dotnet/hash-multiset-reverse-iterator-stl-clr.md)|Der Typ eines umgekehrten Iterators für die gesteuerte Sequenz.|  
|[hash_multiset::size_type (STL/CLR)](../dotnet/hash-multiset-size-type-stl-clr.md)|Der Typ eines Abstands zwischen zwei Elementen (negativ).|  
|[hash_multiset::value_compare (STL/CLR)](../dotnet/hash-multiset-value-compare-stl-clr.md)|Der Delegat für zwei Elementwerte.|  
|[hash_multiset::value_type (STL/CLR)](../dotnet/hash-multiset-value-type-stl-clr.md)|Der Typ eines Elements.|  
  
|Memberfunktion|Beschreibung|  
|---------------------|-----------------|  
|[hash_multiset::begin (STL/CLR)](../dotnet/hash-multiset-begin-stl-clr.md)|Legt den Anfang der kontrollierten Sequenz fest.|  
|[hash_multiset::bucket_count (STL/CLR)](../dotnet/hash-multiset-bucket-count-stl-clr.md)|Zählt die Anzahl der Buckets an.|  
|[hash_multiset::clear (STL/CLR)](../dotnet/hash-multiset-clear-stl-clr.md)|Entfernt alle Elemente.|  
|[hash_multiset::count (STL/CLR)](../dotnet/hash-multiset-count-stl-clr.md)|Zählt die Elemente, die einem angegebenen Schlüssel entsprechen.|  
|[hash_multiset::empty (STL/CLR)](../dotnet/hash-multiset-empty-stl-clr.md)|Testet, ob keine Elemente vorhanden sind.|  
|[hash_multiset::end (STL/CLR)](../dotnet/hash-multiset-end-stl-clr.md)|Legt das Ende der kontrollierten Sequenz fest.|  
|[hash_multiset::equal_range (STL/CLR)](../dotnet/hash-multiset-equal-range-stl-clr.md)|Sucht den Bereich, der einem angegebenen Schlüssel entspricht.|  
|[hash_multiset::erase (STL/CLR)](../dotnet/hash-multiset-erase-stl-clr.md)|Entfernt Elemente an den angegebenen Positionen.|  
|[hash_multiset::find (STL/CLR)](../dotnet/hash-multiset-find-stl-clr.md)|Sucht ein Element, das einem angegebenen Schlüssel entspricht.|  
|[hash_multiset::hash_delegate (STL/CLR)](../dotnet/hash-multiset-hash-delegate-stl-clr.md)|Kopiert den hashing Delegaten für einen Schlüssel an.|  
|[hash_multiset::hash_multiset (STL/CLR)](../dotnet/hash-multiset-hash-multiset-stl-clr.md)|Erstellt ein container-Objekt.|  
|[hash_multiset::insert (STL/CLR)](../dotnet/hash-multiset-insert-stl-clr.md)|Fügt Elemente hinzu.|  
|[hash_multiset::key_comp (STL/CLR)](../dotnet/hash-multiset-key-comp-stl-clr.md)|Kopiert der Delegat für zwei Schlüssel.|  
|[hash_multiset::load_factor (STL/CLR)](../dotnet/hash-multiset-load-factor-stl-clr.md)|Zählt die durchschnittliche Anzahl von Elementen pro Bucket.|  
|[hash_multiset::lower_bound (STL/CLR)](../dotnet/hash-multiset-lower-bound-stl-clr.md)|Sucht den Anfang des Bereichs, die einem angegebenen Schlüssel entspricht.|  
|[hash_multiset::make_value (STL/CLR)](../dotnet/hash-multiset-make-value-stl-clr.md)|Erstellt ein Wertobjekt.|  
|[hash_multiset::max_load_factor (STL/CLR)](../dotnet/hash-multiset-max-load-factor-stl-clr.md)|Ruft die maximale Anzahl von Elementen pro Bucket ab oder legt sie fest.|  
|[hash_multiset::rbegin (STL/CLR)](../dotnet/hash-multiset-rbegin-stl-clr.md)|Legt den Anfang der umgekehrten kontrollierten Sequenz fest.|  
|[hash_multiset::rehash (STL/CLR)](../dotnet/hash-multiset-rehash-stl-clr.md)|Erstellt die Hashtabelle neu.|  
|[hash_multiset::rend (STL/CLR)](../dotnet/hash-multiset-rend-stl-clr.md)|Legt das Ende der umgekehrten kontrollierten Sequenz fest.|  
|[hash_multiset::size (STL/CLR)](../dotnet/hash-multiset-size-stl-clr.md)|Ermittelt die Anzahl von Elementen.|  
|[hash_multiset::swap (STL/CLR)](../dotnet/hash-multiset-swap-stl-clr.md)|Vertauscht den Inhalt von zwei Containern.|  
|[hash_multiset::to_array (STL/CLR)](../dotnet/hash-multiset-to-array-stl-clr.md)|Kopiert die gesteuerte Sequenz in ein neues Array.|  
|[hash_multiset::upper_bound (STL/CLR)](../dotnet/hash-multiset-upper-bound-stl-clr.md)|Sucht nach Ende des Bereichs, die einem angegebenen Schlüssel entspricht.|  
|[hash_multiset::value_comp (STL/CLR)](../dotnet/hash-multiset-value-comp-stl-clr.md)|Der Delegat für zwei Elementwerte wird kopiert.|  
  
|Operator|Beschreibung|  
|--------------|-----------------|  
|[hash_multiset::operator= (STL/CLR)](../dotnet/hash-multiset-operator-assign-stl-clr.md)|Ersetzt die kontrollierte Sequenz.|  
  
## <a name="interfaces"></a>Schnittstellen  
  
|Schnittstelle|Beschreibung|  
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
  
 Beachten Sie, dass der Container nur wird sichergestellt, dass Elemente, deren Schlüssel die entsprechende Reihenfolge aufweisen (und welche Hash auf den gleichen Wert für ganze Zahl) in einem Bucket nebeneinander angeordnet sind. Im Gegensatz zur Vorlagenklasse [Hash_set (STL/CLR)](../dotnet/hash-set-stl-clr.md), ein Objekt der Vorlagenklasse `hash_multiset` erfordert nicht, dass der Schlüssel für alle Elemente eindeutig sind. (Mindestens zwei Tasten können die entsprechende Reihenfolge aufweisen.)  
  
 Das Objekt bestimmt, welche Bucket einen bestimmten Reihenfolge Schlüssel enthalten soll, durch den Aufruf einer gespeicherten Delegatobjekt des Typs [hash_set::hasher (STL/CLR)](../dotnet/hash-set-hasher-stl-clr.md). Sie Zugriff auf diesem gespeicherten Objekt durch Aufrufen der Memberfunktion [hash_set::hash_delegate (STL/CLR)](../dotnet/hash-set-hash-delegate-stl-clr.md) `()` um einen ganzzahligen Wert zu erhalten, die den Schlüsselwert abhängt. Sie können das gespeicherte Delegatobjekt angeben, beim Erstellen von Hash_set; Wenn Sie keine Delegatobjekt angeben, wird der Standardwert ist die Funktion `System::Object::hash_value(key_type)`. Bedeutet, dass für sämtliche Schlüssel `X` und `Y`:  
  
 `hash_delegate()(X)`Gibt den gleichen Ganzzahlergebnis bei jedem Aufruf zurück.  
  
 Wenn `X` und `Y` haben Sie die entsprechende Reihenfolge, klicken Sie dann `hash_delegate()(X)` sollte dasselbe Ergebnis als ganze Zahl zurückgeben `hash_delegate()(Y)`.  
  
 Jedes Element dient als Schlüssel und Wert. Die Sequenz wird so dargestellt, die ermöglicht Such-, Einfüge- und Entfernung eines beliebigen Elements mit einer Reihen von Vorgängen, die unabhängig von der Anzahl der Elemente in der Sequenz (Konstante Zeit)--mindestens das beste aus Fällen wird. Darüber hinaus führt das Einfügen eines Elements nicht dazu, dass Iteratoren ungültig werden, und durch das Entfernen eines Elements werden nur solche Iteratoren ungültig, die auf das entfernte Element gezeigt haben.  
  
 Wenn die Hashwerte nicht gleichmäßig verteilt sind, kann jedoch eine Hashtabelle degenerierte. Im Extremfall – für eine Hashfunktion, die immer den gleichen Wert--zurückgibt werden Such-, Einfüge- und Entfernvorgänge proportional zur Anzahl der Elemente in der Sequenz (lineare Zeit). Der Container versucht wird, wählen Sie eine angemessene Hashfunktion, die mittlere Bucketgröße und Hashtabelle Größe (gesamte Anzahl der Buckets), aber Sie können einige oder alle diese Optionen außer Kraft setzen. Anzeigen, z. B. die Funktionen [hash_set::max_load_factor (STL/CLR)](../dotnet/hash-set-max-load-factor-stl-clr.md) und [hash_set::rehash (STL/CLR)](../dotnet/hash-set-rehash-stl-clr.md).  
  
 Ein hash_multiset-Element unterstützt bidirektionale Iteratoren, was bedeutet, dass Sie schrittweise können, um benachbarte Elemente, die einen Iterator, der ein Element in der kontrollierten Sequenz angegeben. Ein spezieller Hauptknoten entspricht vom zurückgegebenen Iterator [hash_multiset:: End (STL/CLR)](../dotnet/hash-multiset-end-stl-clr.md)`()`. Dieser Iterator für das letzte Element in der kontrollierten Sequenz erreichen können ggf. verringert werden. Sie können einen Hash_multiset-Iterator für den Hauptknoten erreichen erhöhen und wird dann Vergleichen gleich `end()`. Aber Sie können nicht dereferenziert werden vom zurückgegebenen Iterator `end()`.  
  
 Beachten Sie, dass Sie auf ein Hash_multiset-Element, das direkt erhält die numerische Position--, die einen Iterator mit zufälligem Zugriff erfordert verweisen können.  
  
 Ein Iterator hash_multiset-Objekt speichert ein Handle zum Knoten zugeordnete hash_multiset-Objekt, der wiederum ein Handle für den zugehörigen Container speichert. Sie können nur mit ihrer zugeordneten Containerobjekte Iteratoren verwenden. Ein Hash_multiset-Iterator bleibt gültig, solange die Knoten der zugeordneten Hash_multiset einige hash_multiset-Objekt zugeordnet ist. Darüber hinaus ein gültiger Iterator ist dereferencable – können sie Zugriff haben und den Elementwert, die er festlegt – ändern, solange er nicht gleich `end()`.  
  
 Löschen oder Entfernen eines Elements ruft der Destruktor für den gespeicherten Wert. Zerstören von dem Container löscht alle Elemente. Somit wird sichergestellt, dass ein Container, dessen Elementtyp eine Verweisklasse ist, dass keine Elemente den Container Überleben. Beachten Sie jedoch, dass ein Container von Handles ist `not` seine Elemente zu zerstören.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext Hash_set/>  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [hash_map-Element (STL/CLR)](../dotnet/hash-map-stl-clr.md)   
 [hash_multiset-Element](../dotnet/hash-multiset-stl-clr.md)   
 [Hash_set (STL/CLR)](../dotnet/hash-set-stl-clr.md)   
 [Karte (STL/CLR)](../dotnet/map-stl-clr.md)   
 [Multiset (STL/CLR)](../dotnet/multiset-stl-clr.md)   
 [Multiset (STL/CLR)](../dotnet/multiset-stl-clr.md)   
 [Legen Sie (STL/CLR)](../dotnet/set-stl-clr.md)   
 [Referenz zur STL/CLR-Bibliothek](../dotnet/stl-clr-library-reference.md)