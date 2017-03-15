---
title: "LineBeginsWith | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "LineBeginsWith"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LineBeginsWith-Methode"
ms.assetid: cbdd08ad-7309-4504-9f23-1c22bb3e4bd0
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# LineBeginsWith
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wird von [InsertIntoFunction](../ide/insertintofunction.md) aufgerufen, um festzustellen, ob eine Zeile mit einer bestimmten Zeichenfolge beginnt.  
  
## Syntax  
  
```  
  
      function LineBeginsWith(   
   strBody,   
   strSearchString,   
   nStartPos    
);  
```  
  
#### Parameter  
 *strBody*  
 Der Funktionsrumpf.  
  
 `strSearchString`  
 Die zu suchende Zeichenfolge.  
  
 *nStartPos*  
 Der Startpunkt für die Suche.  
  
## Rückgabewert  
 **true**, wenn die Zeichenfolge gefunden wird; andernfalls **false**.  
  
## Hinweise  
 Diese Funktion wird von `InsertIntoFunction` aufgerufen, um festzustellen, ob die angegebene Zeile mit der angegebenen Zeichenfolge beginnt.  
  
## Siehe auch  
 [Anpassen von C\+\+\-Assistenten mit allgemeinen JScript\-Funktionen](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [JScript\-Funktionen für C\+\+\-Assistenten](../ide/jscript-functions-for-cpp-wizards.md)   
 [Erstellen eines benutzerdefinierten Assistenten](../ide/creating-a-custom-wizard.md)   
 [Entwerfen eines Assistenten](../ide/designing-a-wizard.md)   
 [OffsetToLineNumber](../ide/offsettolinenumber.md)