---
title: '&lt;numerisch&gt; | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std::<numeric>
- std.<numeric>
- <numeric>
dev_langs:
- C++
helpviewer_keywords:
- <numeric> header
ms.assetid: 6d6ccb94-48cc-479b-b4a9-bd9c78d4896a
caps.latest.revision: 23
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: 1af103aee129eee8176d6c34754521f7c2381da7
ms.lasthandoff: 02/24/2017

---
# <a name="ltnumericgt"></a>&lt;numerisch&gt;
Definiert Containervorlagenfunktionen, die Algorithmen für die numerische Verarbeitung durchführen.  
  
## <a name="syntax"></a>Syntax  
  
```  
#include <numeric>  
```  
  
## <a name="remarks"></a>Hinweise  
Die numerischen Algorithmen ähneln den Algorithmen der C++-Standardbibliothek in [\<algorithm>](algorithm.md) und können für einer Vielzahl von Datenstrukturen ausgeführt werden. Dazu gehören Standard-Bibliothekscontainerklassen, z.B. [vector](../standard-library/vector-class.md) und [list](../standard-library/list-class.md), sowie programmdefinierte Datenstrukturen und Arrays von Elementen, die die Anforderungen eines bestimmten Algorithmus erfüllen. Algorithmen erzielen dieses Maß an Allgemeingültigkeit, indem sie indirekt über Iteratoren auf die Elemente eines Containers zugreifen und diese durchlaufen. Die Process-Iteratorbereiche für Algorithmen werden in der Regel durch ihre Start- oder Zielpositionen angegeben. Die Bereiche, die angegeben werden, müssen in dem Sinne gültig sein, dass alle Zeiger in den Bereichen dereferenzierbar sind und innerhalb der Sequenzen der einzelnen Bereiche liegen. Die letzte Position muss außerdem von der ersten mittels Zunahme erreichbar sein.  
  
 Die Algorithmen erweitern die Aktionen, die durch die Vorgänge und Memberfunktionen der einzelnen C++-Standardbibliothekscontainer unterstützt werden, und aktivieren die Interaktion mit verschiedenen Typen von Containerobjekten gleichzeitig.  
  
### <a name="functions"></a>Funktionen  
  
|||  
|-|-|  
|[accumulate](../standard-library/numeric-functions.md#accumulate)|Berechnet die Summe aller Elemente in einem angegebenen Bereich, einschließlich Anfangswert, indem aufeinander folgende Teilsummen berechnet werden, oder berechnet das Ergebnis der aufeinander folgenden Teilergebnisse, die mithilfe eines angegebenen binären Vorgangs (außer Summe) abgerufen werden.|  
|[adjacent_difference](../standard-library/numeric-functions.md#adjacent_difference)|Berechnet die aufeinander folgenden Unterschiede zwischen einem Element und seinem Vorgänger in einem Eingabebereich und gibt die Ergebnisse in einem Zielbereich aus oder berechnet das Ergebnis einer allgemeinen Prozedur, in der der Vorgang zum Feststellen von Unterschieden durch einen anderen angegebenen binären Vorgang ersetzt wird.|  
|[inner_product](../standard-library/numeric-functions.md#inner_product)|Berechnet die Summe des elementweisen Produkts von zwei Bereichen und fügt sie einem angegebenen Anfangswert hinzu oder berechnet das Ergebnis einer allgemeinen Prozedur, in der die Summen- und Produktvorgänge durch andere angegebene binäre Vorgänge ersetzt werden.|  
|[iota](../standard-library/numeric-functions.md#iota)|Speichert einen Startwert, beginnend mit dem ersten Element und füllt ihn mit aufeinander folgenden Schritten des Werts (`value++`) in jedem der Elemente im Intervall `[first, last)` auf.|  
|[partial_sum](../standard-library/numeric-functions.md#partial_sum)|Berechnet eine Reihe von Summen in einem Eingabebereich vom ersten Element bis zum *i*th-Element und speichert das Ergebnis jeder Summe im *i*th-Element eines Zielbereichs oder berechnet das Ergebnis einer allgemeinen Prozedur, in der der Summenvorgang durch einen anderen angegebenen binären Vorgang ersetzt wird.|  
  
## <a name="see-also"></a>Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)


