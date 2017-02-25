---
title: "CreateProject | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CreateProject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateProject-Methode"
ms.assetid: b5598b46-fe29-4ad0-8bfe-a4dc789aeebd
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# CreateProject
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Erstellt ein C\+\+\-Projekt.  
  
## Syntax  
  
```  
  
      function CreateProject(   
   strProjectName,   
   strProjectPath    
);  
```  
  
#### Parameter  
 `strProjectName`  
 Eine Zeichenfolge, die den Projektnamen enthält.  
  
 *strProjectPath*  
 Eine Zeichenfolge, die den Projektpfad enthält.  
  
## Rückgabewert  
 Das Projektobjekt.  
  
## Hinweise  
 Rufen Sie diese Funktion auf, um ein C\+\+\-Projekt zu erstellen, das Sie in Visual Studio öffnen können.  Wenn der **WizardType**\-Kontextparameter des Assistenten als **vsWizardAddSubProject** festgelegt ist, wird das Projekt dem bestehenden Projekt als Unterprojekt hinzugefügt.  Weitere Informationen finden Sie unter [ContextParams\-Enumeration](../Topic/Context%20Parameters%20for%20Launching%20Wizards.md).  
  
## Beispiel  
 Siehe [AddFilesToProject](../ide/addfilestoproject.md).  
  
## Siehe auch  
 [Anpassen von C\+\+\-Assistenten mit allgemeinen JScript\-Funktionen](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [JScript\-Funktionen für C\+\+\-Assistenten](../ide/jscript-functions-for-cpp-wizards.md)   
 [Erstellen eines benutzerdefinierten Assistenten](../ide/creating-a-custom-wizard.md)   
 [Entwerfen eines Assistenten](../ide/designing-a-wizard.md)