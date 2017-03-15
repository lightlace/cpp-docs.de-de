---
title: "AddCoclassFromFile | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "AddCoclassFromFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AddCoclassFromFile-Methode"
ms.assetid: a8a211fd-2df3-4361-8137-9c0d999b7f88
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# AddCoclassFromFile
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Rendert eine Vorlagendatei, die eine Co\-Klasse enthält, und fügt sie in die IDL\-Datei des Projekts ein.  
  
## Syntax  
  
```  
  
      function AddCoclassFromFile(   
   oCM,   
   strCoclassFile    
);  
```  
  
#### Parameter  
 `oCM`  
 Das [Visual C\+\+ Code Model](assetId:///dd6452c2-1054-44a1-b0eb-639a94a1216b)\-Objekt.  
  
 *strCoclassFile*  
 Der Name der Vorlagendatei ohne Pfadangabe.  
  
## Hinweise  
 Rufen Sie diese Funktion auf, um eine Vorlagendatei, die eine Co\-Klasse enthält, zu rendern und sie in die IDL\-Datei des Projekts einzufügen.  
  
## Beispiel  
  
```  
// Render myproj.idl and insert into the project's .idl.  
AddCoclassFromFile(oCM, "myproj.idl");  
```  
  
## Siehe auch  
 [Anpassen von C\+\+\-Assistenten mit allgemeinen JScript\-Funktionen](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [JScript\-Funktionen für C\+\+\-Assistenten](../ide/jscript-functions-for-cpp-wizards.md)   
 [Erstellen eines benutzerdefinierten Assistenten](../ide/creating-a-custom-wizard.md)   
 [Entwerfen eines Assistenten](../ide/designing-a-wizard.md)