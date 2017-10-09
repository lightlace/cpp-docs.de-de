---
title: Signierte bitweise Operationen | Microsoft-Dokumentation
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
- bitwise operations
- signed bitwise operations
ms.assetid: 1e5cf65b-ee32-41a0-a5c2-82c1854091f6
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: 9ffc5335bb28e619f166a524083937d17a59bb97
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="signed-bitwise-operations"></a>Signierte bitweise Operationen
**ANSI 3.3** Die Ergebnisse der bitweisen Vorgänge an Ganzzahlen mit Vorzeichen  
  
 Bitweise Vorgänge auf Ganzzahlen mit Vorzeichen arbeiten genauso wie bitweise Vorgänge auf Ganzzahlen ohne Vorzeichen. So kann beispielsweise `-16 & 99` binär ausgedrückt werden als  
  
```  
  11111111 11110000  
& 00000000 01100011  
  _________________  
  00000000 01100000  
```  
  
 Das Ergebnis des bitweisen AND-Vorgangs ist 96.  
  
## <a name="see-also"></a>Siehe auch  
 [Ganze Zahlen](../c-language/integers.md)
