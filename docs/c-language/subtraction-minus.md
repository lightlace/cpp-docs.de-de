---
title: Subtraktion (-) | Microsoft-Dokumentation
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
- operators [C], subtraction
- subtraction operator, syntax
ms.assetid: 9cacba7d-20b3-4372-8a63-ba5d8ee64177
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 78723d67f5938f8c8e4cfd299a18de39da9787ab
ms.contentlocale: de-de
ms.lasthandoff: 04/01/2017

---
# <a name="subtraction--"></a>Subtraction (-)
Der Subtraktionsoperator (**-**) subtrahiert den zweiten Operanden vom ersten. Beide Operanden können entweder vom Typ „Ganze Zahl“ oder „Gleitkommazahl“ sein, oder ein Operand kann ein Zeiger und der andere eine ganze Zahl sein.  
  
 Wenn zwei Zeiger subtrahiert werden, wird die Differenz in einen ganzzahligen Wert mit Vorzeichen konvertiert, indem die Differenz durch die Größe eines Werts vom Typ geteilt wird, auf den die Zeiger zeigen. Die Größe des Integralwerts wird durch den Typ **ptrdiff_t** in der Standardincludedatei „stddef.h“ definiert. Das Ergebnis zeigt die Anzahl von Arbeitsspeicherpositionen dieses Typs zwischen den beiden Adressen. Das Ergebnis ist nur für zwei Elemente desselben Arrays garantiert sinnvoll, wie in [Zeigerarithmetik](../c-language/pointer-arithmetic.md) erläutert.  
  
 Wenn ein ganzzahliger Wert von einem Zeigerwert subtrahiert wird, konvertiert der Subtraktionsoperator den ganzzahligen Wert (*i*), indem er ihn mit der Größe des Werts multipliziert, auf den der Zeiger zeigt. Nach der Konvertierung stellt der ganzzahlige Wert *i* Arbeitsspeicherpositionen dar, wobei jede Position über die Länge verfügt, die vom Zeigertyp angegeben wird. Wenn der konvertierte ganzzahlige Wert vom Zeigerwert subtrahiert wird, ist das Ergebnis die Speicheradresse *i* Positionen vor der ursprünglichen Adresse. Der neue Zeiger zeigt auf einen Wert von dem Typ, der vom ursprünglichen Zeigerwert angegeben wurde.  
  
## <a name="see-also"></a>Siehe auch  
 [C-Operatoren (additiv)](../c-language/c-additive-operators.md)
