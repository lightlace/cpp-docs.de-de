---
title: Vektor (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::vector
dev_langs: C++
helpviewer_keywords:
- vector class [STL/CLR]
- <cliext/vector> header [STL/CLR]
- <vector> header [STL/CLR]
ms.assetid: f90060d5-097a-4e9d-9a26-a634b5b9c6c2
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: bbbded2cb679d1f55949095cae3508d658e020c5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="vector-stlclr"></a>vector (STL/CLR)
Die Vorlagenklasse beschreibt ein Objekt, das eine Elementsequenz variabler Länge steuert, die zufälligen Zugriff hat. Verwenden Sie den Container `vector` um eine Sequenz von Elementen als einen zusammenhängenden Block von Speicher zu verwalten. Der Block wird als Array implementiert, die bei Bedarf vergrößert wird.  
  
 In der folgenden Beschreibung `GValue` ist identisch mit `Value` , wenn die zweite Datei einen Ref-Typ ist, in diesem Fall wird `Value^`.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<typename Value>  
    ref class vector  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        System::Collections::Generic::IList<GValue>,  
        Microsoft::VisualC::StlClr::IVector<GValue>  
    { ..... };  
```  
  
#### <a name="parameters"></a>Parameter  
 Wert  
 Der Typ eines Elements in der kontrollierten Sequenz.  
  
## <a name="members"></a>Member  
  
|Typdefinition|Beschreibung|  
|---------------------|-----------------|  
|[vector::const_iterator (STL/CLR)](../dotnet/vector-const-iterator-stl-clr.md)|Der Typ eines konstanten Iterators für die gesteuerte Sequenz.|  
|[vector::const_reference (STL/CLR)](../dotnet/vector-const-reference-stl-clr.md)|Der Typ eines konstanten Verweises auf ein Element.|  
|[vector::const_reverse_iterator (STL/CLR)](../dotnet/vector-const-reverse-iterator-stl-clr.md)|Der Typ eines konstanten umgekehrten Iterators für die gesteuerte Sequenz.|  
|[vector::difference_type (STL/CLR)](../dotnet/vector-difference-type-stl-clr.md)|Der Typ eines Abstands mit Vorzeichen zwischen zwei Elementen.|  
|[vector::generic_container (STL/CLR)](../dotnet/vector-generic-container-stl-clr.md)|Der Typ der generischen Schnittstelle für den Container.|  
|[vector::generic_iterator (STL/CLR)](../dotnet/vector-generic-iterator-stl-clr.md)|Der Typ eines Iterators für die generische Schnittstelle für den Container.|  
|[vector::generic_reverse_iterator (STL/CLR)](../dotnet/vector-generic-reverse-iterator-stl-clr.md)|Der Typ eines umgekehrten Iterators für die generische Schnittstelle für den Container.|  
|[vector::generic_value (STL/CLR)](../dotnet/vector-generic-value-stl-clr.md)|Der Typ eines Elements für die generische Schnittstelle für den Container.|  
|[vector::iterator (STL/CLR)](../dotnet/vector-iterator-stl-clr.md)|Der Typ eines Iterators für die gesteuerte Sequenz.|  
|[vector::reference (STL/CLR)](../dotnet/vector-reference-stl-clr.md)|Der Typ eines Verweises auf ein Element.|  
|[vector::reverse_iterator (STL/CLR)](../dotnet/vector-reverse-iterator-stl-clr.md)|Der Typ eines umgekehrten Iterators für die gesteuerte Sequenz.|  
|[vector::size_type (STL/CLR)](../dotnet/vector-size-type-stl-clr.md)|Der Typ eines Abstands mit Vorzeichen zwischen zwei Elementen.|  
|[vector::value_type (STL/CLR)](../dotnet/vector-value-type-stl-clr.md)|Der Typ eines Elements.|  
  
|Memberfunktion|Beschreibung|  
|---------------------|-----------------|  
|[vector::assign (STL/CLR)](../dotnet/vector-assign-stl-clr.md)|Ersetzt alle Elemente.|  
|[vector::at (STL/CLR)](../dotnet/vector-at-stl-clr.md)|Greift auf ein Element an einer angegebenen Position zu.|  
|[vector::back (STL/CLR)](../dotnet/vector-back-stl-clr.md)|Greift auf das letzte Element zu.|  
|[vector::begin (STL/CLR)](../dotnet/vector-begin-stl-clr.md)|Legt den Anfang der kontrollierten Sequenz fest.|  
|[vector::capacity (STL/CLR)](../dotnet/vector-capacity-stl-clr.md)|Gibt die Größe des belegten Speichers für den Container.|  
|[vector::clear (STL/CLR)](../dotnet/vector-clear-stl-clr.md)|Entfernt alle Elemente.|  
|[vector::empty (STL/CLR)](../dotnet/vector-empty-stl-clr.md)|Testet, ob keine Elemente vorhanden sind.|  
|[vector::end (STL/CLR)](../dotnet/vector-end-stl-clr.md)|Legt das Ende der kontrollierten Sequenz fest.|  
|[vector::erase (STL/CLR)](../dotnet/vector-erase-stl-clr.md)|Entfernt Elemente an den angegebenen Positionen.|  
|[vector::front (STL/CLR)](../dotnet/vector-front-stl-clr.md)|Greift auf das erste Element zu.|  
|[vector::insert (STL/CLR)](../dotnet/vector-insert-stl-clr.md)|Fügt Elemente an einer angegebenen Position hinzu.|  
|[vector::pop_back (STL/CLR)](../dotnet/vector-pop-back-stl-clr.md)|Entfernt das letzte Element.|  
|[vector::push_back (STL/CLR)](../dotnet/vector-push-back-stl-clr.md)|Fügt ein neues Letztes Element hinzu.|  
|[vector::rbegin (STL/CLR)](../dotnet/vector-rbegin-stl-clr.md)|Legt den Anfang der umgekehrten kontrollierten Sequenz fest.|  
|[vector::rend (STL/CLR)](../dotnet/vector-rend-stl-clr.md)|Legt das Ende der umgekehrten kontrollierten Sequenz fest.|  
|[vector::reserve (STL/CLR)](../dotnet/vector-reserve-stl-clr.md)|Es wird sichergestellt, dass eine Erweiterung der Mindestkapazität für den Container.|  
|[vector::resize (STL/CLR)](../dotnet/vector-resize-stl-clr.md)|Ändert die Anzahl der Elemente an.|  
|[vector::size (STL/CLR)](../dotnet/vector-size-stl-clr.md)|Ermittelt die Anzahl von Elementen.|  
|[vector::swap (STL/CLR)](../dotnet/vector-swap-stl-clr.md)|Vertauscht den Inhalt von zwei Containern.|  
|[vector::to_array (STL/CLR)](../dotnet/vector-to-array-stl-clr.md)|Kopiert die gesteuerte Sequenz in ein neues Array.|  
|[vector::vector (STL/CLR)](../dotnet/vector-vector-stl-clr.md)|Erstellt ein container-Objekt.|  
  
|Eigenschaft|Beschreibung|  
|--------------|-----------------|  
|[vector::back_item (STL/CLR)](../dotnet/vector-back-item-stl-clr.md)|Greift auf das letzte Element zu.|  
|[vector::front_item (STL/CLR)](../dotnet/vector-front-item-stl-clr.md)|Greift auf das erste Element zu.|  
  
|Operator|Beschreibung|  
|--------------|-----------------|  
|[vector::operator= (STL/CLR)](../dotnet/vector-operator-assign-stl-clr.md)|Ersetzt die kontrollierte Sequenz.|  
|[vector::operator(STL/CLR)](../dotnet/vector-operator-stl-clr.md)|Greift auf ein Element an einer angegebenen Position zu.|  
|[operator!= (vector) (STL/CLR)](../dotnet/operator-inequality-vector-stl-clr.md)|Bestimmt, ob eine `vector` Objekt ist nicht gleich einem anderen `vector` Objekt.|  
|[operator< (vector) (STL/CLR)](../dotnet/operator-less-than-vector-stl-clr.md)|Bestimmt, ob eine `vector` Objekt ist kleiner als ein anderes `vector` Objekt.|  
|[operator<= (vector) (STL/CLR)](../dotnet/operator-less-or-equal-vector-stl-clr.md)|Bestimmt, ob eine `vector` Objekt ist kleiner als oder gleich einem anderen `vector` Objekt.|  
|[operator== (vector) (STL/CLR)](../dotnet/operator-equality-vector-stl-clr.md)|Bestimmt, ob eine `vector` -Objekt gleich einem anderen `vector` Objekt.|  
|[operator> (vector) (STL/CLR)](../dotnet/operator-greater-than-vector-stl-clr.md)|Bestimmt, ob eine `vector` -Quellobjekt ist größer als ein anderes `vector` Objekt.|  
|[operator>= (vector) (STL/CLR)](../dotnet/operator-greater-or-equal-vector-stl-clr.md)|Bestimmt, ob eine `vector` Objekt ist größer als oder gleich einem anderen `vector` Objekt.|  
  
## <a name="interfaces"></a>Schnittstellen  
  
|Interface|Beschreibung|  
|---------------|-----------------|  
|<xref:System.ICloneable>|Duplizieren Sie ein Objekt.|  
|<xref:System.Collections.IEnumerable>|Durch die Elemente der Sequenz.|  
|<xref:System.Collections.ICollection>|Behalten Sie die Gruppe von Elementen.|  
|<xref:System.Collections.Generic.IEnumerable%601>|Durch die Elemente der typisierte Sequenz.|  
|<xref:System.Collections.Generic.ICollection%601>|Behalten Sie die Gruppe von typisierten Elementen.|  
|<xref:System.Collections.Generic.IList%601>|Verwalten Sie geordnete Gruppe von typisierten Elementen.|  
|IVector < Wert\>|Verwalten von generischen Container.|  
  
## <a name="remarks"></a>Hinweise  
 Das Objekt weist und-Freigaben für die Sequenz, die durch eine gespeicherte Array von Steuersoftware `Value` -Elemente, die bei Bedarf vergrößert wird. Wachstum tritt auf, auf eine Weise, dass die Kosten für das Anhängen eines neuen Elements amortisierter konstanter Zeit ist. Das heißt, erhöht die Kosten für das Hinzufügen von Elementen am Ende nicht, im Durchschnitt als die Länge der gesteuerten Sequenz ruft größere. Ein Vektor ist daher ein guter Kandidat für die zugrunde liegenden Container für die Vorlagenklasse [Stapel (STL/CLR)](../dotnet/stack-stl-clr.md).  
  
 Ein `vector` unterstützt random-Access-Iteratoren, d. h., Sie verweisen auf ein Element direkt die numerische Position Zählung von 0 (null) für das erste (Vordergrund)-Element, auf `size() - 1` für das letzte Element der (zurück). Es bedeutet auch, dass Sie ein Vektor ein guter Kandidat für die zugrunde liegenden Container für die Vorlagenklasse ist [Priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md).  
  
 Ein Iterator Vektor speichert einen Handle für seine zugeordneten Vector-Objekt, zusammen mit den Zeitunterschied des Elements, die er festlegt. Sie können nur mit ihrer zugeordneten Containerobjekte Iteratoren verwenden. Die Verschiebung eines Vektorelements ist identisch mit seiner Position.  
  
 Einfügen und Löschen von Elementen kann den Elementwert an einer bestimmten Position gespeichert werden, sodass von einem Iterator festgelegten auch ändern kann, ändern. (Der Container möglicherweise, kopieren Sie Elemente oben oder nach unten, um eine Lücke vor einer INSERT-Anweisung zu erstellen oder nach einer löschen eine Lücke zu füllen). Ein Iterator Vektor bleibt dennoch gültig, solange im Bereich der Bias ist `[0, size()]`. Darüber hinaus ein gültiger Iterator bleibt dereferencable – können sie Zugriff haben und den Elementwert, die er festlegt – ändern, solange die Verschiebung nicht gleich `size()`.  
  
 Löschen oder Entfernen eines Elements ruft der Destruktor für den gespeicherten Wert. Zerstören von dem Container löscht alle Elemente. Somit wird sichergestellt, dass ein Container, dessen Elementtyp eine Verweisklasse ist, dass keine Elemente den Container Überleben. Beachten Sie jedoch, dass ein Container von Handles, die nicht über die Elemente gelöscht.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext/Vektor >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [Deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [Liste (STL/CLR)](../dotnet/list-stl-clr.md)   
 [Priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)   
 [Warteschlange (STL/CLR)](../dotnet/queue-stl-clr.md)   
 [Stack (STL/CLR)](../dotnet/stack-stl-clr.md)   
 [vector::size (STL/CLR)](../dotnet/vector-size-stl-clr.md)  
 [Referenz zur STL/CLR-Bibliothek](../dotnet/stl-clr-library-reference.md)