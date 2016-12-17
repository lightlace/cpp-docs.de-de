---
title: "SetErrorInfo"
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
  - "SetErrorInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetErrorInfo-Methode"
ms.assetid: 78bca763-3f90-4e04-b566-b4b7fe2431b1
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# SetErrorInfo
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wird von [OnWizFinish](../ide/onwizfinish.md) und [CanUseFileName](../ide/canusefilename.md) aufgerufen, um Informationen zum aktuellen Fehler zu erhalten.  
  
## Syntax  
  
```  
  
      function SetErrorInfo(   
   oErrorObj   
);  
```  
  
#### Parameter  
 *oErrorObj*  
 Das Fehlerobjekt.  
  
## Hinweise  
 Wird von [OnWizFinish](../ide/onwizfinish.md) und [CanUseFileName](../ide/canusefilename.md) aufgerufen, um Informationen zum aktuellen Fehler zu erhalten.  Weitere Informationen finden Sie im Visual C\+\+\-Assistenten\-Modell unter <xref:Microsoft.VisualStudio.VsWizard.VCWizCtlClass.SetErrorInfo*>.  
  
## Siehe auch  
 [Anpassen von C\+\+\-Assistenten mit allgemeinen JScript\-Funktionen](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [JScript\-Funktionen für C\+\+\-Assistenten](../ide/jscript-functions-for-cpp-wizards.md)   
 [Erstellen eines benutzerdefinierten Assistenten](../ide/creating-a-custom-wizard.md)   
 [Entwerfen eines Assistenten](../ide/designing-a-wizard.md)