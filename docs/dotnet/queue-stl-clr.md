---
title: "queue (STL/CLR)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "cliext::queue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<cliext/queue>-Header [STL/CLR]"
  - "<queue>-Header [STL/CLR]"
  - "queue-Klasse [STL/CLR]"
ms.assetid: 9ea7dec3-ea98-48ff-87d0-a5afc924aaf2
caps.latest.revision: 18
caps.handback.revision: "18"
ms.author: "mblome"
manager: "ghogen"
---
# queue (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Vorlagenklasse beschreibt ein Objekt, das eine VARYINGLängen\-Folge von Elementen steuert, die First In, First Out\-Zugriff hat.  Sie verwenden den Containeradapter `queue`, um einen Container als zugrunde liegenden Warteschlange zu verwalten.  
  
 In der unten stehenden Beschreibung, `GValue` ist das `Value` identisch, es sei denn, das zweite ein Referenz\-Typ ist, in diesem Fall `Value^` dar.  Ebenso besteht `GContainer` dem `Container`, es sei denn, das zweite ein Referenz\-Typ ist, in diesem Fall `Container^` dar.  
  
## Syntax  
  
```  
template<typename Value,  
    typename Container>  
    ref class queue  
        :   public  
        System::ICloneable,  
        Microsoft::VisualC::StlClr::IQueue<GValue, GContainer>  
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
|[queue::const\_reference](../dotnet/queue-const-reference-stl-clr.md)|Der Typ eines konstanten Verweises auf ein Element.|  
|[queue::container\_type](../dotnet/queue-container-type-stl-clr.md)|Der Typ des zugrunde liegenden Containers.|  
|[queue::difference\_type](../dotnet/queue-difference-type-stl-clr.md)|Der Typ eines Abstands mit Vorzeichen zwischen zwei Elementen.|  
|[queue::generic\_container](../dotnet/queue-generic-container-stl-clr.md)|Der Typ der generischen Schnittstelle für den Containeradapter.|  
|[queue::generic\_value](../dotnet/queue-generic-value-stl-clr.md)|Der Typ des Elements für die generische Schnittstelle für den Containeradapter.|  
|[queue::reference](../dotnet/queue-reference-stl-clr.md)|Der Typ eines Verweises auf ein Element.|  
|[queue::size\_type](../dotnet/queue-size-type-stl-clr.md)|Der Typ eines Abstands mit Vorzeichen zwischen zwei Elementen.|  
|[queue::value\_type](../dotnet/queue-value-type-stl-clr.md)|Der Typ eines Elements.|  
  
|Memberfunktion|**Beschreibung**|  
|--------------------|----------------------|  
|[queue::assign](../dotnet/queue-assign-stl-clr.md)|Ersetzt alle Elemente.|  
|[queue::back](../dotnet/queue-back-stl-clr.md)|Greift auf das letzte Element zu.|  
|[queue::empty](../dotnet/queue-empty-stl-clr.md)|Testet, dass keine Elemente vorhanden sind.|  
|[queue::front](../dotnet/queue-front-stl-clr.md)|Greift auf das erste Element zu.|  
|[queue::get\_container](../dotnet/queue-get-container-stl-clr.md)|Greift auf den zugrunde liegenden Container zu.|  
|[queue::pop](../dotnet/queue-pop-stl-clr.md)|Entfernt das erste Element.|  
|[queue::push](../dotnet/queue-push-stl-clr.md)|Fügt ein neues letzte Element hinzu.|  
|[queue::queue](../dotnet/queue-queue-stl-clr.md)|Erstellt ein container\-Objekt.|  
|[queue::size](../dotnet/queue-size-stl-clr.md)|Ermittelt die Anzahl der Elemente.|  
|[queue::to\_array](../dotnet/queue-to-array-stl-clr.md)|Kopiert die gesteuerte Sequenz zu einem neuen Array.|  
  
|Eigenschaft|**Beschreibung**|  
|-----------------|----------------------|  
|[queue::back\_item](../dotnet/queue-back-item-stl-clr.md)|Greift auf das letzte Element zu.|  
|[queue::front\_item](../dotnet/queue-front-item-stl-clr.md)|Greift auf das erste Element zu.|  
  
|Operator|**Beschreibung**|  
|--------------|----------------------|  
|[queue::operator\=](../dotnet/queue-operator-assign-stl-clr.md)|Ersetzt die gesteuerte Sequenz.|  
|[operator\!\= \(queue\)](../dotnet/operator-inequality-queue-stl-clr.md)|Bestimmt, ob ein `queue`\-Objekt nicht gleich ein anderes `queue`\-Objekt ist.|  
|[operator\< \(queue\)](../dotnet/operator-less-than-queue-stl-clr.md)|Bestimmt, ob ein `queue`\-Objekt kleiner als ein anderes `queue`\-Objekt ist.|  
|[operator\<\= \(queue\)](../dotnet/operator-less-or-equal-queue-stl-clr.md)|Bestimmt, ob ein `queue`\-Objekt maximal ein anderes `queue`\-Objekt ist.|  
|[operator\=\= \(queue\)](../dotnet/operator-equality-queue-stl-clr.md)|Bestimmt, ob ein `queue`\-Objekt ein anderes Objekt gleich `queue` ist.|  
|[operator\> \(queue\)](../dotnet/operator-greater-than-queue-stl-clr.md)|Bestimmt, ob ein `queue`\-Objekt größer als ein anderes `queue`\-Objekt ist.|  
|[operator\>\= \(queue\)](../dotnet/operator-greater-or-equal-queue-stl-clr.md)|Bestimmt, ob ein `queue`\-Objekt größer oder gleich einem anderen `queue`\-Objekt ist.|  
  
## Schnittstellen  
  
|Schnittstelle|**Beschreibung**|  
|-------------------|----------------------|  
|<xref:System.ICloneable>|Ein Objekt duplizieren.|  
|IQueueValue \<, Container\>|Warten Sie generischen Containeradapter.|  
  
## Hinweise  
 Das Objekt belegt und gibt Arbeitsspeicher für die Sequenz, die durch einen zugrunde liegenden Container steuert, Typ des `Container` verwenden, der `Value`\-Elemente gespeichert und bei Bedarf vergrößert.  Das Objekt wird auf das erste Element einfach zu drücken und das letzte Element einzufügen ein und implementiert eine First In, First Out\-Warteschlange \(auch als FIFO\-Warteschlange oder einfach eine Warteschlange\).  
  
## Anforderungen  
 **Header:** \<cliext\/Warteschlange\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [deque](../dotnet/deque-stl-clr.md)   
 [list](../dotnet/list-stl-clr.md)   
 [priority\_queue](../dotnet/priority-queue-stl-clr.md)   
 [Stapel](../dotnet/stack-stl-clr.md)   
 [Vektor](../dotnet/vector-stl-clr.md)   
 [STL\/CLR\-Bibliothek](../dotnet/stl-clr-library-reference.md)