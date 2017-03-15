---
title: "AddATLSupportToProject | Microsoft Docs"
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
  - "AddATLSupportToProject-Methode"
ms.assetid: 26708f22-1e9b-4432-83b2-ed94c765b753
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# AddATLSupportToProject
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Fügt einem MFC\-Projekt ATL\-Unterstützung hinzu.  
  
## Syntax  
  
```  
  
      function AddATLSupportToProject(   
   oProj   
);  
```  
  
#### Parameter  
 `oProj`  
 Das ausgewählte Projekt.  
  
## Rückgabewert  
 **true**, wenn dem MFC\-Projekt die ATL\-Unterstützung erfolgreich hinzugefügt wurde.  
  
## Hinweise  
 Verwenden Sie diese Funktion, um einem MFC\-Projekt, das vom Assistenten erstellt wurde, ATL\-Unterstützung hinzuzufügen.  
  
 Um zu bestätigen, dass dem MFC\-Projekt ATL\-Unterstützung hinzugefügt wird, zeigt der Assistent ein Meldungsfeld an.  Nach der Bestätigung überprüft der Assistent die vorhandene Unterstützung und fügt alle erforderlichen GUIDs, Vorlagen, Header und Zusatzfunktionen hinzu, sodass das vom Assistenten erstellte MFC\-Projekt ATL unterstützt.  
  
## Beispiel  
  
```  
var oCM = selProj.CodeModel;  
var L_TRANSACTION_Text = "Add ATL Support To Project";  
oCM.StartTransaction(L_TRANSACTION_Text);  
var bRet = AddATLSupportToProject(selProj);  
if (bRet)  
   oCM.CommitTransaction();  
else  
   oCM.AbortTransaction();  
return bRet;  
```  
  
## Siehe auch  
 [Anpassen von C\+\+\-Assistenten mit allgemeinen JScript\-Funktionen](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [Erstellen eines benutzerdefinierten Assistenten](../ide/creating-a-custom-wizard.md)   
 [Entwerfen eines Assistenten](../ide/designing-a-wizard.md)   
 [CanAddATLClass](../ide/canaddatlclass.md)   
 [IsMFCProject](../ide/ismfcproject.md)   
 [Einführung in ATL](../atl/introduction-to-atl.md)