---
title: "CreateSafeName"
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
  - "CreateSafeName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateSafeName-Methode"
ms.assetid: 3a0dd4af-776d-4c25-aff9-4c539f173cb8
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# CreateSafeName
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Generiert einen C\+\+\-Anzeigenamen.  
  
## Syntax  
  
```  
  
      function CreateSafeName(   
   strName    
);  
```  
  
#### Parameter  
 `strName`  
 Der alte Name.  
  
## Rückgabewert  
 Der neue, sichere Name.  
  
## Hinweise  
 Rufen Sie diese Funktion auf, um aus einem Namen, der in C\+\+ nicht zulässige Zeichen enthält, einen zulässigen C\+\+\-Anzeigenamen zu erstellen.  Ein zulässiger C\+\+\-Name darf Klein\- oder Großbuchstaben, Zahlen oder einen Unterstrich \("\_"\) enthalten.  
  
 Diese Funktion überprüft alle Zeichen des alten Namens und überspringt unzulässige Zeichen.  Wenn der alte Name keine zulässigen Zeichen enthält, gibt die Funktion den neuen Namen als "My" zurück.  Wenn der neue Anzeigename mit einer Zahl beginnt, stellt die Funktion dem neuen Namen die Zeichenfolge "My" voran.  
  
## Beispiel  
  
```  
// Get the project name  
var strProjectName = wizard.FindSymbol("PROJECT_NAME");  
  
// Set the project name to the safe project name.   
var strSafeProjectName = CreateSafeName(strProjectName);  
```  
  
## Siehe auch  
 [Anpassen von C\+\+\-Assistenten mit allgemeinen JScript\-Funktionen](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [JScript\-Funktionen für C\+\+\-Assistenten](../ide/jscript-functions-for-cpp-wizards.md)   
 [Erstellen eines benutzerdefinierten Assistenten](../ide/creating-a-custom-wizard.md)   
 [Entwerfen eines Assistenten](../ide/designing-a-wizard.md)