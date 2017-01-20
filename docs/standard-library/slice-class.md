---
title: "slice-Klasse"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "valarray/std::slice"
  - "std.slice"
  - "slice"
  - "std::slice"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "slice-Klasse"
ms.assetid: 00f0b03d-d657-4b81-ba53-5a9034bb2bf2
caps.latest.revision: 23
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# slice-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Hilfsklasse für valarray, die dazu verwendet wird, eindimensionale Teilmengen eines übergeordneten valarrays zu definieren.  Wenn ein valarray als eine zweidimensionale Matrix mit allen Elementen in einem Array angesehen wird, extrahiert das slice\-Objekt einen Vektor in einer Dimension aus dem zweidimensionalen Array.  
  
## Hinweise  
 Die Klasse speichert die Parameter, die ein Objekt des Typs [slice\_array](../standard-library/slice-array-class.md) charakterisieren. Die Teilmenge eines valarrays wird indirekt erstellt, wenn ein slice\-Objekt als ein Argument für ein Objekt der Klasse [valarray](../Topic/valarray::operator.md)**\<Typ\>** verwendet wird.  Die gespeicherten Werte, die die aus dem übergeordneten valarray ausgewählte Teilmenge angeben, enthalten:  
  
-   Den Anfangsindex im valarray  
  
-   Die Gesamtlänge oder die Anzahl der Elemente im Segment  
  
-   Den Schritt oder den Abstand zwischen aufeinander folgenden Indizes der Elemente im valarray  
  
 Wenn die durch ein slice\-Objekt definierte Menge eine Teilmenge eines konstanten valarrays ist, ist das slice\-Objekt ein neues valarray.  Ist die durch ein slice\-Objekt definierte Menge eine Teilmenge eines nichtkonstanten valarrays, hat das slice\-Objekt Verweissemantik zum ursprünglichen valarray.  Der Auswertungsmechanismus für nichtkonstante valarrays spart Zeit und Speicherplatz.  
  
 Vorgänge für valarrays sind nur garantiert, wenn die durch die slice\-Objekte definierten Quell\- und Zielteilmengen verschieden und alle Indizes gültig sind.  
  
### Konstruktoren  
  
|||  
|-|-|  
|[slice](../Topic/slice::slice.md)|Definiert eine Teilmenge eines `valarray`s, die aus einer Anzahl von Elementen besteht, die jeweils denselben Abstand zueinander haben, und die am angegebenen Element beginnt.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[size](../Topic/slice::size.md)|Ermittelt die Anzahl von Elementen eines slice\-Objekts von einem `valarray`.|  
|[Start](../Topic/slice::start.md)|Ermittelt den Startindex eines slice\-Objekts von einem `valarray`.|  
|[Sprung](../Topic/slice::stride.md)|Ermittelt den Abstand zwischen den Elementen eines slice\-Objekts von einem `valarray`.|  
  
## Anforderungen  
 **Header:** \<valarray\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)