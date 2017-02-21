---
title: "__if_not_exists-Anweisung | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__if_not_exists"
  - "__if_not_exists_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__if_not_exists-Schlüsselwort [C++]"
ms.assetid: a2f322d4-e96f-4a32-954e-4323d20c6e32
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# __if_not_exists-Anweisung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die `__if_not_exists`\-Anweisung testet, ob der angegebene Bezeichner vorhanden ist.  Wenn der Bezeichner nicht vorhanden ist, wird der angegebene Anweisungsblock ausgeführt.  
  
## Syntax  
  
```  
__if_not_exists ( identifier ) {   
statements  
};  
```  
  
#### Parameter  
  
|Parameter|Beschreibung|  
|---------------|------------------|  
|`identifier`|Der Bezeichner, dessen Vorhandensein Sie überprüfen möchten.|  
|`statements`|Eine oder mehrere Anweisungen, die auszuführen sind, wenn `identifier` nicht vorhanden ist.|  
  
## Hinweise  
  
> [!CAUTION]
>  Um die zuverlässigsten Ergebnisse zu erzielen, verwenden Sie die `__if_not_exists`\-Anweisung mit den folgenden Einschränkungen.  
  
-   Wenden Sie die `__if_not_exists`\-Anweisung nur auf einfache Typen, nicht auf Vorlagen an.  
  
-   Wenden Sie die `__if_not_exists`\-Anweisung auf Bezeichner innerhalb oder außerhalb einer Klasse an.  Übernehmen Sie die `__if_not_exists`\-Anweisung nicht für lokale Variablen.  
  
-   Verwenden Sie die `__if_not_exists`\-Anweisung nur im Text einer Funktion.  Außerhalb des Texts einer Funktion kann die `__if_not_exists`\-Anweisung nur vollständig definierte Typen testen.  
  
-   Wenn Sie auf überladene Funktionen testen, können Sie nicht auf eine bestimmte Form der Überladung testen.  
  
 Die Ergänzung zur `__if_not_exists`\-Anweisung ist die [\_\_if\_exists](../cpp/if-exists-statement.md)\-Anweisung.  
  
## Beispiel  
 Ein Beispiel für die Verwendung von `__if_not_exists` finden Sie unter [\_\_if\_exists\-Anweisung](../cpp/if-exists-statement.md).  
  
## Siehe auch  
 [Auswahlanweisungen](../cpp/selection-statements-cpp.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)   
 [\_\_if\_exists\-Anweisung](../cpp/if-exists-statement.md)