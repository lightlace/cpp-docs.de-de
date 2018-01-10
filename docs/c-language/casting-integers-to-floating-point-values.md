---
title: Umwandlung ganzer Zahlen in Gleitkommawerte | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: integers, casting to floating-point values
ms.assetid: 81fd5b7d-15eb-4c11-a8c8-e1621ff54fd3
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1d926b50cdd8caef1a1119aaf319bfae88970651
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="casting-integers-to-floating-point-values"></a>Umwandlung ganzer Zahlen in Gleitkommazahlen-Punktwerte
**ANSI 3.2.1.3** Die Richtung des Abschneidens, wenn eine Ganzzahl in eine Gleitkommazahl konvertiert wird, die den ursprünglichen Wert nicht genau darstellen kann.  
  
 Wenn eine Ganzzahl in einen Gleitkommawert umgewandelt wird, der den Wert nicht genau darstellen kann, wird der Wert auf den geeigneten nächsten Wert auf- oder abgerundet.  
  
 Zum Beispiel wird beim Umwandeln eines **unsigned long**-Werts (mit 32 Bits Genauigkeit) in einen **float**-Wert (dessen Mantisse 23 Bits Genauigkeit hat) die Zahl auf das nächste Vielfache von 256 gerundet. Die **long**-Werte 4.294.966.913 bis 4.294.967.167 werden alle auf den **float**-Wert 4.294.967.040 abgerundet.  
  
## <a name="see-also"></a>Siehe auch  
 [Gleitkommaoperationen](../c-language/floating-point-math.md)