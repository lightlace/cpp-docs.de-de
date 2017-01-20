---
title: "SetMergeProxySymbol"
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
  - "SetMergeProxySymbol"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetMergeProxySymbol-Methode"
ms.assetid: d6a9db59-2d5b-4431-98bc-785675e0eafe
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# SetMergeProxySymbol
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Diese Funktion wird vom Assistenten aufgerufen, um bei Bedarf das Symbol **\_MERGE\_PROXYSTUB** hinzuzufügen.  
  
## Syntax  
  
```  
  
      function SetMergeProxySymbol(   
   oProj    
);  
```  
  
#### Parameter  
 `oProj`  
 Das ausgewählte Projektobjekt.  
  
## Hinweise  
 Diese Funktion wird vom Assistenten aufgerufen, um bei Bedarf das Symbol **\_MERGE\_PROXYSTUB** hinzuzufügen.  
  
## Beispiel  
  
```  
SetMergeProxySymbol (selproj);  
```  
  
## Siehe auch  
 [Anpassen von C\+\+\-Assistenten mit allgemeinen JScript\-Funktionen](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [JScript\-Funktionen für C\+\+\-Assistenten](../ide/jscript-functions-for-cpp-wizards.md)   
 [Erstellen eines benutzerdefinierten Assistenten](../ide/creating-a-custom-wizard.md)   
 [Entwerfen eines Assistenten](../ide/designing-a-wizard.md)