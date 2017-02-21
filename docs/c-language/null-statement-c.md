---
title: "NULL-Anweisung (C) | Microsoft Docs"
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
  - "Ausdrücke [C++], NULL"
  - "NULL-Anweisung"
  - "NULL-Werte, Ausdrücke"
  - "Semikolon, C-NULL-Anweisung"
ms.assetid: 72576ce6-26d0-4379-be65-fee522088790
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# NULL-Anweisung (C)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine "NULL\-Anweisung" ist eine Anweisung, die nur ein Semikolon enthält. Sie kann an jeder Stelle stehen, an der eine Anweisung erwartet wird.  Wenn eine NULL\-Anweisung ausgeführt wird, passiert nichts.  Dies ist die korrekte Methode, eine NULL\-Anweisung zu codieren:  
  
## Syntax  
  
```  
  
;  
  
```  
  
## Hinweise  
 Anweisungen wie **do**, **for**, **if** und `while` erfordern als Anweisungstext eine ausführbare Anweisung.  Die NULL\-Anweisung erfüllt die Syntaxanforderung in Fällen, die keinen substanziellen Anweisungstext benötigen.  
  
 Wie bei jeder anderen C\-Anweisung können Sie vor einer NULL\-Anweisung eine Bezeichnung einfügen.  Um ein Element zu bezeichnen, das keine Anweisung ist, z. B. die schließende Klammer einer Verbundanweisung, können Sie eine NULL\-Anweisung bezeichnen und direkt vor dem Element einfügen, um dasselbe Ergebnis zu erzielen.  
  
 In diesem Beispiel wird die NULL\-Anweisung veranschaulicht:  
  
```  
for ( i = 0; i < 10; line[i++] = 0 )  
     ;  
```  
  
 Im Beispiel initialisiert der Schleifenausdruck der **for**\-Anweisung `line[i++] = 0` die ersten 10 Elemente von `line` mit 0.  Der Anweisungstext ist eine NULL\-Anweisung, da keine weiteren Anweisungen erforderlich sind.  
  
## Siehe auch  
 [Anweisungen](../c-language/statements-c.md)