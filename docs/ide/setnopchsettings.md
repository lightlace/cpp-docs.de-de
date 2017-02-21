---
title: "SetNoPchSettings | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SetNoPchSettings"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetNoPchSettings-Methode"
ms.assetid: 52373c98-ad5e-4e9b-9e0f-9f58ddb2a636
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# SetNoPchSettings
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Richtet die Konfigurationseigenschaften eines Projekts ein, wenn kein vorkompilierter Header verwendet wird.  
  
## Syntax  
  
```  
  
      function SetNoPchSettings(   
   oProj    
);  
```  
  
#### Parameter  
 `oProj`  
 Das ausgewählte Projekt.  
  
## Hinweise  
 Rufen Sie diese Funktion auf, um das Projekt zu konfigurieren, wenn das Projekt keine Einstellungen für vorkompilierte Header verwendet.  
  
## Beispiel  
 Siehe [SetCommonPchSettings](../ide/setcommonpchsettings.md).  
  
## Siehe auch  
 [Anpassen von C\+\+\-Assistenten mit allgemeinen JScript\-Funktionen](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [JScript\-Funktionen für C\+\+\-Assistenten](../ide/jscript-functions-for-cpp-wizards.md)   
 [Erstellen eines benutzerdefinierten Assistenten](../ide/creating-a-custom-wizard.md)   
 [Entwerfen eines Assistenten](../ide/designing-a-wizard.md)   
 [SetCommonPchSettings](../ide/setcommonpchsettings.md)   
 [AddCommonConfig](../ide/addcommonconfig.md)