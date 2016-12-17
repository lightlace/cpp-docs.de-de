---
title: "Degradierung von ganzen Zahlen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Degradieren von Ganzzahlen"
ms.assetid: 51fb3654-60b0-4de7-80eb-bd910086c18a
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Degradierung von ganzen Zahlen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

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
  
 Wenn Variablen mit Vorzeichen in Variablen ohne Vorzeichen und umgekehrt konvertiert werden, bleiben die Bitmuster identisch.  Zum Beispiel ergibt die Umwandlung von – 2 \(0xFE\) in einen Wert ohne Vorzeichen 254 \(auch 0xFE\).  
  
## Siehe auch  
 [Ganze Zahlen](../c-language/integers.md)