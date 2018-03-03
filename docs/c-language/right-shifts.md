---
title: Verschiebungen nach rechts | Microsoft-Dokumentation
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
ms.assetid: c878e97d-ea3c-4c6b-90a8-b1b24b2d5b19
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 307cf91bf86f2912ad6cafa7e89f48e614c3865a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="right-shifts"></a>Verschiebungen nach rechts
Das Ergebnis einer Rechtsverschiebung eines Ganzzahltyps mit Vorzeichen mit negativem Wert  
  
 Das Verschieben eines negativen Werts nach rechts ergibt die Hälfte des absoluten Werts (abgerundet). Zum Beispiel ein signierter `short` Wert -253 (hexadezimal 0xFF03, Binärzahl 11111111 00000011) ein Bit nach rechts verschoben erzeugt -127 (hexadezimal 0xFF81, Binärzahl 11111111 10000001). Ein positiver nach rechts verschobener Wert 253 erzeugt + 126.  
  
 Rechtsverschiebungen behalten das signierte Bit des signierten Ganzzahltyps bei. Wenn eine ganze Zahl mit Vorzeichen nach rechts verschoben wird, bleibt das wichtigste Byte festgelegt. Wenn "0xF0000000" beispielsweise ein signierter `int` ist, ergibt eine Rechtsverschiebung den Wert "0xF8000000". Beim 32-maligen Verschieben eines negativen Werts `int` wird hierdurch "0xFFFFFFFF" erzeugt.  
  
 Bei der Rechtsverschiebung einer ganzen Zahl ohne Vorzeichen wird das wichtigste Byte gelöscht. Wenn "0xF000" nicht signiert ist, lautet das Ergebnis "0x7800". Beim 32-maligen Verschieben eines Werts `unsigned` oder positiven `int`-Werts wird hierdurch "0x00000000" erzeugt.  
  
## <a name="see-also"></a>Siehe auch  
 [Ganze Zahlen](../c-language/integers.md)