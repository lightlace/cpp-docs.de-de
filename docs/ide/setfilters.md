---
title: "SetFilters | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SetFilters"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetFilters-Methode"
ms.assetid: ae934e1b-8ead-4c1d-a0f8-e9c80d182340
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# SetFilters
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Fügt Quell\-, Include\- und Ressourcenfilter für Projektordner hinzu.  
  
## Syntax  
  
```  
  
      function SetFilters(   
   oProj    
);  
```  
  
#### Parameter  
 `oProj`  
 Das ausgewählte Projekt.  
  
## Hinweise  
 Rufen Sie diese Funktion auf, um Quell\-, Include\- und Ressourcenfilter für Projektordner hinzuzufügen.  Diese Funktion sucht im Projekt nach den folgenden Symbolen:  
  
-   SOURCE\_FILTER  
  
-   INCLUDE\_FILTER  
  
-   RESOURCE\_FILTER  
  
 Diese Symbole enthalten die Dateierweiterungen, die beim Filtern verwendet werden.  
  
## Beispiel  
  
```  
// Create and set the project name and path.  
selProj = CreateProject(strProjectName, strProjectPath);  
// Add the previously-identified configurations to the project.  
AddConfigurations(selProj, strProjectName);  
// Set filters for the project.  
SetFilters (selproj);  
// Indicate that the project is an ATL project.  
selProj.Object.keyword = "AtlProj";  
```  
  
## Siehe auch  
 [Anpassen von C\+\+\-Assistenten mit allgemeinen JScript\-Funktionen](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [JScript\-Funktionen für C\+\+\-Assistenten](../ide/jscript-functions-for-cpp-wizards.md)   
 [Erstellen eines benutzerdefinierten Assistenten](../ide/creating-a-custom-wizard.md)   
 [Entwerfen eines Assistenten](../ide/designing-a-wizard.md)