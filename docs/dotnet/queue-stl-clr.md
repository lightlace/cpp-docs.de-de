---
title: Warteschlange (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::queue
dev_langs:
- C++
helpviewer_keywords:
- <queue> header [STL/CLR]
- queue class [STL/CLR]
- <cliext/queue> header [STL/CLR]
ms.assetid: 9ea7dec3-ea98-48ff-87d0-a5afc924aaf2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 7e65d5a364f5886df2bad976e3c34dc57266b70f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="queue-stlclr"></a>queue (STL/CLR)
Die Vorlagenklasse beschreibt ein Objekt, das eine Elementsequenz variabler Länge steuert, die FIFO-Reihenfolge Zugriff hat. Sie verwenden die Containeradapter `queue` einen zugrunde liegenden Container wie eine Warteschlange zu verwalten.  
  
 In der folgenden Beschreibung `GValue` ist identisch mit `Value` , wenn die zweite Datei einen Ref-Typ ist, in diesem Fall wird `Value^`. Auf ähnliche Weise `GContainer` ist identisch mit `Container` , wenn die zweite Datei einen Ref-Typ ist, in diesem Fall wird `Container^`.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<typename Value,  
    typename Container>  
    ref class queue  
        :   public  
        System::ICloneable,  
        Microsoft::VisualC::StlClr::IQueue<GValue, GContainer>  
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
|[queue::const_reference (STL/CLR)](../dotnet/queue-const-reference-stl-clr.md)|Der Typ eines konstanten Verweises auf ein Element.|  
|[queue::container_type (STL/CLR)](../dotnet/queue-container-type-stl-clr.md)|Der Typ des zugrunde liegenden Containers.|  
|[queue::difference_type (STL/CLR)](../dotnet/queue-difference-type-stl-clr.md)|Der Typ eines Abstands mit Vorzeichen zwischen zwei Elementen.|  
|[queue::generic_container (STL/CLR)](../dotnet/queue-generic-container-stl-clr.md)|Der Typ der generischen Schnittstelle für den Containeradapter.|  
|[queue::generic_value (STL/CLR)](../dotnet/queue-generic-value-stl-clr.md)|Der Typ eines Elements für die generische Schnittstelle für den Containeradapter.|  
|[queue::reference (STL/CLR)](../dotnet/queue-reference-stl-clr.md)|Der Typ eines Verweises auf ein Element.|  
|[queue::size_type (STL/CLR)](../dotnet/queue-size-type-stl-clr.md)|Der Typ eines Abstands mit Vorzeichen zwischen zwei Elementen.|  
|[queue::value_type (STL/CLR)](../dotnet/queue-value-type-stl-clr.md)|Der Typ eines Elements.|  
  
|Memberfunktion|Beschreibung|  
|---------------------|-----------------|  
|[queue::assign (STL/CLR)](../dotnet/queue-assign-stl-clr.md)|Ersetzt alle Elemente.|  
|[queue::back (STL/CLR)](../dotnet/queue-back-stl-clr.md)|Greift auf das letzte Element zu.|  
|[queue::empty (STL/CLR)](../dotnet/queue-empty-stl-clr.md)|Testet, ob keine Elemente vorhanden sind.|  
|[queue::front (STL/CLR)](../dotnet/queue-front-stl-clr.md)|Greift auf das erste Element zu.|  
|[queue::get_container (STL/CLR)](../dotnet/queue-get-container-stl-clr.md)|Greift auf die zugrunde liegenden Containers.|  
|[queue::pop (STL/CLR)](../dotnet/queue-pop-stl-clr.md)|Entfernt das erste Element.|  
|[queue::push (STL/CLR)](../dotnet/queue-push-stl-clr.md)|Fügt ein neues Letztes Element hinzu.|  
|[queue::queue (STL/CLR)](../dotnet/queue-queue-stl-clr.md)|Erstellt ein container-Objekt.|  
|[queue::size (STL/CLR)](../dotnet/queue-size-stl-clr.md)|Ermittelt die Anzahl von Elementen.|  
|[queue::to_array (STL/CLR)](../dotnet/queue-to-array-stl-clr.md)|Kopiert die gesteuerte Sequenz in ein neues Array.|  
  
|Eigenschaft|Beschreibung|  
|--------------|-----------------|  
|[queue::back_item (STL/CLR)](../dotnet/queue-back-item-stl-clr.md)|Greift auf das letzte Element zu.|  
|[queue::front_item (STL/CLR)](../dotnet/queue-front-item-stl-clr.md)|Greift auf das erste Element zu.|  
  
|Operator|Beschreibung|  
|--------------|-----------------|  
|[queue::operator= (STL/CLR)](../dotnet/queue-operator-assign-stl-clr.md)|Ersetzt die kontrollierte Sequenz.|  
|[operator!= (queue) (STL/CLR)](../dotnet/operator-inequality-queue-stl-clr.md)|Bestimmt, ob eine `queue` Objekt ist nicht gleich einem anderen `queue` Objekt.|  
|[operator< (queue) (STL/CLR)](../dotnet/operator-less-than-queue-stl-clr.md)|Bestimmt, ob eine `queue` Objekt ist kleiner als ein anderes `queue` Objekt.|  
|[operator<= (queue) (STL/CLR)](../dotnet/operator-less-or-equal-queue-stl-clr.md)|Bestimmt, ob eine `queue` Objekt ist kleiner als oder gleich einem anderen `queue` Objekt.|  
|[operator== (queue) (STL/CLR)](../dotnet/operator-equality-queue-stl-clr.md)|Bestimmt, ob eine `queue` -Objekt gleich einem anderen `queue` Objekt.|  
|[operator> (queue) (STL/CLR)](../dotnet/operator-greater-than-queue-stl-clr.md)|Bestimmt, ob eine `queue` -Quellobjekt ist größer als ein anderes `queue` Objekt.|  
|[operator>= (queue) (STL/CLR)](../dotnet/operator-greater-or-equal-queue-stl-clr.md)|Bestimmt, ob eine `queue` Objekt ist größer als oder gleich einem anderen `queue` Objekt.|  
  
## <a name="interfaces"></a>Schnittstellen  
  
|Interface|Beschreibung|  
|---------------|-----------------|  
|<xref:System.ICloneable>|Duplizieren Sie ein Objekt.|  
|IQueue\<Container, den Wert >|Behalten Sie die generische Containeradapter.|  
  
## <a name="remarks"></a>Hinweise  
 Das Objekt weist und-Freigaben für die Sequenz, die sie über einen zugrunde liegenden Containers, des Typs steuert `Container`, zur Speicherung der `Value` Elemente und bei Bedarf vergrößert wird. Das Objekt schränkt den Zugriff mit dem Betätigen nur des ersten Elements, und entfernt das letzte Element, eine Warteschlange implementieren eine FIFO-Reihenfolge (auch bekannt als eine FIFO-Warteschlange oder einfach eine Warteschlange).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext bzw. einer neuen Warteschlange >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [Deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [Liste (STL/CLR)](../dotnet/list-stl-clr.md)   
 [Priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)   
 [Stack (STL/CLR)](../dotnet/stack-stl-clr.md)   
 [Vektor (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [Referenz zur STL/CLR-Bibliothek](../dotnet/stl-clr-library-reference.md)