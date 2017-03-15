---
title: "CanAddClass | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CanAddClass"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CanAddClass-Methode"
ms.assetid: 76739742-1e34-470c-910d-8784f0adfbf0
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# CanAddClass
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wird vom Assistenten aufgerufen, um zu überprüfen, ob das Projekt mit dem Code\-Assistenten kompatibel ist, den der Benutzer ausführen möchte.  
  
## Syntax  
  
```  
  
      function CanAddClass(   
   oProj,   
   oObject    
);  
```  
  
#### Parameter  
 `oProj`  
 Das ausgewählte Projekt.  
  
 `oObject`  
 Das ausgewählte Objekt.  In diesem Fall das aktuelle Projekt.  
  
## Rückgabewert  
 **true**, wenn die Klasse hinzugefügt werden kann, andernfalls **false**.  
  
## Hinweise  
 Der Assistent ruft diese Funktion auf, wenn die [VSZ\-Datei der Projektsteuerung](../ide/dot-vsz-file-project-control.md) den **PREPROCESS\_FUNCTION**\-Parameter enthält.  
  
 Er überprüft, ob das [Visual C\+\+\-Codemodellobjekt](assetId:///dd6452c2-1054-44a1-b0eb-639a94a1216b) verfügbar ist.  Wenn das Codemodell nicht verfügbar ist, meldet die Funktion einen Fehler und gibt **false** zurück.  
  
## Beispiel  
  
```  
// Determine if a class can be added to the project  
if (CanAddClass(selProj, selObj))  
{  
   return true;  
}  
```  
  
## Siehe auch  
 [Anpassen von C\+\+\-Assistenten mit allgemeinen JScript\-Funktionen](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [JScript\-Funktionen für C\+\+\-Assistenten](../ide/jscript-functions-for-cpp-wizards.md)   
 [Erstellen eines benutzerdefinierten Assistenten](../ide/creating-a-custom-wizard.md)   
 [Entwerfen eines Assistenten](../ide/designing-a-wizard.md)   
 [CanAddMFCClass](../ide/canaddmfcclass.md)   
 [CanAddATLClass](../ide/canaddatlclass.md)   
 [IsMFCProject](../ide/ismfcproject.md)