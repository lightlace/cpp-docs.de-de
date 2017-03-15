---
title: "DoesIncludeExist | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "DoesIncludeExist"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DoesIncludeExist-Methode"
ms.assetid: 39751a3d-dfe5-423c-bd94-a53771c3e360
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# DoesIncludeExist
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt an, ob in der Datei eine `#include`\-Anweisung für eine bestimmte Headerdatei vorhanden ist.  
  
## Syntax  
  
```  
  
      function DoesIncludeExist(   
   oProj,   
   strHeaderFile,   
   strInsertIntoFile    
);  
```  
  
#### Parameter  
 `oProj`  
 Das ausgewählte Projekt.  
  
 *strHeaderFile*  
 Der Name der zu suchenden Headerdatei.  
  
 `strInsertIntoFile`  
 Die Quelldatei, die die `#include`\-Anweisung für die Headerdatei enthält \(ohne den Pfad\).  
  
## Rückgabewert  
 **true**, wenn der angegebene Header in der Datei enthalten ist; andernfalls **false**.  
  
## Hinweise  
 Gibt an, ob in der durch `strInsertIntoFile` angegebenen Datei eine `#include`\-Anweisung für eine bestimmte Headerdatei vorhanden ist.  
  
## Beispiel  
  
```  
// Check to see if #include for atlbase.h   
// is included in the project's stdafx.h.  
// and add it if it is not.  
if (!DoesIncludeExist(selProj, "<atlbase.h>", strSTDAFX))  
   oCM.AddInclude("<atlbase.h>", strSTDAFX, vsCMAddPositionEnd);  
```  
  
## Siehe auch  
 [Anpassen von C\+\+\-Assistenten mit allgemeinen JScript\-Funktionen](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [JScript\-Funktionen für C\+\+\-Assistenten](../ide/jscript-functions-for-cpp-wizards.md)   
 [Erstellen eines benutzerdefinierten Assistenten](../ide/creating-a-custom-wizard.md)   
 [Entwerfen eines Assistenten](../ide/designing-a-wizard.md)