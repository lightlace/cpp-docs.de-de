---
title: Konvertierungen von anderen Typen | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- values, converting
- type casts, conversion
ms.assetid: 30fbd974-8f5a-4b70-ac44-d3937b96b702
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ed56c0c9ab3186200d3cbb47224dedc60adddb2f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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