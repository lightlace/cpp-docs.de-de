---
title: "InsertIntoFunction"
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
  - "InsertIntoFunction"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "InsertIntoFunction-Methode"
ms.assetid: 50500c3c-bee3-4a9c-a403-7dcd752de23c
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# InsertIntoFunction
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wird von [AddATLSupportToProject](../ide/addatlsupporttoproject.md) verwendet, um Code in [InitInstance](../Topic/CWinApp::InitInstance.md) einzufügen.  
  
## Syntax  
  
```  
  
      function InsertIntoFunction(   
   oFunction,   
   strSearchString,   
   nStartLine,   
   nEndLine,   
   bInsideIfBlock    
);  
```  
  
#### Parameter  
 *oFunction*  
 Das Funktionsobjekt, in das Code eingefügt wird.  
  
 `strSearchString`  
 Die Suchzeichenfolge, mit die der Einfügemarke bestimmt wird.  
  
 *nStartLine*  
 Die Startzeile, die an [GetCodeForInitInstance](../ide/getcodeforinitinstance.md) übergeben werden soll.  
  
 *nEndLine*  
 Die Endzeile, die an [GetCodeForInitInstance](../ide/getcodeforinitinstance.md) übergeben werden soll.  
  
 *bInsideIfBlock*  
 Gibt an, ob eine Einfügung in einen Funktionsblock erfolgt.  
  
## Rückgabewert  
 **true** bei erfolgreicher Einfügung; andernfalls **false**.  
  
## Siehe auch  
 [Anpassen von C\+\+\-Assistenten mit allgemeinen JScript\-Funktionen](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [JScript\-Funktionen für C\+\+\-Assistenten](../ide/jscript-functions-for-cpp-wizards.md)   
 [Erstellen eines benutzerdefinierten Assistenten](../ide/creating-a-custom-wizard.md)   
 [Entwerfen eines Assistenten](../ide/designing-a-wizard.md)   
 [GetMemberfunction](../ide/getmemberfunction.md)