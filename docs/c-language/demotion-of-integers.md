---
title: Degradierung von Ganzzahlen | Microsoft-Dokumentation
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
- demoting integers
ms.assetid: 51fb3654-60b0-4de7-80eb-bd910086c18a
caps.latest.revision: 6
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
ms.openlocfilehash: 468b88ccb64c06e64e9b234188295b3fcc148b1f
ms.contentlocale: de-de
ms.lasthandoff: 04/01/2017

---
# <a name="demotion-of-integers"></a>Degradierung von Ganzzahlen
**ANSI 3.2.1.2** Das Ergebnis der Konvertierung einer ganzen Zahl in eine kürzere Ganzzahl mit Vorzeichen oder das Ergebnis der Konvertierung einer Ganzzahl ohne Vorzeichen in eine Ganzzahl mit Vorzeichen derselben Länge, wenn der Wert nicht dargestellt werden kann  
  
 Wenn eine ganze Zahl vom Typ **long** in den Typ **short** oder vom Typ **short** in den Typ `char` umgewandelt wird, werden die unwichtigsten Bytes beibehalten.  
  
 Diese Zeile weist beispielsweise  
  
```  
short x = (short)0x12345678L;  
```  
  
 `x` den Wert 0x5678 zu, und diese Zeile  
  
```  
char y = (char)0x1234;  
```  
  
 weist `y` den Wert 0x34 zu.  
  
 Wenn Variablen mit Vorzeichen in Variablen ohne Vorzeichen und umgekehrt konvertiert werden, bleiben die Bitmuster identisch. Zum Beispiel ergibt die Umwandlung von -2 (0xFE) in einen Wert ohne Vorzeichen 254 (auch 0xFE).  
  
## <a name="see-also"></a>Siehe auch  
 [Ganze Zahlen](../c-language/integers.md)
