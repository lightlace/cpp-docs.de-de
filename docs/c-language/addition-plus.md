---
title: Addition (+) | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- pointers, adding integers
ms.assetid: b9014fee-825d-46ef-91db-5d46807081fc
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 021f7099c6028f4f94dbb37b34ce165c0324c329
ms.contentlocale: de-de
ms.lasthandoff: 05/18/2017

---
# <a name="addition-"></a>Addition (+)
Der Additionsoperator (**+**) sorgt dafür, dass seine beiden Operanden hinzugefügt werden. Beide Operanden können entweder vom Typ „Ganze Zahl“ oder „Gleitkommazahl“ sein, oder ein Operand kann ein Zeiger und der andere eine ganze Zahl sein.  
  
 Wenn eine ganze Zahl zu einem Zeiger addiert wird, wird der Ganzzahlwert (*i*) konvertiert, indem er mit der Größe des Werts multipliziert wird, auf den der Zeiger zeigt. Nach der Konvertierung stellt der ganzzahlige Wert *i* Arbeitsspeicherpositionen dar, wobei jede Position über die Länge verfügt, die vom Zeigertyp angegeben wird. Wenn der konvertierte Ganzzahlwert zum Zeigerwert addiert wird, ist das Ergebnis ein neuer Zeigerwert, der die Adresse in der Entfernung von *i* Positionen von der ursprünglichen Adresse darstellt. Der neue Zeigerwert gibt den Wert desselben Typs an, der vom ursprüngliche Zeigerwert adressiert wurde. Dieser Wert gleicht der Arrayindizierung (siehe [Eindimensionale Arrays](../c-language/one-dimensional-arrays.md) und [Mehrdimensionale Arrays](../c-language/multidimensional-arrays-c.md)). Wenn der Summenzeiger über das Array hinaus zeigt (außer auf die erste Position oberhalb des oberen Grenzwerts), ist das Ergebnis nicht definiert. Weitere Informationen finden Sie unter [Zeigerarithmetik](../c-language/pointer-arithmetic.md).  
  
## <a name="see-also"></a>Siehe auch  
 [C-Operatoren (additiv)](../c-language/c-additive-operators.md)
