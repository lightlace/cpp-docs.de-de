---
title: numerisch (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- <cliext/numeric>
dev_langs:
- C++
helpviewer_keywords:
- numeric functions [STL/CLR]
- <cliext/numeric> header [STL/CLR]
- <numeric> header [STL/CLR]
ms.assetid: 1dc4d9a3-e734-459c-9678-5d9be0ef4c79
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 8d02423b2f8a2573fb4a90fd6f348a8e012dc91b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="numeric-stlclr"></a>numeric (STL/CLR)
Definiert containervorlagenfunktionen, die für die numerische Verarbeitung bereitgestellte Algorithmen ausführen.  
  
## <a name="syntax"></a>Syntax  
  
```  
#include <cliext/numeric>  
```  
  
## <a name="functions"></a>Funktionen  
  
|Funktion|Beschreibung|  
|--------------|-----------------|  
|[accumulate (STL/CLR)](../dotnet/accumulate-stl-clr.md)|Berechnet die Summe aller Elemente in einem angegebenen Bereich, einschließlich einigen Anfangswerten, indem aufeinander folgende Teilsummen berechnet werden, oder berechnet das Ergebnis der aufeinander folgenden Teilergebnisse, die auf ähnliche Weise mithilfe eines angegebenen binären Vorgangs (außer Summe) abgerufen werden.|  
|[adjacent_difference (STL/CLR)](../dotnet/adjacent-difference-stl-clr.md)|Berechnet die aufeinander folgenden Unterschiede zwischen einem Element und seinem Vorgänger in einem Eingabebereich und gibt die Ergebnisse in einem Zielbereich aus oder berechnet das Ergebnis einer allgemeinen Prozedur, in der der Vorgang zum Feststellen von Unterschieden durch einen anderen angegebenen binären Vorgang ersetzt wird.|  
|[inner_product (STL/CLR)](../dotnet/inner-product-stl-clr.md)|Berechnet die Summe des elementweisen Produkts von zwei Bereichen und fügt sie einem angegebenen Anfangswert hinzu oder berechnet das Ergebnis einer allgemeinen Prozedur, in der die Summen- und Produktvorgänge durch andere angegebene binäre Vorgänge ersetzt werden.|  
|[partial_sum (STL/CLR)](../dotnet/partial-sum-stl-clr.md)|Berechnet eine Reihe von Summen in einem Eingabebereich vom ersten Element über die `i`th-Element und speichert das Ergebnis jeder Summe im `i`th-Element eines Zielbereichs oder berechnet das Ergebnis einer allgemeinen Prozedur, in dem die Sum-Vorgang wird von einem anderen angegebenen binären Vorgang ersetzt.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext/Numeric >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [Referenz zur STL/CLR-Bibliothek](../dotnet/stl-clr-library-reference.md)