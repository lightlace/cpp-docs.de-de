---
title: "GetInterfaceClasses"
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
  - "GetInterfaceClasses"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetInterfaceClasses-Methode"
ms.assetid: 712c112f-b4ff-43c4-ad49-c4f4c13c48bd
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# GetInterfaceClasses
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt das einer Schnittstelle zugehörige `VCCodeClass`\-Objekt zurück.  
  
## Syntax  
  
```  
  
      function GetInterfaceClasses(   
   strInterface,   
   oProject,   
   aryClasses    
);  
```  
  
#### Parameter  
 *strInterface*  
 Der Name der Schnittstelle, die die Klassenobjekte enthält.  
  
 *oProject*  
 Das ausgewählte Projekt.  
  
 *aryClasses*  
 \[out\] Ein Array von Klassenobjekten in der Schnittstelle.  
  
## Rückgabewert  
 Das <xref:Microsoft.VisualStudio.VCCodeModel.VCCodeClass>\-Objekt, das einer Schnittstelle zugeordnet ist.  
  
## Hinweise  
 Rufen Sie diese Funktion auf, um die mit einer Schnittstelle verknüpften Klassen abzurufen.  
  
## Beispiel  
  
```  
var aryClasses = new Array();  
GetInterfaceClasses(oInterface.Name, selProj, aryClasses);  
```  
  
## Siehe auch  
 [Anpassen von C\+\+\-Assistenten mit allgemeinen JScript\-Funktionen](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [JScript\-Funktionen für C\+\+\-Assistenten](../ide/jscript-functions-for-cpp-wizards.md)   
 [Erstellen eines benutzerdefinierten Assistenten](../ide/creating-a-custom-wizard.md)   
 [Entwerfen eines Assistenten](../ide/designing-a-wizard.md)   
 [GetInterfaceType](../ide/getinterfacetype.md)