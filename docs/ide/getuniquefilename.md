---
title: "GetUniqueFileName"
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
  - "GetUniqueFileName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetUniqueFilename-Methode"
ms.assetid: f9760e1a-82d0-4d8b-b00a-6f4c36f6b2c6
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# GetUniqueFileName
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt einen eindeutigen Dateinamen zurück.  
  
## Syntax  
  
```  
  
      function GetUniqueFileName(   
   strDirectory,   
   strFileName    
);  
```  
  
#### Parameter  
 *strDirectory*  
 Verzeichnis, in dem nach dem Dateinamen gesucht werden soll.  
  
 `strFileName`  
 Der zu suchende Dateiname.  
  
## Rückgabewert  
 Der durch `strFileName` angegebene Dateiname, sofern eindeutig; andernfalls gibt diese Funktion `strFileName` mit einer angehängten Zahl zwischen 1 und 9999999 zurück, um den Namen eindeutig zu kennzeichnen.  Wenn `strFileName` nicht angegeben ist, gibt diese Funktion mithilfe der [GetTempName\-Methode](jsmthGetTempName) einen eindeutigen Dateinamen zurück.  
  
## Hinweise  
 Gibt einen eindeutigen Dateinamen zurück.  
  
## Siehe auch  
 [Anpassen von C\+\+\-Assistenten mit allgemeinen JScript\-Funktionen](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [JScript\-Funktionen für C\+\+\-Assistenten](../ide/jscript-functions-for-cpp-wizards.md)   
 [Erstellen eines benutzerdefinierten Assistenten](../ide/creating-a-custom-wizard.md)   
 [Entwerfen eines Assistenten](../ide/designing-a-wizard.md)   
 [GetProjectFile](../ide/getprojectfile.md)