---
title: "CanAddATLClass | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CanAddATLClass"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CanAddATLClass-Methode"
ms.assetid: 7a8abf90-c1b8-475c-af22-7948478084f9
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# CanAddATLClass
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wird vom Assistenten aufgerufen, um zu überprüfen, ob der Benutzer dem Projekt eine ATL\-Klasse hinzufügen kann.  
  
## Syntax  
  
```  
  
      function CanAddATLClass(   
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
 **true**, wenn die Klasse hinzugefügt werden kann; **false**, wenn der Benutzer die Funktion für ein Projekt aufruft, das kein ATL\-Projekt ist und keine ATL\-Unterstützung besitzt.  
  
## Hinweise  
 Wird vom Assistenten aufgerufen, um zu überprüfen, ob das Projekt mit dem auszuführenden Code\-Assistenten kompatibel ist \(d. h., ob das Projekt eine ATL\-Klasse annehmen kann\).  
  
 Der Assistent ruft diese Funktion auf, wenn die [VSZ\-Datei der Projektsteuerung](../ide/dot-vsz-file-project-control.md) den **PREPROCESS\_FUNCTION**\-Parameter enthält. Er überprüft, ob das [Visual C\+\+\-Codemodell](assetId:///dd6452c2-1054-44a1-b0eb-639a94a1216b) verfügbar ist.  Wenn das Codemodell nicht verfügbar ist, meldet die Funktion einen Fehler und gibt **false** zurück.  
  
## Beispiel  
  
```  
// Determine if an ATL class can be added to the project  
if (CanAddATLClass(selProj, selObj))  
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
 [IsMFCProject](../ide/ismfcproject.md)   
 [CanAddMFCClass](../ide/canaddmfcclass.md)