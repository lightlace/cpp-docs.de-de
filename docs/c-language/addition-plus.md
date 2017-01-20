---
title: "Addition (+)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Zeiger, Hinzufügen von Ganzzahlen"
ms.assetid: b9014fee-825d-46ef-91db-5d46807081fc
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Addition (+)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der Addition\-Operator \(**\+**\) sorgt dafür, dass seine beiden Operanden hinzugefügt werden.  Beide Operanden können entweder vom Typ ganze Zahl oder Gleitkommazahl sein, oder ein Operand kann ein Zeiger und der andere eine ganze Zahl sein.  
  
 Wenn eine ganze Zahl zu einem Zeiger addiert wird, wird der Ganzzahlwert \(*i*\) konvertiert, indem er mit der Größe des Werts multipliziert wird, auf den der Zeiger zeigt.  Nach der Konvertierung stellt der ganzzahlige Wert *i* Arbeitsspeicherpositionen dar, wobei jede Position über die Länge verfügt, die vom Zeigertyp angegeben wird.  Wenn der konvertierte Ganzzahlwert zum Zeigerwert addiert wird, ist das Ergebnis ein neuer Zeigerwert, der die Adresse in der Entfernung von *i* Positionen von der ursprünglichen Adresse darstellt.  Der neue Zeigerwert gibt den Wert desselben Typs an, der vom ursprüngliche Zeigerwert adressiert wurde. Dieser Wert gleicht der Arrayindizierung \(siehe [Eindimensionale Arrays](../c-language/one-dimensional-arrays.md) und [Mehrdimensionale Arrays](../c-language/multidimensional-arrays-c.md)\).  Wenn der Summenzeiger über das Array hinaus zeigt \(außer auf die erste Position oberhalb des oberen Grenzwerts\), ist das Ergebnis nicht definiert.  Weitere Informationen finden Sie unter [Zeigerarithmetik](../c-language/pointer-arithmetic.md).  
  
## Siehe auch  
 [C\-Operatoren \(additiv\)](../c-language/c-additive-operators.md)