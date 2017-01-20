---
title: "GetInterfaceType"
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
  - "GetInterfaceType"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetInterfaceType-Methode"
ms.assetid: cc6403a8-0c2b-47f7-a8f7-9db95df87d5a
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# GetInterfaceType
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ruft den Typ der Schnittstelle ab.  
  
## Syntax  
  
```  
  
      function GetInterfaceType(   
   oInterface    
);  
```  
  
#### Parameter  
 *oInterface*  
 Ein <xref:Microsoft.VisualStudio.VCCodeModel.VCCodeInterface>\-Objekt.  
  
## Rückgabewert  
 Die Zeichenfolge, die den Schnittstellentyp \(z. B. **custom**, **dual**, **dispinterface** oder **oleautomation**\) kennzeichnet.  
  
## Hinweise  
 Rufen Sie diese Funktion auf, um den Schnittstellentyp zu ermitteln.  
  
## Beispiel  
 Siehe [GetMaxID](../ide/getmaxid.md).  
  
## Siehe auch  
 [Anpassen von C\+\+\-Assistenten mit allgemeinen JScript\-Funktionen](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [JScript\-Funktionen für C\+\+\-Assistenten](../ide/jscript-functions-for-cpp-wizards.md)   
 [Erstellen eines benutzerdefinierten Assistenten](../ide/creating-a-custom-wizard.md)   
 [Entwerfen eines Assistenten](../ide/designing-a-wizard.md)   
 [GetInterfaceClasses](../ide/getinterfaceclasses.md)