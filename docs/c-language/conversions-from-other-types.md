---
title: Konvertierungen von anderen Typen | Microsoft-Dokumentation
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
- values, converting
- type casts, conversion
ms.assetid: 30fbd974-8f5a-4b70-ac44-d3937b96b702
caps.latest.revision: 9
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
ms.openlocfilehash: e4a0b8b8a377808a18cc106cd2edeef7ecde4abc
ms.contentlocale: de-de
ms.lasthandoff: 05/18/2017

---
# <a name="conversions-from-other-types"></a>Konvertierungen von anderen Typen
Da ein `enum`-Wert definitionsgemäß ein `int`-Wert ist, sind Konvertierungen aus und in einen `enum`-Wert identisch mit denen für den Typ `int`. Für den Microsoft C-Compiler entspricht eine Ganzzahl **long**.  
  
 **Microsoft-spezifisch**  
  
 Es sind keine Konvertierungen zwischen Struktur- oder Union-Typen zulässig.  
  
 Jeder Wert kann in den Typ `void` konvertiert werden, aber das Ergebnis einer solchen Konvertierung kann nur in einem Kontext verwendet werden, in dem ein Ausdruckswert verworfen wird, z. B. in einer Ausdrucksanweisung.  
  
 Der `void`-Typ hat definitionsgemäß keinen Wert. Daher kann er nicht in einen anderen Typ konvertiert werden, und andere Typen können nicht durch Zuweisung in `void` konvertiert werden. Sie können jedoch explizit einen Wert in den Typ `void` umwandeln, wie in [Typumwandlungskonvertierungen](../c-language/type-cast-conversions.md) erläutert.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Zuweisungskonvertierungen](../c-language/assignment-conversions.md)
