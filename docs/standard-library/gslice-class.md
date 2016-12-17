---
title: "gslice-Klasse"
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
  - "std::gslice"
  - "std.gslice"
  - "gslice"
  - "valarray/std::gslice"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "gslice-Klasse"
ms.assetid: f47cffd0-ea59-4b13-848b-7a5ce1d7e2a3
caps.latest.revision: 21
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# gslice-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Hilfsprogrammklasse zu valarray, die zum Definieren von mehrdimensionaler Teilmengen von einem valarray verwendet wird.  Wenn ein valarray als mehrdimensionale Matrix mit allen Elementen in einem Array angesehen wird, extrahiert das Segment einen Vektor aus dem mehrdimensionalen Array.  
  
## Hinweise  
 Die Klasse speichert die Parameter, die ein Objekt des Typs [gslice\_array](../standard-library/gslice-array-class.md) charakterisieren.  Die Teilmenge von einem valarray wird indirekt erstellt, wenn ein Objekt der gslice\-Klasse als ein Argument für ein Objekt der Klasse [valarray](../Topic/valarray::operator.md)**\<Typ\>** erscheint .  Die gespeicherten Werte, die die aus dem übergeordneten valarray ausgewählte Teilmenge angeben, enthalten:  
  
-   Einen Startindex.  
  
-   Ein Längenvektor der Klasse **valarray\<size\_t\>**.  
  
-   Ein Sprungvektor der Klasse **valarray\<size\_t\>**.  
  
 Die beiden Vektoren müssen dieselbe Länge haben.  
  
 Wenn der von einem gslice festgelegte Teil eine Teilmenge eines konstanten valarray ist, ist das gslice ein neues valarray.  Ist die durch ein Gslice definierte Menge die Teilmenge von einem nichtkonstanten valarray, hat das gslice Verweissemantik zum ursprünglichen valarray.  Der Auswertungsmechanismus für nichtkonstante valarrays spart Zeit und Speicherplatz.  
  
 Vorgänge für valarrays sind nur garantiert, wenn die durch die gslices definierten Quell\- und Zielteilmengen verschieden und alle Indizes gültig sind.  
  
### Konstruktoren  
  
|||  
|-|-|  
|[gslice](../Topic/gslice::gslice.md)|Definiert eine Teilmenge von `valarray`, die aus mehreren Segmenten von `valarray` besteht, die alle bei einem angegebenen Element beginnen.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[size](../Topic/gslice::size.md)|Sucht die Arraywerte durch Angabe der Anzahl von Elementen in einem allgemeinen Segment von `valarray`.|  
|[Start](../Topic/gslice::start.md)|Sucht den Startindex eines allgemeinen Segments von `valarray`.|  
|[Sprung](../Topic/gslice::stride.md)|Sucht den Abstand zwischen Elementen in einem allgemeinen Segment von `valarray`.|  
  
## Anforderungen  
 **Header:** \<valarray\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)