---
title: Deque (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::deque
dev_langs:
- C++
helpviewer_keywords:
- deque class [STL/CLR]
- <deque> header [STL/CLR]
- <cliext/deque> header [STL/CLR]
ms.assetid: dd669da3-3c0e-45e9-8596-f6b483720941
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9bd847b2641e6670a91d2edf1eb926aca423ad2f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="deque-stlclr"></a>deque (STL/CLR)
Die Vorlagenklasse beschreibt ein Objekt, das eine Elementsequenz variabler Länge steuert, die zufälligen Zugriff hat. Verwenden Sie den Container `deque` um eine Sequenz von Elementen zu verwalten, sieht, die einen zusammenhängenden Block von Speicher, aber die vergrößert oder verkleinert werden, an beiden Enden, ohne die Notwendigkeit, alle verbleibenden Elemente kopieren können. Sie können daher effizient implementieren, eine `double-ended queue`. (Daher den Namen.)  
  
 In der folgenden Beschreibung `GValue` ist identisch mit `Value` , wenn die zweite Datei einen Ref-Typ ist, in diesem Fall wird `Value^`.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<typename Value>  
    ref class deque  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        System::Collections::Generic::IList<GValue>,  
        Microsoft::VisualC::StlClr::IDeque<GValue>  
    { ..... };  
```  
  
#### <a name="parameters"></a>Parameter  
 GValue  
 Der generische Typ eines Elements in der kontrollierten Sequenz.  
  
 Wert  
 Der Typ eines Elements in der kontrollierten Sequenz.  
  
## <a name="members"></a>Member  
  
|Typdefinition|Beschreibung|  
|---------------------|-----------------|  
|[deque::const_iterator (STL/CLR)](../dotnet/deque-const-iterator-stl-clr.md)|Der Typ eines konstanten Iterators für die gesteuerte Sequenz.|  
|[deque::const_reference (STL/CLR)](../dotnet/deque-const-reference-stl-clr.md)|Der Typ eines konstanten Verweises auf ein Element.|  
|[deque::const_reverse_iterator (STL/CLR)](../dotnet/deque-const-reverse-iterator-stl-clr.md)|Der Typ eines konstanten umgekehrten Iterators für die gesteuerte Sequenz.|  
|[deque::difference_type (STL/CLR)](../dotnet/deque-difference-type-stl-clr.md)|Der Typ eines Abstands mit Vorzeichen zwischen zwei Elementen.|  
|[deque::generic_container (STL/CLR)](../dotnet/deque-generic-container-stl-clr.md)|Der Typ der generischen Schnittstelle für den Container.|  
|[deque::generic_iterator (STL/CLR)](../dotnet/deque-generic-iterator-stl-clr.md)|Der Typ eines Iterators für die generische Schnittstelle für den Container.|  
|[deque::generic_reverse_iterator (STL/CLR)](../dotnet/deque-generic-reverse-iterator-stl-clr.md)|Der Typ eines umgekehrten Iterators für die generische Schnittstelle für den Container.|  
|[deque::generic_value (STL/CLR)](../dotnet/deque-generic-value-stl-clr.md)|Der Typ eines Elements für die generische Schnittstelle für den Container.|  
|[deque::iterator (STL/CLR)](../dotnet/deque-iterator-stl-clr.md)|Der Typ eines Iterators für die gesteuerte Sequenz.|  
|[deque::reference (STL/CLR)](../dotnet/deque-reference-stl-clr.md)|Der Typ eines Verweises auf ein Element.|  
|[deque::reverse_iterator (STL/CLR)](../dotnet/deque-reverse-iterator-stl-clr.md)|Der Typ eines umgekehrten Iterators für die gesteuerte Sequenz.|  
|[deque::size_type (STL/CLR)](../dotnet/deque-size-type-stl-clr.md)|Der Typ eines Abstands mit Vorzeichen zwischen zwei Elementen.|  
|[deque::value_type (STL/CLR)](../dotnet/deque-value-type-stl-clr.md)|Der Typ eines Elements.|  
  
|Memberfunktion|Beschreibung|  
|---------------------|-----------------|  
|[deque::assign (STL/CLR)](../dotnet/deque-assign-stl-clr.md)|Ersetzt alle Elemente.|  
|[deque::at (STL/CLR)](../dotnet/deque-at-stl-clr.md)|Greift auf ein Element an einer angegebenen Position zu.|  
|[deque::back (STL/CLR)](../dotnet/deque-back-stl-clr.md)|Greift auf das letzte Element zu.|  
|[deque::begin (STL/CLR)](../dotnet/deque-begin-stl-clr.md)|Legt den Anfang der kontrollierten Sequenz fest.|  
|[deque::clear (STL/CLR)](../dotnet/deque-clear-stl-clr.md)|Entfernt alle Elemente.|  
|[deque::deque (STL/CLR)](../dotnet/deque-deque-stl-clr.md)|Erstellt ein container-Objekt.|  
|[deque::empty (STL/CLR)](../dotnet/deque-empty-stl-clr.md)|Testet, ob keine Elemente vorhanden sind.|  
|[deque::end (STL/CLR)](../dotnet/deque-end-stl-clr.md)|Legt das Ende der kontrollierten Sequenz fest.|  
|[deque::erase (STL/CLR)](../dotnet/deque-erase-stl-clr.md)|Entfernt Elemente an den angegebenen Positionen.|  
|[deque::front (STL/CLR)](../dotnet/deque-front-stl-clr.md)|Greift auf das erste Element zu.|  
|[deque::insert (STL/CLR)](../dotnet/deque-insert-stl-clr.md)|Fügt Elemente an einer angegebenen Position hinzu.|  
|[deque::pop_back (STL/CLR)](../dotnet/deque-pop-back-stl-clr.md)|Entfernt das letzte Element.|  
|[deque::pop_front (STL/CLR)](../dotnet/deque-pop-front-stl-clr.md)|Entfernt das erste Element.|  
|[deque::push_back (STL/CLR)](../dotnet/deque-push-back-stl-clr.md)|Fügt ein neues Letztes Element hinzu.|  
|[deque::push_front (STL/CLR)](../dotnet/deque-push-front-stl-clr.md)|Fügt ein neues erstes Element hinzu.|  
|[deque::rbegin (STL/CLR)](../dotnet/deque-rbegin-stl-clr.md)|Legt den Anfang der umgekehrten kontrollierten Sequenz fest.|  
|[deque::rend (STL/CLR)](../dotnet/deque-rend-stl-clr.md)|Legt das Ende der umgekehrten kontrollierten Sequenz fest.|  
|[deque::resize (STL/CLR)](../dotnet/deque-resize-stl-clr.md)|Ändert die Anzahl der Elemente an.|  
|[deque::size (STL/CLR)](../dotnet/deque-size-stl-clr.md)|Ermittelt die Anzahl von Elementen.|  
|[deque::swap (STL/CLR)](../dotnet/deque-swap-stl-clr.md)|Vertauscht den Inhalt von zwei Containern.|  
|[deque::to_array (STL/CLR)](../dotnet/deque-to-array-stl-clr.md)|Kopiert die gesteuerte Sequenz in ein neues Array.|  
  
|Eigenschaft|Beschreibung|  
|--------------|-----------------|  
|[deque::back_item (STL/CLR)](../dotnet/deque-back-item-stl-clr.md)|Greift auf das letzte Element zu.|  
|[deque::front_item (STL/CLR)](../dotnet/deque-front-item-stl-clr.md)|Greift auf das erste Element zu.|  
  
|Operator|Beschreibung|  
|--------------|-----------------|  
|[deque::operator!= (STL/CLR)](../dotnet/deque-operator-inequality-stl-clr.md)|Bestimmt, ob zwei `deque` -Objekte ungleich sind.|  
|[deque::operator(STL/CLR)](../dotnet/deque-operator-stl-clr.md)|Greift auf ein Element an einer angegebenen Position zu.|  
|[operator< (deque) (STL/CLR)](../dotnet/operator-less-than-deque-stl-clr.md)|Bestimmt, ob eine `deque` Objekt ist kleiner als ein anderes `deque` Objekt.|  
|[operator<= (deque) (STL/CLR)](../dotnet/operator-less-or-equal-deque-stl-clr.md)|Bestimmt, ob eine `deque` Objekt ist kleiner als oder gleich einem anderen `deque` Objekt.|  
|[operator= (deque) (STL/CLR)](../dotnet/operator-assign-deque-stl-clr.md)|Ersetzt die kontrollierte Sequenz.|  
|[operator== (deque) (STL/CLR)](../dotnet/operator-equality-deque-stl-clr.md)|Bestimmt, ob eine `deque` -Objekt gleich einem anderen `deque` Objekt.|  
|[operator> (deque) (STL/CLR)](../dotnet/operator-greater-than-deque-stl-clr.md)|Bestimmt, ob eine `deque` -Quellobjekt ist größer als ein anderes `deque` Objekt.|  
|[operator>= (deque) (STL/CLR)](../dotnet/operator-greater-or-equal-deque-stl-clr.md)|Bestimmt, ob eine `deque` Objekt ist größer als oder gleich einem anderen `deque` Objekt.|  
  
## <a name="interfaces"></a>Schnittstellen  
  
|Interface|Beschreibung|  
|---------------|-----------------|  
|<xref:System.ICloneable>|Duplizieren Sie ein Objekt.|  
|<xref:System.Collections.IEnumerable>|Durch die Elemente der Sequenz.|  
|<xref:System.Collections.ICollection>|Behalten Sie die Gruppe von Elementen.|  
|<xref:System.Collections.Generic.IEnumerable%601>|Durch die Elemente der typisierte Sequenz.|  
|<xref:System.Collections.Generic.ICollection%601>|Behalten Sie die Gruppe von typisierten Elementen.|  
|<xref:System.Collections.Generic.IList%601>|Verwalten Sie geordnete Gruppe von typisierten Elementen.|  
|IDeque < Wert\>|Verwalten von generischen Container.|  
  
## <a name="remarks"></a>Hinweise  
 Das Objekt weist speicherbelegungen und-Freigaben für die Sequenz, über eine gespeicherte Array von Handles, die Blöcke von festlegen `Value` Elemente. Das Array wird bei Bedarf. Wachstum tritt auf, auf eine Weise, dass die Kosten für vorangestellt wird, oder ein neues Element anfügen konstanter Zeit, und keine verbleibenden Elemente gestört werden. Sie können auch ein Element an beiden Enden in konstanter Zeit und ohne beunruhigende verbleibenden Elemente entfernen. Daher eine doppelschlange ist ein guter Kandidat für die zugrunde liegenden Container für die Vorlagenklasse [Warteschlange (STL/CLR)](../dotnet/queue-stl-clr.md) oder Vorlagenklasse [Stapel (STL/CLR)](../dotnet/stack-stl-clr.md).  
  
 Ein `deque` Objekt unterstützt Iteratoren mit zufälligem Zugriff, d. h., Sie verweisen auf ein Element direkt die numerische Position von 0 (null) für das erste (front) Elemente gezählt werden, um [deque:: Size (STL/CLR)](../dotnet/deque-size-stl-clr.md) `() - 1` für das letzte Element für (zurück). Es bedeutet auch, dass eine doppelschlange ein guter Kandidat für die zugrunde liegenden Container für die Vorlagenklasse ist [Priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md).  
  
 Ein Iterator Deque speichert einen Handle für seine zugeordneten Deque-Objekt, zusammen mit den Zeitunterschied des Elements, die er festlegt. Sie können nur mit ihrer zugeordneten Containerobjekte Iteratoren verwenden. Die Verschiebung des ein doppelschlangenelement ist `not` notwendigerweise identisch mit seiner Position. Das erste Element eingefügt wurde Bias 0 (null), das nächste Element des angefügte ist Bias 1, aber das nächste Element vorangestellt wurde Bias-1 zurück.  
  
 Einfügen und Löschen von Elementen an beiden Enden ist `not` ändern Sie den Wert eines Elements auf eine beliebige gültige Bias gespeichert. Einfügen oder Löschen eines inneren Elements `can` ändern Sie den Elementwert, der an eine angegebene Verschiebung gespeichert werden, damit von einem Iterator festgelegten auch ändern kann. (Der Container möglicherweise, kopieren Sie Elemente oben oder nach unten, um eine Lücke vor einer INSERT-Anweisung zu erstellen oder nach einer löschen eine Lücke zu füllen). Ein Iterator Deque bleibt dennoch gültig, solange ihre Bias ein gültiges Element kennzeichnet. Darüber hinaus ein gültiger Iterator bleibt dereferencable – Sie können es verwenden, um Zugriff haben und den Elementwert, die er festlegt – ändern, solange der Zeitunterschied die Verschiebung für den Iterator zurückgegebenes nicht entspricht `end()`.  
  
 Löschen oder Entfernen eines Elements ruft der Destruktor für den gespeicherten Wert. Zerstören von dem Container löscht alle Elemente. Somit wird sichergestellt, dass ein Container, dessen Elementtyp eine Verweisklasse ist, dass keine Elemente den Container Überleben. Beachten Sie jedoch, dass ein Container von Handles ist `not` seine Elemente zu zerstören.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext/doppelschlange >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [Liste (STL/CLR)](../dotnet/list-stl-clr.md)   
 [Priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)   
 [Warteschlange (STL/CLR)](../dotnet/queue-stl-clr.md)   
 [Stack (STL/CLR)](../dotnet/stack-stl-clr.md)   
 [Vektor (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [Referenz zur STL/CLR-Bibliothek](../dotnet/stl-clr-library-reference.md)