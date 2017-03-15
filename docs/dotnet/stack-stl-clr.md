---
title: "stack (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::stack"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<cliext/stack>-Header [STL/CLR]"
  - "<stack>-Header [STL/CLR]"
  - "stack-Klasse [STL/CLR]"
ms.assetid: 6ee96b9f-8a33-4cf7-b7e0-6535c24bdefb
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# stack (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Vorlagenklasse beschreibt ein Objekt, das eine VARYINGLängen\-Folgevon Elementen steuert, um die Last In, First Out\-Zugriff hat.  Sie verwenden den Containeradapter `stack`, um einen Container als zugrunde liegenden Push\-\-untenstapel zu verwalten.  
  
 In der unten stehenden Beschreibung, `GValue` ist das `Value` identisch, es sei denn, das zweite ein Referenz\-Typ ist, in diesem Fall `Value^` dar.  Ebenso besteht `GContainer` dem `Container`, es sei denn, das zweite ein Referenz\-Typ ist, in diesem Fall `Container^` dar.  
  
## Syntax  
  
```  
template<typename Value,  
    typename Container>  
    ref class stack  
        :   public  
        System::ICloneable,  
        Microsoft::VisualC::StlClr::IStack<GValue, GContainer>  
    { ..... };  
```  
  
#### Parameter  
 Wert  
 Der Typ eines Elements in der kontrollierten Sequenz.  
  
 Container  
 Der Typ des zugrunde liegenden Containers.  
  
## Member  
  
|Typdefinition|**Beschreibung**|  
|-------------------|----------------------|  
|[stack::const\_reference](../dotnet/stack-const-reference-stl-clr.md)|Der Typ eines konstanten Verweises auf ein Element.|  
|[stack::container\_type](../dotnet/stack-container-type-stl-clr.md)|Der Typ des zugrunde liegenden Containers.|  
|[stack::difference\_type](../dotnet/stack-difference-type-stl-clr.md)|Der Typ eines Abstands mit Vorzeichen zwischen zwei Elementen.|  
|[stack::generic\_container](../dotnet/stack-generic-container-stl-clr.md)|Der Typ der generischen Schnittstelle für den Containeradapter.|  
|[stack::generic\_value](../dotnet/stack-generic-value-stl-clr.md)|Der Typ des Elements für die generische Schnittstelle für den Containeradapter.|  
|[stack::reference](../dotnet/stack-reference-stl-clr.md)|Der Typ eines Verweises auf ein Element.|  
|[stack::size\_type](../dotnet/stack-size-type-stl-clr.md)|Der Typ eines Abstands mit Vorzeichen zwischen zwei Elementen.|  
|[stack::value\_type](../dotnet/stack-value-type-stl-clr.md)|Der Typ eines Elements.|  
  
|Memberfunktion|**Beschreibung**|  
|--------------------|----------------------|  
|[stack::assign](../dotnet/stack-assign-stl-clr.md)|Ersetzt alle Elemente.|  
|[stack::empty](../dotnet/stack-empty-stl-clr.md)|Testet, dass keine Elemente vorhanden sind.|  
|[stack::get\_container](../dotnet/stack-get-container-stl-clr.md)|Greift auf den zugrunde liegenden Container zu.|  
|[stack::pop](../dotnet/stack-pop-stl-clr.md)|Entfernt das letzte Element.|  
|[stack::push](../dotnet/stack-push-stl-clr.md)|Fügt ein neues letzte Element hinzu.|  
|[stack::size](../dotnet/stack-size-stl-clr.md)|Ermittelt die Anzahl der Elemente.|  
|[stack::stack](../dotnet/stack-stack-stl-clr.md)|Erstellt ein container\-Objekt.|  
|[stack::top](../dotnet/stack-top-stl-clr.md)|Greift auf das letzte Element zu.|  
|[stack::to\_array](../dotnet/stack-to-array-stl-clr.md)|Kopiert die gesteuerte Sequenz zu einem neuen Array.|  
  
|Eigenschaft|**Beschreibung**|  
|-----------------|----------------------|  
|[stack::top\_item](../dotnet/stack-top-item-stl-clr.md)|Greift auf das letzte Element zu.|  
  
|Operator|**Beschreibung**|  
|--------------|----------------------|  
|[stack::operator\=](../dotnet/stack-operator-assign-stl-clr.md)|Ersetzt die gesteuerte Sequenz.|  
|[operator\!\= \(stack\)](../dotnet/operator-inequality-stack-stl-clr.md)|Bestimmt, ob ein `stack`\-Objekt nicht gleich ein anderes `stack`\-Objekt ist.|  
|[operator\< \(stack\)](../dotnet/operator-less-than-stack-stl-clr.md)|Bestimmt, ob ein `stack`\-Objekt kleiner als ein anderes `stack`\-Objekt ist.|  
|[operator\<\= \(stack\)](../dotnet/operator-less-or-equal-stack-stl-clr.md)|Bestimmt, ob ein `stack`\-Objekt maximal ein anderes `stack`\-Objekt ist.|  
|[operator\=\= \(stack\)](../dotnet/operator-equality-stack-stl-clr.md)|Bestimmt, ob ein `stack`\-Objekt ein anderes Objekt gleich `stack` ist.|  
|[operator\> \(stack\)](../dotnet/operator-greater-than-stack-stl-clr.md)|Bestimmt, ob ein `stack`\-Objekt größer als ein anderes `stack`\-Objekt ist.|  
|[operator\>\= \(stack\)](../dotnet/operator-greater-or-equal-stack-stl-clr.md)|Bestimmt, ob ein `stack`\-Objekt größer oder gleich einem anderen `stack`\-Objekt ist.|  
  
## Schnittstellen  
  
|Schnittstelle|**Beschreibung**|  
|-------------------|----------------------|  
|<xref:System.ICloneable>|Ein Objekt duplizieren.|  
|IStackValue \<, Container\>|Warten Sie generischen Containeradapter.|  
  
## Hinweise  
 Das Objekt belegt und gibt Arbeitsspeicher für die Sequenz, die durch einen zugrunde liegenden Container steuert, Typ des `Container` verwenden, der `Value`\-Elemente gespeichert und bei Bedarf vergrößert.  Das Objekt wird der Zugriff auf das Drucken und z Bringen nur des letzten Elements ein und implementiert eine Last In, First Out\-Warteschlange \(auch als LIFO\-Warteschlange oder Stapel\).  
  
## Anforderungen  
 **Header:** \<cliext\/Stapel\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [deque](../dotnet/deque-stl-clr.md)   
 [list](../dotnet/list-stl-clr.md)   
 [priority\_queue](../dotnet/priority-queue-stl-clr.md)   
 [queue](../dotnet/queue-stl-clr.md)   
 [Vektor](../dotnet/vector-stl-clr.md)   
 [STL\/CLR\-Bibliothek](../dotnet/stl-clr-library-reference.md)