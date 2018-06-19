---
title: Liste (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::list
dev_langs:
- C++
helpviewer_keywords:
- <cliext/list> header [STL/CLR]
- list class [STL/CLR]
- <list> header [STL/CLR]
ms.assetid: a70c45c8-a257-4f6b-8434-b27ff6685bac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 4ff009da3ca29697e9b3affceb424bcd84b9b896
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33141749"
---
# <a name="list-stlclr"></a>list (STL/CLR)
Die Vorlagenklasse beschreibt ein Objekt, das eine Elementsequenz variabler Länge steuert, die bidirektionalen Zugriff hat. Verwenden Sie den Container `list` Vewaltung eine Sequenz von Elementen als bidirektionale verknüpfte Liste von Knoten, jeweils ein Element speichern kann.  
  
 In der folgenden Beschreibung `GValue` ist identisch mit `Value` , wenn die zweite Datei einen Ref-Typ ist, in diesem Fall wird `Value^`.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<typename Value>  
    ref class list  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        Microsoft::VisualC::StlClr::IList<GValue>  
    { ..... };  
```  
  
#### <a name="parameters"></a>Parameter  
 Wert  
 Der Typ eines Elements in der kontrollierten Sequenz.  
  
## <a name="members"></a>Member  
  
|Typdefinition|Beschreibung|  
|---------------------|-----------------|  
|[list::const_iterator (STL/CLR)](../dotnet/list-const-iterator-stl-clr.md)|Der Typ eines konstanten Iterators für die gesteuerte Sequenz.|  
|[list::const_reference (STL/CLR)](../dotnet/list-const-reference-stl-clr.md)|Der Typ eines konstanten Verweises auf ein Element.|  
|[list::const_reverse_iterator (STL/CLR)](../dotnet/list-const-reverse-iterator-stl-clr.md)|Der Typ eines konstanten umgekehrten Iterators für die gesteuerte Sequenz.|  
|[list::difference_type (STL/CLR)](../dotnet/list-difference-type-stl-clr.md)|Der Typ eines Abstands mit Vorzeichen zwischen zwei Elementen.|  
|[list::generic_container (STL/CLR)](../dotnet/list-generic-container-stl-clr.md)|Der Typ der generischen Schnittstelle für den Container.|  
|[list::generic_iterator (STL/CLR)](../dotnet/list-generic-iterator-stl-clr.md)|Der Typ eines Iterators für die generische Schnittstelle für den Container.|  
|[list::generic_reverse_iterator (STL/CLR)](../dotnet/list-generic-reverse-iterator-stl-clr.md)|Der Typ eines umgekehrten Iterators für die generische Schnittstelle für den Container.|  
|[list::generic_value (STL/CLR)](../dotnet/list-generic-value-stl-clr.md)|Der Typ eines Elements für die generische Schnittstelle für den Container.|  
|[list::iterator (STL/CLR)](../dotnet/list-iterator-stl-clr.md)|Der Typ eines Iterators für die gesteuerte Sequenz.|  
|[list::reference (STL/CLR)](../dotnet/list-reference-stl-clr.md)|Der Typ eines Verweises auf ein Element.|  
|[list::reverse_iterator (STL/CLR)](../dotnet/list-reverse-iterator-stl-clr.md)|Der Typ eines umgekehrten Iterators für die gesteuerte Sequenz.|  
|[list::size_type (STL/CLR)](../dotnet/list-size-type-stl-clr.md)|Der Typ eines Abstands mit Vorzeichen zwischen zwei Elementen.|  
|[list::value_type (STL/CLR)](../dotnet/list-value-type-stl-clr.md)|Der Typ eines Elements.|  
  
|Memberfunktion|Beschreibung|  
|---------------------|-----------------|  
|[list::assign (STL/CLR)](../dotnet/list-assign-stl-clr.md)|Ersetzt alle Elemente.|  
|[list::back (STL/CLR)](../dotnet/list-back-stl-clr.md)|Greift auf das letzte Element zu.|  
|[list::begin (STL/CLR)](../dotnet/list-begin-stl-clr.md)|Legt den Anfang der kontrollierten Sequenz fest.|  
|[list::clear (STL/CLR)](../dotnet/list-clear-stl-clr.md)|Entfernt alle Elemente.|  
|[list::empty (STL/CLR)](../dotnet/list-empty-stl-clr.md)|Testet, ob keine Elemente vorhanden sind.|  
|[list::end (STL/CLR)](../dotnet/list-end-stl-clr.md)|Legt das Ende der kontrollierten Sequenz fest.|  
|[list::erase (STL/CLR)](../dotnet/list-erase-stl-clr.md)|Entfernt Elemente an den angegebenen Positionen.|  
|[list::front (STL/CLR)](../dotnet/list-front-stl-clr.md)|Greift auf das erste Element zu.|  
|[list::insert (STL/CLR)](../dotnet/list-insert-stl-clr.md)|Fügt Elemente an einer angegebenen Position hinzu.|  
|[list::list (STL/CLR)](../dotnet/list-list-stl-clr.md)|Erstellt ein container-Objekt.|  
|[list::merge (STL/CLR)](../dotnet/list-merge-stl-clr.md)|Verbindet zwei kontrollierte Sequenzen sortiert.|  
|[list::pop_back (STL/CLR)](../dotnet/list-pop-back-stl-clr.md)|Entfernt das letzte Element.|  
|[list::pop_front (STL/CLR)](../dotnet/list-pop-front-stl-clr.md)|Entfernt das erste Element.|  
|[list::push_back (STL/CLR)](../dotnet/list-push-back-stl-clr.md)|Fügt ein neues Letztes Element hinzu.|  
|[list::push_front (STL/CLR)](../dotnet/list-push-front-stl-clr.md)|Fügt ein neues erstes Element hinzu.|  
|[list::rbegin (STL/CLR)](../dotnet/list-rbegin-stl-clr.md)|Legt den Anfang der umgekehrten kontrollierten Sequenz fest.|  
|[list::remove (STL/CLR)](../dotnet/list-remove-stl-clr.md)|Entfernt ein Element mit einem angegebenen Wert.|  
|[list::remove_if (STL/CLR)](../dotnet/list-remove-if-stl-clr.md)|Entfernt die Elemente, die einen angegebenen Test bestehen.|  
|[list::rend (STL/CLR)](../dotnet/list-rend-stl-clr.md)|Legt das Ende der umgekehrten kontrollierten Sequenz fest.|  
|[list::resize (STL/CLR)](../dotnet/list-resize-stl-clr.md)|Ändert die Anzahl der Elemente an.|  
|[list::reverse (STL/CLR)](../dotnet/list-reverse-stl-clr.md)|Kehrt die gesteuerte Sequenz.|  
|[list::size (STL/CLR)](../dotnet/list-size-stl-clr.md)|Ermittelt die Anzahl von Elementen.|  
|[list::sort (STL/CLR)](../dotnet/list-sort-stl-clr.md)|Sortiert die gesteuerte Sequenz.|  
|[list::splice (STL/CLR)](../dotnet/list-splice-stl-clr.md)|Erneuert Links zwischen Knoten.|  
|[list::swap (STL/CLR)](../dotnet/list-swap-stl-clr.md)|Vertauscht den Inhalt von zwei Containern.|  
|[list::to_array (STL/CLR)](../dotnet/list-to-array-stl-clr.md)|Kopiert die gesteuerte Sequenz in ein neues Array.|  
|[list::unique (STL/CLR)](../dotnet/list-unique-stl-clr.md)|Entfernt benachbarte Elemente, die einen angegebenen Test bestehen.|  
  
|Eigenschaft|Beschreibung|  
|--------------|-----------------|  
|[list::back_item (STL/CLR)](../dotnet/list-back-item-stl-clr.md)|Greift auf das letzte Element zu.|  
|[list::front_item (STL/CLR)](../dotnet/list-front-item-stl-clr.md)|Greift auf das erste Element zu.|  
  
|Operator|Beschreibung|  
|--------------|-----------------|  
|[list::operator= (STL/CLR)](../dotnet/list-operator-assign-stl-clr.md)|Ersetzt die kontrollierte Sequenz.|  
|[operator!= (list) (STL/CLR)](../dotnet/operator-inequality-list-stl-clr.md)|Bestimmt, ob eine `list` Objekt ist nicht gleich einem anderen `list` Objekt.|  
|[operator< (list) (STL/CLR)](../dotnet/operator-less-than-list-stl-clr.md)|Bestimmt, ob eine `list` Objekt ist kleiner als ein anderes `list` Objekt.|  
|[operator<= (list) (STL/CLR)](../dotnet/operator-less-or-equal-list-stl-clr.md)|Bestimmt, ob eine `list` Objekt ist kleiner als oder gleich einem anderen `list` Objekt.|  
|[operator== (list) (STL/CLR)](../dotnet/operator-equality-list-stl-clr.md)|Bestimmt, ob eine `list` -Objekt gleich einem anderen `list` Objekt.|  
|[operator> (list) (STL/CLR)](../dotnet/operator-greater-than-list-stl-clr.md)|Bestimmt, ob eine `list` -Quellobjekt ist größer als ein anderes `list` Objekt.|  
|[operator>= (list) (STL/CLR)](../dotnet/operator-greater-or-equal-list-stl-clr.md)|Bestimmt, ob eine `list` Objekt ist größer als oder gleich einem anderen `list` Objekt.|  
  
## <a name="interfaces"></a>Schnittstellen  
  
|Interface|Beschreibung|  
|---------------|-----------------|  
|<xref:System.ICloneable>|Duplizieren Sie ein Objekt.|  
|<xref:System.Collections.IEnumerable>|Durch die Elemente der Sequenz.|  
|<xref:System.Collections.ICollection>|Behalten Sie die Gruppe von Elementen.|  
|<xref:System.Collections.Generic.IEnumerable%601>|Durch die Elemente der typisierte Sequenz.|  
|<xref:System.Collections.Generic.ICollection%601>|Behalten Sie die Gruppe von typisierten Elementen.|  
|IList\<Wert >|Verwalten von generischen Container.|  
  
## <a name="remarks"></a>Hinweise  
 Das Objekt weist und Speicherplatz für die Sequenz, die als einzelner Knoten in einer Linkliste von bidirektionalen Steuersoftware frei. Sie ordnet Elemente durch die Links zwischen Knoten, nie durch Kopieren den Inhalt eines Knotens zu einem anderen ändern. Bedeutet, dass Sie einfügen können, und Elemente beliebig ohne beunruhigende verbleibenden Elemente entfernen. Daher ist eine Liste ein guter Kandidat für die zugrunde liegenden Container für die Vorlagenklasse [Warteschlange (STL/CLR)](../dotnet/queue-stl-clr.md) oder Vorlagenklasse [Stapel (STL/CLR)](../dotnet/stack-stl-clr.md).  
  
 Ein `list` Objekt unterstützt bidirektionale Iteratoren, d. h. Sie können schrittweise um benachbarte Elemente, die einen Iterator, der ein Element in der kontrollierten Sequenz angegeben. Ein spezieller Hauptknoten entspricht vom zurückgegebenen Iterator [List:: End (STL/CLR)](../dotnet/list-end-stl-clr.md)`()`. Dieser Iterator für das letzte Element in der kontrollierten Sequenz erreichen können ggf. verringert werden. Erhöhen Sie einen Listeniterator für den Hauptknoten zu erreichen, und wird dann Vergleichen gleich `end()`. Aber Sie können nicht dereferenziert werden vom zurückgegebenen Iterator `end()`.  
  
 Beachten Sie, dass Sie verweisen können, um ein Listenelement direkt erhält die numerische Position--, die einen Iterator mit zufälligem Zugriff erfordert. Damit wird eine Liste `not` als den zugrunde liegenden Container für die Vorlagenklasse [Priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md).  
  
 Ein Listeniterator speichert ein Handle zum Knoten zugeordneten Liste, die wiederum ein Handle für den zugehörigen Container gespeichert. Sie können nur mit ihrer zugeordneten Containerobjekte Iteratoren verwenden. Ein Listeniterator bleibt gültig, solange der zugeordneten Liste-Knoten mit einer Liste verbunden ist. Darüber hinaus ein gültiger Iterator ist dereferencable – können sie Zugriff haben und den Elementwert, die er festlegt – ändern, solange er nicht gleich `end()`.  
  
 Löschen oder Entfernen eines Elements ruft der Destruktor für den gespeicherten Wert. Zerstören von dem Container löscht alle Elemente. Somit wird sichergestellt, dass ein Container, dessen Elementtyp eine Verweisklasse ist, dass keine Elemente den Container Überleben. Beachten Sie jedoch, dass ein Container von Handles ist `not` seine Elemente zu zerstören.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext/List >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [Deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [Priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)   
 [Warteschlange (STL/CLR)](../dotnet/queue-stl-clr.md)   
 [Stack (STL/CLR)](../dotnet/stack-stl-clr.md)   
 [Vektor (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [Referenz zur STL/CLR-Bibliothek](../dotnet/stl-clr-library-reference.md)