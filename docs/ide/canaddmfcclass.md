---
title: "CanAddMFCClass | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CanAddMFCClass"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CanAddMFCClass-Methode"
ms.assetid: 6a97a410-b028-4aad-9b06-04c12cf481eb
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# CanAddMFCClass
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wird vom Assistenten aufgerufen, um zu überprüfen, ob der Benutzer dem Projekt eine MFC\-Klasse hinzufügen kann.  
  
## Syntax  
  
```  
  
      function CanAddMFCClass(   
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
 **true**, wenn die Klasse hinzugefügt werden kann; **false**, wenn der Benutzer die Funktion für ein Projekt aufruft, das kein MFC\-Projekt ist und keine MFC\-Unterstützung besitzt.  
  
## Hinweise  
 Wird vom Assistenten aufgerufen, um zu überprüfen, ob das Projekt mit dem auszuführenden Code\-Assistenten kompatibel ist \(d. h., ob das Projekt eine MFC\-Klasse annehmen kann\).  
  
 Der Assistent ruft diese Funktion auf, wenn die [VSZ\-Datei der Projektsteuerung](../ide/dot-vsz-file-project-control.md) den **PREPROCESS\_FUNCTION**\-Parameter enthält. Er überprüft, ob das [Visual C\+\+\-Codemodell](assetId:///dd6452c2-1054-44a1-b0eb-639a94a1216b) verfügbar ist.  Wenn das Codemodell nicht verfügbar ist, meldet die Funktion einen Fehler und gibt **false** zurück.  
  
## Beispiel  
  
```  
// Determine if an MFC class can be added to the project  
if (CanAddMFCClass(selProj, selObj))  
{  
   return true;  
}  
```  
  
## Siehe auch  
 [Anpassen von C\+\+\-Assistenten mit allgemeinen JScript\-Funktionen](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [JScript\-Funktionen für C\+\+\-Assistenten](../ide/jscript-functions-for-cpp-wizards.md)   
 [Erstellen eines benutzerdefinierten Assistenten](../ide/creating-a-custom-wizard.md)   
 [Entwerfen eines Assistenten](../ide/designing-a-wizard.md)   
 [CanAddClass](../ide/canaddclass.md)   
 [CanAddATLClass](../ide/canaddatlclass.md)   
 [IsMFCProject](../ide/ismfcproject.md)