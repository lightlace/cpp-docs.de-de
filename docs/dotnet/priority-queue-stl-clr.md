---
title: "priority_queue (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::priority_queue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<cliext/queue>-Header [STL/CLR]"
  - "<queue>-Header [STL/CLR]"
  - "priority_queue-Klasse [STL/CLR]"
ms.assetid: 4d0000d3-68ff-4c4b-8157-7060540136f5
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# priority_queue (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Vorlagenklasse beschreibt ein Objekt, das eine VARYINGLänge bestellte Sequenz von Elementen gesteuert wird, die beschränkten Zugriff hat.  Sie verwenden den Containeradapter `priority_queue`, um einen Container als zugrunde liegenden Prioritätswarteschlange zu verwalten.  
  
 In der unten stehenden Beschreibung, `GValue` ist das `Value` identisch, es sei denn, das zweite ein Referenz\-Typ ist, in diesem Fall `Value^` dar.  Ebenso besteht `GContainer` dem `Container`, es sei denn, das zweite ein Referenz\-Typ ist, in diesem Fall `Container^` dar.  
  
## Syntax  
  
```  
template<typename Value,  
    typename Container>  
    ref class priority_queue  
        System::ICloneable,  
        Microsoft::VisualC::StlClr::IPriorityQueue<GValue, GContainer>  
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
|[priority\_queue::const\_reference](../dotnet/priority-queue-const-reference-stl-clr.md)|Der Typ eines konstanten Verweises auf ein Element.|  
|[priority\_queue::container\_type](../dotnet/priority-queue-container-type-stl-clr.md)|Der Typ des zugrunde liegenden Containers.|  
|[priority\_queue::difference\_type](../dotnet/priority-queue-difference-type-stl-clr.md)|Der Typ eines Abstands mit Vorzeichen zwischen zwei Elementen.|  
|[priority\_queue::generic\_container](../dotnet/priority-queue-generic-container-stl-clr.md)|Der Typ der generischen Schnittstelle für den Containeradapter.|  
|[priority\_queue::generic\_value](../dotnet/priority-queue-generic-value-stl-clr.md)|Der Typ des Elements für die generische Schnittstelle für den Containeradapter.|  
|[priority\_queue::reference](../dotnet/priority-queue-reference-stl-clr.md)|Der Typ eines Verweises auf ein Element.|  
|[priority\_queue::size\_type](../dotnet/priority-queue-size-type-stl-clr.md)|Der Typ eines Abstands mit Vorzeichen zwischen zwei Elementen.|  
|[priority\_queue::value\_compare](../dotnet/priority-queue-value-compare-stl-clr.md)|Der Reihenfolgendelegat für zwei Elemente.|  
|[priority\_queue::value\_type](../dotnet/priority-queue-value-type-stl-clr.md)|Der Typ eines Elements.|  
  
|Memberfunktion|**Beschreibung**|  
|--------------------|----------------------|  
|[priority\_queue::assign](../dotnet/priority-queue-assign-stl-clr.md)|Ersetzt alle Elemente.|  
|[priority\_queue::empty](../dotnet/priority-queue-empty-stl-clr.md)|Testet, dass keine Elemente vorhanden sind.|  
|[priority\_queue::get\_container](../dotnet/priority-queue-get-container-stl-clr.md)|Greift auf den zugrunde liegenden Container zu.|  
|[priority\_queue::pop](../dotnet/priority-queue-pop-stl-clr.md)|Entfernt das HghestPrioritätselement.|  
|[priority\_queue::priority\_queue](../dotnet/priority-queue-priority-queue-stl-clr.md)|Erstellt ein container\-Objekt.|  
|[priority\_queue::push](../dotnet/priority-queue-push-stl-clr.md)|Fügt ein neues Element hinzu.|  
|[priority\_queue::size](../dotnet/priority-queue-size-stl-clr.md)|Ermittelt die Anzahl der Elemente.|  
|[priority\_queue::top](../dotnet/priority-queue-top-stl-clr.md)|Greift auf das höchste Element zu.|  
|[priority\_queue::to\_array](../dotnet/priority-queue-to-array-stl-clr.md)|Kopiert die gesteuerte Sequenz zu einem neuen Array.|  
|[priority\_queue::value\_comp](../dotnet/priority-queue-value-comp-stl-clr.md)|Kopiert den Delegaten für die Sortierung für zwei Elemente.|  
  
|Eigenschaft|**Beschreibung**|  
|-----------------|----------------------|  
|[priority\_queue::top\_item](../dotnet/priority-queue-top-item-stl-clr.md)|Greift auf das höchste Element zu.|  
  
|Operator|**Beschreibung**|  
|--------------|----------------------|  
|[priority\_queue::operator\=](../dotnet/priority-queue-operator-assign-stl-clr.md)|Ersetzt die gesteuerte Sequenz.|  
  
## Schnittstellen  
  
|Schnittstelle|**Beschreibung**|  
|-------------------|----------------------|  
|<xref:System.ICloneable>|Ein Objekt duplizieren.|  
|IPriorityQueueValue \<, Container\>|Warten Sie generischen Containeradapter.|  
  
## Hinweise  
 Das Objekt belegt und gibt Arbeitsspeicher für die Sequenz, die durch einen zugrunde liegenden Container steuert, Typ des `Container` verwenden, der `Value`\-Elemente gespeichert und bei Bedarf vergrößert.  Sie enthält die Sequenz angeordnet als Heap, mit dem höchsten Element \(das oberste Element\) bereit zugegriffen werden entfernbar.  Das Objekt wird der Zugriff auf das Drucken von neuen Elementen und zum Setzen nur des höchsten Elements ein und implementiert eine Prioritätswarteschlange.  
  
 Das Objekt ordnet die Sequenz, die steuert, indem ein gespeichertes Delegatobjekt des Typs [priority\_queue::value\_compare](../dotnet/priority-queue-value-compare-stl-clr.md).  Sie können dem gespeicherten Delegatobjekt angeben, wenn Sie das priority\_queue erstellen; Wenn Sie kein Delegatobjekt angeben, gilt standardmäßig der Vergleich `operator<(value_type, value_type)`.  Sie greifen auf das gespeicherte Objekt zu, indem Sie die Memberfunktion [priority\_queue::value\_comp](../dotnet/priority-queue-value-comp-stl-clr.md)`()` aufrufen.  
  
 Ein solches Delegatobjekt muss eine genaue schwache Sortierung Werte des Typs [priority\_queue::value\_type](../dotnet/priority-queue-value-type-stl-clr.md) festlegen.  Das heißt, für alle zwei Schlüssel `X` und `Y`:  
  
 `value_comp()(X, Y)` gibt die gleichen Auswirkungen auf booleschen jeden Aufruf zurück.  
  
 Wenn `value_comp()(X, Y)` true ist, muss `value_comp()(Y, X)` falsch sein.  
  
 Wenn `value_comp()(X, Y)` true ist, dann wird `X` vor `Y` nach.  
  
 Wenn `!value_comp()(X, Y) && !value_comp()(Y, X)` true ist, werden `X` und `Y` gibt an, um übereinstimmende Reihenfolge zu haben.  
  
 Für jedes Element `X`, das `Y` in der Sequenz gesteuerten vorangeht, ist `key_comp()(Y, X)` falsch. \(Für das Standarddelegatobjekt, verringert wird Schlüssel nie.\)  
  
 Das höchste Element entspricht insofern eines der Elemente, das nicht vor jeglichem anderen Element angeordnet wird.  
  
 Da der zugrunde liegende Container Elemente angeordnet als Heap enthält:  
  
 Der Container Iteratoren muss mit wahlfreier Zugriff unterstützen.  
  
 Elemente mit entsprechender Reihenfolge werden in einer anderen Reihenfolge geholt werden, als sie gedrückt wurden. \(Die Reihenfolge ist nicht stabil\).  
  
 So schließen Kandidaten für den zugrunde liegenden Container [deque](../dotnet/deque-stl-clr.md) und [Vektor](../dotnet/vector-stl-clr.md).  
  
## Anforderungen  
 **Header:** \<cliext\/Warteschlange\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [deque](../dotnet/deque-stl-clr.md)   
 [queue](../dotnet/queue-stl-clr.md)   
 [Stapel](../dotnet/stack-stl-clr.md)   
 [Vektor](../dotnet/vector-stl-clr.md)   
 [STL\/CLR\-Bibliothek](../dotnet/stl-clr-library-reference.md)