---
title: Umwandlung ganzer Zahlen in Gleitkommawerte | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- integers, casting to floating-point values
ms.assetid: 81fd5b7d-15eb-4c11-a8c8-e1621ff54fd3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e00fdfc44c5939dbed2fb3258f0cab0023feeda0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="casting-integers-to-floating-point-values"></a>Umwandlung ganzer Zahlen in Gleitkommazahlen-Punktwerte
**ANSI 3.2.1.3** Die Richtung des Abschneidens, wenn eine Ganzzahl in eine Gleitkommazahl konvertiert wird, die den ursprünglichen Wert nicht genau darstellen kann.  
  
 Wenn eine Ganzzahl in einen Gleitkommawert umgewandelt wird, der den Wert nicht genau darstellen kann, wird der Wert auf den geeigneten nächsten Wert auf- oder abgerundet.  
  
 Zum Beispiel wird beim Umwandeln eines **unsigned long**-Werts (mit 32 Bits Genauigkeit) in einen **float**-Wert (dessen Mantisse 23 Bits Genauigkeit hat) die Zahl auf das nächste Vielfache von 256 gerundet. Die **long**-Werte 4.294.966.913 bis 4.294.967.167 werden alle auf den **float**-Wert 4.294.967.040 abgerundet.  
  
## <a name="see-also"></a>Siehe auch  
 [Gleitkommaoperationen](../c-language/floating-point-math.md)