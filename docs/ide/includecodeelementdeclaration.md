---
title: "IncludeCodeElementDeclaration"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "IncludeCodeElementDeclaration"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IncludeCodeElementDeclaration-Methode"
ms.assetid: 714e76e4-76bc-439a-982a-cf9d4ada7677
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# IncludeCodeElementDeclaration
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Fügt `strInFile` die **include**\-Anweisung hinzu, wobei auch der Header mit dem implementierten `strCodeElemName` eingefügt wird, falls `oProj` einen solchen Header enthält.  
  
## Syntax  
  
```  
  
      function IncludeCodeElementDeclaration(   
   oProj,   
   strCodeElemName,   
   strInFile    
);  
```  
  
#### Parameter  
 `oProj`  
 Das ausgewählte Projekt.  
  
 `strCodeElemName`  
 Der vollständige Name des Codeelements, dessen Definitionsheader gesucht wird.  
  
 `strInFile`  
 Die Datei, in die der Definitionsheader eingefügt wird \(falls dieser gefunden wird\).  
  
## Hinweise  
 Fügt `strInFile` die **include**\-Anweisung hinzu, wobei auch der Header mit dem implementierten `strCodeElemName` eingefügt wird, falls `oProj` einen solchen Header enthält.  
  
## Siehe auch  
 [Anpassen von C\+\+\-Assistenten mit allgemeinen JScript\-Funktionen](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [JScript\-Funktionen für C\+\+\-Assistenten](../ide/jscript-functions-for-cpp-wizards.md)   
 [Erstellen eines benutzerdefinierten Assistenten](../ide/creating-a-custom-wizard.md)   
 [Entwerfen eines Assistenten](../ide/designing-a-wizard.md)