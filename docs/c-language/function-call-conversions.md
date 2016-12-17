---
title: "Funktionsaufrufkonvertierungen"
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
  - "Funktionsaufrufe, Argumenttypkonvertierungen"
  - "Funktionsaufrufe, Konvertieren"
  - "Funktionen [C], Argumentkonvertierungen"
ms.assetid: 04ea0f81-509a-4913-8b12-0937a81babcf
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Funktionsaufrufkonvertierungen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der Konvertierungstyp, der an Argumenten in einem Funktionsaufruf ausgeführt wird, hängt von der Anwesenheit eines Funktionsprototyps \(Vorwärtsdeklaration\) mit deklarierten Argumenttypen für die aufgerufene Funktion ab.  
  
 Wenn ein Funktionsprototyp vorhanden ist und deklarierte Argumenttypen enthält, führt der Compiler die Typüberprüfung aus \(siehe [Funktionen](../c-language/functions-c.md)\).  
  
 Wenn kein Funktionsprototyp vorhanden ist, werden nur die üblichen arithmetischen Konvertierungen mit den Argumenten im Funktionsaufruf ausgeführt.  Diese Konvertierungen werden für jedes Argument im Aufruf unabhängig ausgeführt.  Dies bedeutet, dass ein **float**\-Wert in einen **double**\-Wert, ein `char`\- oder **short**\-Wert in einen `int`\-Wert und ein `unsigned char`\- oder **unsigned short**\-Wert in einen `unsigned int`\-Wert konvertiert wird.  
  
## Siehe auch  
 [Typkonvertierungen](../c-language/type-conversions-c.md)