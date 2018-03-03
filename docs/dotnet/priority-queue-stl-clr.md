---
title: Priority_queue (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::priority_queue
dev_langs:
- C++
helpviewer_keywords:
- priority_queue class [STL/CLR]
- <queue> header [STL/CLR]
- <cliext/queue> header [STL/CLR]
ms.assetid: 4d0000d3-68ff-4c4b-8157-7060540136f5
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: b7d1459da07f7e392a2da1fbf5d6e9d72c8f4653
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="priorityqueue-stlclr"></a>priority_queue (STL/CLR)
Die Vorlagenklasse beschreibt ein Objekt, das eine Elementsequenz variabler Länge sortierte Sequenz von Elementen, die mit Zugriff eingeschränkter gesteuert. Sie verwenden die Containeradapter `priority_queue` einen zugrunde liegenden Container als eine Prioritätswarteschlange zu verwalten.  
  
 In der folgenden Beschreibung `GValue` ist identisch mit `Value` , wenn die zweite Datei einen Ref-Typ ist, in diesem Fall wird `Value^`. Auf ähnliche Weise `GContainer` ist identisch mit `Container` , wenn die zweite Datei einen Ref-Typ ist, in diesem Fall wird `Container^`.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<typename Value,  
    typename Container>  
    ref class priority_queue  
        System::ICloneable,  
        Microsoft::VisualC::StlClr::IPriorityQueue<GValue, GContainer>  
    { ..... };  
```  
  
#### <a name="parameters"></a>Parameter  
 Wert  
 Der Typ eines Elements in der kontrollierten Sequenz.  
  
 Container  
 Der Typ des zugrunde liegenden Containers.  
  
## <a name="members"></a>Member  
  
|Typdefinition|Beschreibung|  
|---------------------|-----------------|  
|[priority_queue::const_reference (STL/CLR)](../dotnet/priority-queue-const-reference-stl-clr.md)|Der Typ eines konstanten Verweises auf ein Element.|  
|[priority_queue::container_type (STL/CLR)](../dotnet/priority-queue-container-type-stl-clr.md)|Der Typ des zugrunde liegenden Containers.|  
|[priority_queue::difference_type (STL/CLR)](../dotnet/priority-queue-difference-type-stl-clr.md)|Der Typ eines Abstands mit Vorzeichen zwischen zwei Elementen.|  
|[priority_queue::generic_container (STL/CLR)](../dotnet/priority-queue-generic-container-stl-clr.md)|Der Typ der generischen Schnittstelle für den Containeradapter.|  
|[priority_queue::generic_value (STL/CLR)](../dotnet/priority-queue-generic-value-stl-clr.md)|Der Typ eines Elements für die generische Schnittstelle für den Containeradapter.|  
|[priority_queue::reference (STL/CLR)](../dotnet/priority-queue-reference-stl-clr.md)|Der Typ eines Verweises auf ein Element.|  
|[priority_queue::size_type (STL/CLR)](../dotnet/priority-queue-size-type-stl-clr.md)|Der Typ eines Abstands mit Vorzeichen zwischen zwei Elementen.|  
|[priority_queue::value_compare (STL/CLR)](../dotnet/priority-queue-value-compare-stl-clr.md)|Der Delegat für zwei Elemente.|  
|[priority_queue::value_type (STL/CLR)](../dotnet/priority-queue-value-type-stl-clr.md)|Der Typ eines Elements.|  
  
|Memberfunktion|Beschreibung|  
|---------------------|-----------------|  
|[priority_queue::assign (STL/CLR)](../dotnet/priority-queue-assign-stl-clr.md)|Ersetzt alle Elemente.|  
|[priority_queue::empty (STL/CLR)](../dotnet/priority-queue-empty-stl-clr.md)|Testet, ob keine Elemente vorhanden sind.|  
|[priority_queue::get_container (STL/CLR)](../dotnet/priority-queue-get-container-stl-clr.md)|Greift auf die zugrunde liegenden Containers.|  
|[priority_queue::pop (STL/CLR)](../dotnet/priority-queue-pop-stl-clr.md)|Entfernt das Element Hghest Priorität.|  
|[priority_queue::priority_queue (STL/CLR)](../dotnet/priority-queue-priority-queue-stl-clr.md)|Erstellt ein container-Objekt.|  
|[priority_queue::push (STL/CLR)](../dotnet/priority-queue-push-stl-clr.md)|Fügt ein neues Element hinzu.|  
|[priority_queue::size (STL/CLR)](../dotnet/priority-queue-size-stl-clr.md)|Ermittelt die Anzahl von Elementen.|  
|[priority_queue::top (STL/CLR)](../dotnet/priority-queue-top-stl-clr.md)|Greift auf das Element der höchsten Priorität.|  
|[priority_queue::to_array (STL/CLR)](../dotnet/priority-queue-to-array-stl-clr.md)|Kopiert die gesteuerte Sequenz in ein neues Array.|  
|[priority_queue::value_comp (STL/CLR)](../dotnet/priority-queue-value-comp-stl-clr.md)|Kopiert der Delegat für zwei Elemente.|  
  
|Eigenschaft|Beschreibung|  
|--------------|-----------------|  
|[priority_queue::top_item (STL/CLR)](../dotnet/priority-queue-top-item-stl-clr.md)|Greift auf das Element der höchsten Priorität.|  
  
|Operator|Beschreibung|  
|--------------|-----------------|  
|[priority_queue::operator= (STL/CLR)](../dotnet/priority-queue-operator-assign-stl-clr.md)|Ersetzt die kontrollierte Sequenz.|  
  
## <a name="interfaces"></a>Schnittstellen  
  
|Interface|Beschreibung|  
|---------------|-----------------|  
|<xref:System.ICloneable>|Duplizieren Sie ein Objekt.|  
|IPriorityQueue\<Container, den Wert >|Behalten Sie die generische Containeradapter.|  
  
## <a name="remarks"></a>Hinweise  
 Das Objekt weist und-Freigaben für die Sequenz, die sie über einen zugrunde liegenden Containers, des Typs steuert `Container`, zur Speicherung der `Value` Elemente und bei Bedarf vergrößert wird. Darin sind die als Heap mit der höchsten Priorität-Element (dem obersten Element) leicht zugänglich und Wechseldatenträger sortierte Sequenz. Das Objekt schränkt den Zugriff auf die Push neue Elemente und abholen nur die höchste Priorität Element, eine Prioritätswarteschlange implementieren.  
  
 Das Objekt sortiert die Sequenz, die sie durch Aufrufen einer gespeicherten Delegatobjekt des Typs steuert [priority_queue::value_compare (STL/CLR)](../dotnet/priority-queue-value-compare-stl-clr.md). Sie können das gespeicherte Delegatobjekt angeben, beim Erstellen von Priority_queue. Wenn Sie keine Delegatobjekt angeben, wird der Standardwert ist der Vergleich `operator<(value_type, value_type)`. Sie Zugriff auf diesem gespeicherten Objekt durch Aufrufen der Memberfunktion [priority_queue:: value_comp (STL/CLR)](../dotnet/priority-queue-value-comp-stl-clr.md)`()`.  
  
 Solche ein Delegatobjekt muss eine strikte schwache Sortierung anwenden für Werte des Typs [priority_queue:: value_type (STL/CLR)](../dotnet/priority-queue-value-type-stl-clr.md). Bedeutet, dass für zwei beliebige Tasten `X` und `Y`:  
  
 `value_comp()(X, Y)`Gibt der gleiche booleschen führen bei jedem Aufruf.  
  
 Wenn `value_comp()(X, Y)` ist "true", klicken Sie dann `value_comp()(Y, X)` muss "false" sein.  
  
 Wenn `value_comp()(X, Y)` ist "true", klicken Sie dann `X` herrscht die verbreitete vor bestellt werden `Y`.  
  
 Wenn `!value_comp()(X, Y) && !value_comp()(Y, X)` ist "true", klicken Sie dann `X` und `Y` gelten als die entsprechende Reihenfolge aufweisen.  
  
 Für ein bestimmtes Element `X` vorausgeht, die `Y` in der gesteuerten Sequenz `key_comp()(Y, X)` lautet "false". (Für das Standardobjekt Delegaten verringern Schlüssel nie im Wert.)  
  
 Das Element der höchsten Priorität ist daher eines der Elemente, die vor jedem anderen Element nicht sortiert ist.  
  
 Da der zugrunde liegenden Containers Elemente sortiert als einen Heap verfolgt:  
  
 Der Container muss Iteratoren mit zufälligem Zugriff unterstützen.  
  
 Elemente mit der entsprechenden Reihenfolge können in einer anderen Reihenfolge ausgelesen werden, als sie vorgenommen wurden. (Die Reihenfolge nicht stabil ist.)  
  
 Folglich Kandidaten für den zugrunde liegenden Container enthalten [Deque (STL/CLR)](../dotnet/deque-stl-clr.md) und [Vektor (STL/CLR)](../dotnet/vector-stl-clr.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext bzw. einer neuen Warteschlange >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [Deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [Warteschlange (STL/CLR)](../dotnet/queue-stl-clr.md)   
 [Stack (STL/CLR)](../dotnet/stack-stl-clr.md)   
 [Vektor (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [Referenz zur STL/CLR-Bibliothek](../dotnet/stl-clr-library-reference.md)