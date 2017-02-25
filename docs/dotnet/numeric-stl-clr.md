---
title: "numeric (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "<cliext/numeric>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<cliext/numeric>-Header [STL/CLR]"
  - "<numeric>-Header [STL/CLR]"
  - "Numerische Funktionen [STL/CLR]"
ms.assetid: 1dc4d9a3-e734-459c-9678-5d9be0ef4c79
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# numeric (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Definiert Containervorlagenfunktionen, die die Algorithmen ausführen, die für das numerische Verarbeitung bereitgestellt werden.  
  
## Syntax  
  
```  
#include <cliext/numeric>  
```  
  
## Funktionen  
  
|Funktion|**Beschreibung**|  
|--------------|----------------------|  
|[accumulate](../dotnet/accumulate-stl-clr.md)|Berechnet die Summe aller Elemente in einem angegebenen Gültigkeitsbereich einschließlich einige Anfangswert, indem das Ableiten von aufeinander folgenden partiellen Summen oder berechnet das Ergebnis aufeinander folgender partiellen Ergebnisse, die ähnlich mit einer angegebenen binäre Operation als die Summe erreicht werden.|  
|[adjacent\_difference](../dotnet/adjacent-difference-stl-clr.md)|Berechnet die aufeinander folgenden Unterschiede zwischen einem Element und seinem Vorgänger in einem Eingabebereich und gibt die Ergebnisse einem Zielbereich aus oder berechnet das Ergebnis einer allgemeinen Prozedur, in der der Unterschiedvorgang ersetzt wird von anderen, angegebenen binäre Operation.|  
|[inner\_product](../dotnet/inner-product-stl-clr.md)|Berechnet die Summe des elementweisen Produkts von zwei Bereichen und fügt sie einem angegebenen Anfangswert hinzu oder berechnet das Ergebnis einer allgemeinen Prozedur, in der die Summen\- und Produktbinären Standardoperationen durch weitere angegebene binäre Operationen ersetzt werden.|  
|[partial\_sum](../dotnet/partial-sum-stl-clr.md)|Berechnet Reihe Summen in einem Eingabebereich beim ersten Element von `i` das Element und speichert das Ergebnis jeder solchen Summe in `i` des Elements eines Zielbereichs oder berechnet das Ergebnis einer allgemeinen Prozedur, in der der Summenvorgang durch eine weitere angegebene binäre Operation ersetzt wird.|  
  
## Anforderungen  
 **Header:** \<cliext\/numerisches\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [STL\/CLR\-Bibliothek](../dotnet/stl-clr-library-reference.md)