---
title: Angepasste C-Ganzzahltypen | Microsoft-Dokumentation
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
- sized integer types
ms.assetid: 0d6199b4-d0ab-4e8c-a769-785f5afb92eb
caps.latest.revision: 8
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
ms.openlocfilehash: db04c6862be26d5641a485c47ac7fd71b43d16fe
ms.contentlocale: de-de
ms.lasthandoff: 05/18/2017

---
# <a name="c-sized-integer-types"></a>C-Ganzzahltypen (angepasst)
**Microsoft-spezifisch**  
  
 Microsoft C bietet Unterstützung für ganzzahlige Typen mit angegebener Größe. Sie können 8-, 16-, 32- oder 64-Bit-Ganzzahl-Variablen deklarieren, indem Sie den __int*n*-Typbezeichner verwenden, wobei *n* die Größe der ganzzahligen Variable (in Bit) ist. Der Wert von *n* kann 8, 16, 32 oder 64 sein. Im folgenden Beispiel wird eine Variable für jeden der vier Typen der nach Größe angepassten Ganzzahlen deklariert:  
  
```  
__int8 nSmall;      // Declares 8-bit integer  
__int16 nMedium;    // Declares 16-bit integer  
__int32 nLarge;     // Declares 32-bit integer  
__int64 nHuge;      // Declares 64-bit integer  
```  
  
 Die ersten drei Typen der nach Größe angepassten Ganzzahlen sind Synonyme für die ANSI-Typen, die die gleichen Größe haben und nützlich für das Schreiben von übertragbarem Code sind, der sich auf vielen verschiedenen Plattformen genau gleich verhält. Beachten Sie, dass der __int8-Datentyp mit dem Typ „char“ synonym ist, \___int16 mit dem Typ „short“ synonym ist und \___int32 mit dem Typ „int“ synonym ist. Der \___int64-Typ verfügt über keine äquivalente ANSI-Entsprechung.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Speicherung von einfachen Typen](../c-language/storage-of-basic-types.md)
