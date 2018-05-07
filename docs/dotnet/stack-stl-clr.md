---
title: Stack (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::stack
dev_langs:
- C++
helpviewer_keywords:
- <stack> header [STL/CLR]
- <cliext/stack> header [STL/CLR]
- stack class [STL/CLR]
ms.assetid: 6ee96b9f-8a33-4cf7-b7e0-6535c24bdefb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 290857b51fea6726ec7e4a836d4afe1b33a8e615
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="stack-stlclr"></a>stack (STL/CLR)
Die Vorlagenklasse beschreibt ein Objekt, das eine Elementsequenz variabler Länge steuert, die Last in FIFO-Zugriff hat. Sie verwenden die Containeradapter `stack` als Pushdown Stapel einen zugrunde liegenden Container zu verwalten.  
  
 In der folgenden Beschreibung `GValue` ist identisch mit `Value` , wenn die zweite Datei einen Ref-Typ ist, in diesem Fall wird `Value^`. Auf ähnliche Weise `GContainer` ist identisch mit `Container` , wenn die zweite Datei einen Ref-Typ ist, in diesem Fall wird `Container^`.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<typename Value,  
    typename Container>  
    ref class stack  
        :   public  
        System::ICloneable,  
        Microsoft::VisualC::StlClr::IStack<GValue, GContainer>  
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
|[stack::const_reference (STL/CLR)](../dotnet/stack-const-reference-stl-clr.md)|Der Typ eines konstanten Verweises auf ein Element.|  
|[stack::container_type (STL/CLR)](../dotnet/stack-container-type-stl-clr.md)|Der Typ des zugrunde liegenden Containers.|  
|[stack::difference_type (STL/CLR)](../dotnet/stack-difference-type-stl-clr.md)|Der Typ eines Abstands mit Vorzeichen zwischen zwei Elementen.|  
|[stack::generic_container (STL/CLR)](../dotnet/stack-generic-container-stl-clr.md)|Der Typ der generischen Schnittstelle für den Containeradapter.|  
|[stack::generic_value (STL/CLR)](../dotnet/stack-generic-value-stl-clr.md)|Der Typ eines Elements für die generische Schnittstelle für den Containeradapter.|  
|[stack::reference (STL/CLR)](../dotnet/stack-reference-stl-clr.md)|Der Typ eines Verweises auf ein Element.|  
|[stack::size_type (STL/CLR)](../dotnet/stack-size-type-stl-clr.md)|Der Typ eines Abstands mit Vorzeichen zwischen zwei Elementen.|  
|[stack::value_type (STL/CLR)](../dotnet/stack-value-type-stl-clr.md)|Der Typ eines Elements.|  
  
|Memberfunktion|Beschreibung|  
|---------------------|-----------------|  
|[stack::assign (STL/CLR)](../dotnet/stack-assign-stl-clr.md)|Ersetzt alle Elemente.|  
|[stack::empty (STL/CLR)](../dotnet/stack-empty-stl-clr.md)|Testet, ob keine Elemente vorhanden sind.|  
|[stack::get_container (STL/CLR)](../dotnet/stack-get-container-stl-clr.md)|Greift auf die zugrunde liegenden Containers.|  
|[stack::pop (STL/CLR)](../dotnet/stack-pop-stl-clr.md)|Entfernt das letzte Element.|  
|[stack::push (STL/CLR)](../dotnet/stack-push-stl-clr.md)|Fügt ein neues Letztes Element hinzu.|  
|[stack::size (STL/CLR)](../dotnet/stack-size-stl-clr.md)|Ermittelt die Anzahl von Elementen.|  
|[stack::stack (STL/CLR)](../dotnet/stack-stack-stl-clr.md)|Erstellt ein container-Objekt.|  
|[stack::top (STL/CLR)](../dotnet/stack-top-stl-clr.md)|Greift auf das letzte Element zu.|  
|[stack::to_array (STL/CLR)](../dotnet/stack-to-array-stl-clr.md)|Kopiert die gesteuerte Sequenz in ein neues Array.|  
  
|Eigenschaft|Beschreibung|  
|--------------|-----------------|  
|[stack::top_item (STL/CLR)](../dotnet/stack-top-item-stl-clr.md)|Greift auf das letzte Element zu.|  
  
|Operator|Beschreibung|  
|--------------|-----------------|  
|[stack::operator= (STL/CLR)](../dotnet/stack-operator-assign-stl-clr.md)|Ersetzt die kontrollierte Sequenz.|  
|[operator!= (stack) (STL/CLR)](../dotnet/operator-inequality-stack-stl-clr.md)|Bestimmt, ob eine `stack` Objekt ist nicht gleich einem anderen `stack` Objekt.|  
|[operator< (stack) (STL/CLR)](../dotnet/operator-less-than-stack-stl-clr.md)|Bestimmt, ob eine `stack` Objekt ist kleiner als ein anderes `stack` Objekt.|  
|[operator<= (stack) (STL/CLR)](../dotnet/operator-less-or-equal-stack-stl-clr.md)|Bestimmt, ob eine `stack` Objekt ist kleiner als oder gleich einem anderen `stack` Objekt.|  
|[operator== (stack) (STL/CLR)](../dotnet/operator-equality-stack-stl-clr.md)|Bestimmt, ob eine `stack` -Objekt gleich einem anderen `stack` Objekt.|  
|[operator> (stack) (STL/CLR)](../dotnet/operator-greater-than-stack-stl-clr.md)|Bestimmt, ob eine `stack` -Quellobjekt ist größer als ein anderes `stack` Objekt.|  
|[operator>= (stack) (STL/CLR)](../dotnet/operator-greater-or-equal-stack-stl-clr.md)|Bestimmt, ob eine `stack` Objekt ist größer als oder gleich einem anderen `stack` Objekt.|  
  
## <a name="interfaces"></a>Schnittstellen  
  
|Interface|Beschreibung|  
|---------------|-----------------|  
|<xref:System.ICloneable>|Duplizieren Sie ein Objekt.|  
|IStack\<Container, den Wert >|Behalten Sie die generische Containeradapter.|  
  
## <a name="remarks"></a>Hinweise  
 Das Objekt weist und-Freigaben für die Sequenz, die sie über einen zugrunde liegenden Containers, des Typs steuert `Container`, zur Speicherung der `Value` Elemente und bei Bedarf vergrößert wird. Das Objekt schränkt den Zugriff auf die per Push übertragen und abholen nur das letzte Element, eine Warteschlange Last in First Out (auch bekannt als eine LIFO-Warteschlange oder Stapel) implementieren.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext/Stack >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [Deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [Liste (STL/CLR)](../dotnet/list-stl-clr.md)   
 [Priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)   
 [Warteschlange (STL/CLR)](../dotnet/queue-stl-clr.md)   
 [Vektor (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [Referenz zur STL/CLR-Bibliothek](../dotnet/stl-clr-library-reference.md)