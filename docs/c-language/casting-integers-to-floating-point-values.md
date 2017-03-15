---
title: "Umwandlung ganzer Zahlen in Gleitkommazahlen-Punktwerte | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Ganze Zahlen, Umwandeln in Gleitkommawerte"
ms.assetid: 81fd5b7d-15eb-4c11-a8c8-e1621ff54fd3
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Umwandlung ganzer Zahlen in Gleitkommazahlen-Punktwerte
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 3.2.1.3** Die Richtung des Abschneidens, wenn eine Ganzzahl in eine Gleitkommazahl konvertiert wird, die den ursprünglichen Wert nicht genau darstellen kann.  
  
 Wenn eine Ganzzahl in einen Gleitkommawert umgewandelt wird, der den Wert nicht genau darstellen kann, wird der Wert auf den geeigneten nächsten Wert auf\- oder abgerundet.  
  
 Zum Beispiel wird beim Umwandeln eines **unsigned long**\-Werts \(mit 32 Bits Genauigkeit\) in einen **float**\-Wert \(dessen Mantisse 23 Bits Genauigkeit hat\)die Zahl auf das nächste Vielfache von 256 gerundet.  Die **long**\-Werte 4.294.966.913 bis 4.294.967.167 werden alle auf den **float**\-Wert 4.294.967.040 abgerundet.  
  
## Siehe auch  
 [Gleitkommaoperationen](../c-language/floating-point-math.md)