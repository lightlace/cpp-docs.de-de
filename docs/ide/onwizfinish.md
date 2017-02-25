---
title: "OnWizFinish | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "OnWizFinish"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OnWizFinish-Methode"
ms.assetid: 5e0790c3-c5b4-43de-b9db-b18d07c19f41
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# OnWizFinish
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wird vom HTML\-Skript des Assistenten aufgerufen, wenn der Benutzer auf **Fertig stellen** klickt.  Diese Funktion ruft ihrerseits die **Finish**\-Funktion der Assistentensteuerung auf.  
  
## Syntax  
  
```  
  
      function OnWizFinish(   
   document    
);  
```  
  
#### Parameter  
 `document`  
 Das HTML\-Dokumentobjekt.  
  
## Hinweise  
 Diese Funktion wird vom HTML\-Skript des Assistenten aufgerufen, wenn der Benutzer auf **Fertig stellen** klickt.  
  
## Siehe auch  
 [Anpassen von C\+\+\-Assistenten mit allgemeinen JScript\-Funktionen](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [JScript\-Funktionen für C\+\+\-Assistenten](../ide/jscript-functions-for-cpp-wizards.md)   
 [Erstellen eines benutzerdefinierten Assistenten](../ide/creating-a-custom-wizard.md)   
 [Entwerfen eines Assistenten](../ide/designing-a-wizard.md)