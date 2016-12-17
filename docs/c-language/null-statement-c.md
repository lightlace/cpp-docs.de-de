---
title: "NULL-Anweisung (C)"
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
  - "Ausdrücke [C++], NULL"
  - "NULL-Anweisung"
  - "NULL-Werte, Ausdrücke"
  - "Semikolon, C-NULL-Anweisung"
ms.assetid: 72576ce6-26d0-4379-be65-fee522088790
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
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