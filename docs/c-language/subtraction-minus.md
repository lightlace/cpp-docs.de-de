---
title: "Subtraktion (-)"
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
  - "Operatoren [C], Subtraktion"
  - "Subtraktionsoperator, Syntax"
ms.assetid: 9cacba7d-20b3-4372-8a63-ba5d8ee64177
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Subtraktion (-)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der Subtraktionsoperator \(**–**\) subtrahiert den zweiten Operanden vom ersten.  Beide Operanden können entweder vom Typ ganze Zahl oder Gleitkommazahl sein, oder ein Operand kann ein Zeiger und der andere eine ganze Zahl sein.  
  
 Wenn zwei Zeiger subtrahiert werden, wird die Differenz in einen ganzzahligen Wert mit Vorzeichen konvertiert, indem die Differenz durch die Größe eines Werts vom Typ geteilt wird, auf den die Zeiger zeigen.  Die Größe des ganzzahligen Werts wird durch den Typ **ptrdiff\_t** in der Standardincludedatei STDDEF.H definiert.  Das Ergebnis zeigt die Anzahl von Arbeitsspeicherpositionen dieses Typs zwischen den beiden Adressen.  Das Ergebnis ist nur für zwei Elemente desselben Arrays garantiert sinnvoll, wie in [Zeigerarithmetik](../c-language/pointer-arithmetic.md) erläutert.  
  
 Wenn ein ganzzahliger Wert von einem Zeigerwert subtrahiert wird, konvertiert der Subtraktionsoperator den ganzzahligen Wert \(*i*\), indem er ihn mit der Größe des Werts multipliziert, auf den der Zeiger zeigt.  Nach der Konvertierung stellt der ganzzahlige Wert *i* Arbeitsspeicherpositionen dar, wobei jede Position über die Länge verfügt, die vom Zeigertyp angegeben wird.  Wenn der konvertierte ganzzahlige Wert vom Zeigerwert subtrahiert wird, ist das Ergebnis die Speicheradresse *i* Positionen vor der ursprünglichen Adresse.  Der neue Zeiger zeigt auf einen Wert von dem Typ, der vom ursprünglichen Zeigerwert angegeben wurde.  
  
## Siehe auch  
 [C\-Operatoren \(additiv\)](../c-language/c-additive-operators.md)