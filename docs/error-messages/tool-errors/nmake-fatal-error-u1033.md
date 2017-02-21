---
title: "NMAKE: Schwerwiegender Fehler U1033 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "U1033"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1033"
ms.assetid: c146f7b5-7d5c-4329-a522-28a648546016
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# NMAKE: Schwerwiegender Fehler U1033
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Syntaxfehler: 'Zeichenfolge' unerwartet  
  
 Die Zeichenfolge ist nicht Teil einer gültigen Syntax für ein Makefile.  
  
### Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Falls sich das schließende Winkelklammernpaar \(**\<\<**\) für eine Inlinedatei nicht am Anfang eine Zeile befindet, tritt folgender Fehler auf:  
  
    ```  
    syntax error : 'EOF' unexpected  
    ```  
  
2.  Falls eine Makrodefinition im Makefile ein Gleichheitszeichen \(**\=**\) ohne einen voranstehenden Namen enthält oder falls es sich bei dem definierten Namen um ein Makro handelt, das nicht erweitert, tritt folgender Fehler auf:  
  
    ```  
    syntax error : '=' unexpected  
    ```  
  
3.  Falls sich ein Semikolon \(**;**\) in einer Kommentarzeile in **TOOLS.INI** nicht am Anfang der Zeile befindet, tritt folgender Fehler auf:  
  
    ```  
    syntax error : ';' unexpected  
    ```  
  
4.  Falls ein Makefile von einem Textverarbeitungsprogramm formatiert wurde, kann der folgende Fehler auftreten:  
  
    ```  
    syntax error : ':' unexpected  
    ```