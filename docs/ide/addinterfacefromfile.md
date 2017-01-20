---
title: "AddInterfaceFromFile"
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
  - "AddInterfaceFromFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AddInterfaceFromFile-Methode"
ms.assetid: fa848690-ad98-4fb4-bbcf-dffcaad05df2
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# AddInterfaceFromFile
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Rendert eine Vorlagendatei, die eine Schnittstelle enthält, und fügt sie hinzu.  
  
## Syntax  
  
```  
  
      function AddInterfaceFromFile(   
   oCM,   
   strInterfaceFile    
);  
```  
  
#### Parameter  
 `oCM`  
 Das [Visual C\+\+ Code Model](assetId:///dd6452c2-1054-44a1-b0eb-639a94a1216b)\-Objekt.  
  
 *strInterfaceFile*  
 Der Name der Vorlagendatei ohne Pfadangabe.  
  
## Hinweise  
 Rufen Sie diese Funktion auf, um eine Vorlagendatei, die eine Schnittstelle enthält, zu rendern und sie in die IDL\-Datei des Projekts einzufügen.  
  
 Wenn das Einfügen der Schnittstelle fehlschlägt, gibt diese Funktion eine Fehlermeldung aus.  
  
## Beispiel  
  
```  
// Render myint.idl and insert into strProject.idl  
AddInterfaceFromFile(oCM, "myint.idl");  
```  
  
## Siehe auch  
 [Anpassen von C\+\+\-Assistenten mit allgemeinen JScript\-Funktionen](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [JScript\-Funktionen für C\+\+\-Assistenten](../ide/jscript-functions-for-cpp-wizards.md)   
 [Erstellen eines benutzerdefinierten Assistenten](../ide/creating-a-custom-wizard.md)   
 [Entwerfen eines Assistenten](../ide/designing-a-wizard.md)