---
title: "IsMFCProject | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IsMFCProject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IsMFCProject-Methode"
ms.assetid: 98dd57df-9fdb-40d7-afcf-4b99e9d54dad
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# IsMFCProject
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Überprüft, ob ein Projekt MFC\-basiert ist.  
  
## Syntax  
  
```  
  
      function IsMFCProject(   
   oProj,   
   bCWinAppRequired    
);  
```  
  
#### Parameter  
 `oProj`  
 Das ausgewählte Projekt.  
  
 *bCWinAppRequired*  
 Gibt an, ob die Prüfung die Erweiterungs\-DLLs umfasst.  
  
## Rückgabewert  
 **true**, wenn es sich um ein MFC\-Projekt handelt; andernfalls **false**.  
  
## Hinweise  
 Verwenden Sie diese Funktion, um festzustellen, ob es sich bei dem ausgewählten Projekt um ein MFC\-Projekt handelt.  
  
## Beispiel  
  
```  
if (!IsMFCProject(selProj, true))  
   {  
      if (gbExceptionThrown)  
         return false;  
      var L_ErrMsg2_Text = "ATL support can only be added to MFC EXEs or MFC Regular DLLs.";  
      wizard.ReportError(L_ErrMsg2_Text);  
      return false;  
   }  
```  
  
## Siehe auch  
 [Anpassen von C\+\+\-Assistenten mit allgemeinen JScript\-Funktionen](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [JScript\-Funktionen für C\+\+\-Assistenten](../ide/jscript-functions-for-cpp-wizards.md)   
 [Erstellen eines benutzerdefinierten Assistenten](../ide/creating-a-custom-wizard.md)   
 [Entwerfen eines Assistenten](../ide/designing-a-wizard.md)   
 [IsATLProject](../ide/isatlproject.md)   
 [IsAttributedProject](../ide/isattributedproject.md)