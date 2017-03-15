---
title: "IsATLProject | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IsATLProject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IsATLProject-Methode"
ms.assetid: 811115af-5bcd-4ce2-a514-34de4c7419ea
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# IsATLProject
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt an, ob ein Projekt ATL\-basiert ist.  
  
## Syntax  
  
```  
  
      function IsATLProject(   
   oProj    
);  
```  
  
#### Parameter  
 `oProj`  
 Das ausgewählte Projekt.  
  
## Rückgabewert  
 **true**, wenn es sich um ein ATL\-Projekt handelt; andernfalls **false**.  
  
## Hinweise  
 Gibt an, ob ein Projekt ATL\-basiert ist.  
  
## Beispiel  
  
```  
function CanAddATLSupport(selProj, selObj)  
{  
   if (IsATLProject(selProj))  
   {  
      var L_ErrMsg1_Text = "Current project already has ATL support.";  
      wizard.ReportError(L_ErrMsg1_Text);  
      return false;  
   }  
```  
  
## Siehe auch  
 [Anpassen von C\+\+\-Assistenten mit allgemeinen JScript\-Funktionen](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [JScript\-Funktionen für C\+\+\-Assistenten](../ide/jscript-functions-for-cpp-wizards.md)   
 [Erstellen eines benutzerdefinierten Assistenten](../ide/creating-a-custom-wizard.md)   
 [Entwerfen eines Assistenten](../ide/designing-a-wizard.md)   
 [IsAttributedProject](../ide/isattributedproject.md)