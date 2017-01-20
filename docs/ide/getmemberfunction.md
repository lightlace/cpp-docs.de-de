---
title: "GetMemberfunction"
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
  - "GetMemberFunction"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetMemberfunction-Methode"
ms.assetid: 1e610977-9bc7-4ff2-a79f-132c8e913b4d
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# GetMemberfunction
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Rufen Sie diese Funktion auf, um ein Funktionsobjekt auf der Basis des angegebenen Namens zu erhalten.  
  
## Syntax  
  
```  
  
      function GetMemberfunction(   
   oClass,   
   strFuncName,   
   oProj    
);  
```  
  
#### Parameter  
 *oClass*  
 Das ausgewählte Klassenobjekt.  
  
 `strFuncName`  
 Der abzurufende Funktionsname.  
  
 `oProj`  
 Das ausgewählte Projekt.  
  
## Rückgabewert  
 Die Funktion, die durch `strFuncName` angegeben wird.  
  
## Hinweise  
 Rufen Sie diese Funktion auf, um ein Funktionsobjekt auf der Basis des angegebenen Namens zu erhalten.  Weitere Informationen finden Sie im Visual C\+\+\-Codemodell unter <xref:Microsoft.VisualStudio.VCCodeModel.VCCodeModel.Functions*>.  
  
## Beispiel  
  
```  
// Gets the function ExitInstance from the class CWinApp in the   
// current project.  
var oExitInstance = GetMemberFunction(oCWinApp, "ExitInstance", oProj);  
```  
  
## Siehe auch  
 [Anpassen von C\+\+\-Assistenten mit allgemeinen JScript\-Funktionen](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [JScript\-Funktionen für C\+\+\-Assistenten](../ide/jscript-functions-for-cpp-wizards.md)   
 [Erstellen eines benutzerdefinierten Assistenten](../ide/creating-a-custom-wizard.md)   
 [Entwerfen eines Assistenten](../ide/designing-a-wizard.md)