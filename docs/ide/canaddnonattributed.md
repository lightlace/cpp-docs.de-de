---
title: "CanAddNonAttributed | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CanAddNonAttributed"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CanAddNonAttributed-Methode"
ms.assetid: a2b0143e-f84b-40f3-8f51-23a492f651f8
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# CanAddNonAttributed
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Zeigt an, dass das ATL\-Projekt nicht attributierte Objekte unterstützt.  
  
## Syntax  
  
```  
  
function CanAddNonAttributed( );  
  
```  
  
## Rückgabewert  
 **true**, wenn das Projekt attributierte und nicht attributierte ATL\-Objekte unterstützt; **false**, wenn das Projekt nur attributierte Projekte unterstützt.  
  
## Hinweise  
 Rufen Sie diese Funktion auf, um festzustellen, ob das Projekt sowohl attributierte als auch nicht attributierte Objekte unterstützt.  
  
## Beispiel  
  
```  
// Check if attributed project using CanAddNonAttributed  
window.external.Load(document);  
if (IsAttributedProject(window.external))  
{  
   ATTRIBUTED.checked = true;  
   if (!CanAddNonAttributed())  
      ATTRIBUTED.disabled = true;  
}  
```  
  
## Siehe auch  
 [Anpassen von C\+\+\-Assistenten mit allgemeinen JScript\-Funktionen](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [JScript\-Funktionen für C\+\+\-Assistenten](../ide/jscript-functions-for-cpp-wizards.md)   
 [Erstellen eines benutzerdefinierten Assistenten](../ide/creating-a-custom-wizard.md)   
 [Entwerfen eines Assistenten](../ide/designing-a-wizard.md)   
 [Concepts](../windows/attributed-programming-concepts.md)   
 [CanAddClass](../ide/canaddclass.md)