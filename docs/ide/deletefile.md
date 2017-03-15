---
title: "DeleteFile | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DeleteFile-Methode"
ms.assetid: 0cddaedb-8fad-440e-8f18-677fdff94a63
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# DeleteFile
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Löscht die angegebene Datei.  
  
## Syntax  
  
```  
  
      function DeleteFile(   
   oFSO,   
   strFile    
)   
```  
  
#### Parameter  
 *oFSO*  
 Das Dateisystemobjekt.  
  
 `strFile`  
 Der Name der zu löschenden Datei.  
  
## Hinweise  
 Rufen Sie diese Funktion auf, um die angegebene Datei zu löschen.  
  
## Beispiel  
  
```  
// Declare a temporary file.  
var strFile = strTempFolder + "\\" + strTarget;  
var strClassName = strTarget.split(".");  
wizard.AddSymbol("SAFE_CLASS_NAME", strClassName[0]);  
wizard.AddSymbol("SAFE_ITEM_NAME", strClassName[0]);  
  
// Declare the template name.  
var strTemplate = strTemplatePath + "\\" + strTpl;  
  
// Render and insert the template.  
wizard.RenderTemplate(strTemplate, strFile, bCopyOnly);  
  
// Create a new project file and add the file from the template.  
var projfile = projItems.AddFromTemplate(strFile, strTarget);  
  
// Delete the temporary file from the file structure object.  
DeleteFile(fso, strFile);  
```  
  
## Siehe auch  
 [Anpassen von C\+\+\-Assistenten mit allgemeinen JScript\-Funktionen](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [JScript\-Funktionen für C\+\+\-Assistenten](../ide/jscript-functions-for-cpp-wizards.md)   
 [Erstellen eines benutzerdefinierten Assistenten](../ide/creating-a-custom-wizard.md)   
 [Entwerfen eines Assistenten](../ide/designing-a-wizard.md)