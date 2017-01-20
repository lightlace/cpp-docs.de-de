---
title: "&lt; numerisch &gt;"
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
  - "std::<numeric>"
  - "std.<numeric>"
  - "<numeric>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Header < numerisch >"
ms.assetid: 6d6ccb94-48cc-479b-b4a9-bd9c78d4896a
caps.latest.revision: 23
caps.handback.revision: "23"
ms.author: "corob"
manager: "ghogen"
---
# &lt; numerisch &gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Definiert Containervorlagenfunktionen, die Algorithmen für die numerische Verarbeitung durchführen.  
  
## <a name="syntax"></a>Syntax  
  
```  
#include <numeric>  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Algorithmen ähneln den Algorithmen für Standardvorlagenbibliotheken (STL), sind jedoch Teil der C++-Standardbibliothek. Trotzdem sind sie mit STL kompatibel und können ähnlich wie die STL-Algorithmen auf eine Reihe von Datenstrukturen angewendet werden. Dazu gehören STL-Containerklassen, z. B. [Vektor](vector%20Class.md) und [Liste](../standard-library/list-class.md), und programmdefinierte Datenstrukturen und Arrays von Elementen, die die Anforderungen eines bestimmten Algorithmus erfüllen. Algorithmen erzielen dieses Maß an Allgemeingültigkeit, indem sie indirekt über Iteratoren auf die Elemente eines Containers zugreifen und diese durchlaufen. Die Process-Iteratorbereiche für Algorithmen werden in der Regel durch ihre Start- oder Zielpositionen angegeben. Die Bereiche, die angegeben werden, müssen in dem Sinne gültig sein, dass alle Zeiger in den Bereichen dereferenzierbar sind und innerhalb der Sequenzen der einzelnen Bereiche liegen. Die letzte Position muss außerdem von der ersten mittels Zunahme erreichbar sein.  
  
 Die Algorithmen erweitern die Aktionen, die durch die Vorgänge und Memberfunktionen der einzelnen STL-Container unterstützt werden, und aktivieren die Interaktion mit verschiedenen Typen von Containerobjekten gleichzeitig.  
  
### <a name="functions"></a>Funktionen  
  
|||  
|-|-|  
|[Sammeln](../Topic/%3Cnumeric%3E%20functions.md#accumulate)|Berechnet die Summe aller Elemente in einem angegebenen Bereich, einschließlich Anfangswert, indem aufeinander folgende Teilsummen berechnet werden, oder berechnet das Ergebnis der aufeinander folgenden Teilergebnisse, die mithilfe eines angegebenen binären Vorgangs (außer Summe) abgerufen werden.|  
|[adjacent_difference](../Topic/%3Cnumeric%3E%20functions.md#adjacent_difference)|Berechnet die aufeinander folgenden Unterschiede zwischen einem Element und seinem Vorgänger in einem Eingabebereich und gibt die Ergebnisse in einem Zielbereich aus oder berechnet das Ergebnis einer allgemeinen Prozedur, in der der Vorgang zum Feststellen von Unterschieden durch einen anderen angegebenen binären Vorgang ersetzt wird.|  
|[inner_product](../Topic/%3Cnumeric%3E%20functions.md#inner_product)|Berechnet die Summe des elementweisen Produkts von zwei Bereichen und fügt sie einem angegebenen Anfangswert hinzu oder berechnet das Ergebnis einer allgemeinen Prozedur, in der die Summen- und Produktvorgänge durch andere angegebene binäre Vorgänge ersetzt werden.|  
|[Iota](../Topic/%3Cnumeric%3E%20functions.md#iota)|Speichert einen Startwert, beginnend mit dem ersten Element und füllt ihn mit aufeinander folgenden Schritten des Werts (`value++`) in jedem der Elemente im Intervall `[first, last)` auf.|  
|[partial_sum](../Topic/%3Cnumeric%3E%20functions.md#partial_sum)|Berechnet eine Reihe von Summen in einem Eingabebereich vom ersten Element über die *ich*th-Element und speichert das Ergebnis jeder Summe in der *ich*th-Element eines Zielbereichs, oder berechnet das Ergebnis einer allgemeinen Prozedur, in dem die Sum-Vorgang wird, von einem anderen ersetzt, angegebenen binären Vorgang.|  
  
## <a name="see-also"></a>Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Standard Template Library](../misc/standard-template-library.md)

