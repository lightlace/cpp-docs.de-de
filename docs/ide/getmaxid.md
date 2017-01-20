---
title: "GetMaxID"
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
  - "GetMaxID"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetMaxID-Methode"
ms.assetid: a155ec2e-6132-4e40-9b85-d710538778a1
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# GetMaxID
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ermittelt die höchste `dispid` der Member dieser Schnittstelle und aller zugehörigen Basisschnittstellen.  
  
## Syntax  
  
```  
  
      function GetMaxID(   
   ointerface    
);  
```  
  
#### Parameter  
 *ointerface*  
 Ein <xref:Microsoft.VisualStudio.VCCodeModel.VCCodeInterface>\-Objekt.  
  
## Rückgabewert  
 Die höchste `dispid` der Member von *oInterface* und aller zugehörigen Basisschnittstellen.  
  
## Hinweise  
 Rufen Sie diese Funktion auf, um die höchste dispid der Member der angegebenen Schnittstelle sowie aller zugehörigen Basisschnittstellen zu ermitteln.  
  
## Beispiel  
  
```  
if (strInterfaceType == "custom")  
      window.external.AddSymbol("DISPID_DISABLED", true);  
   else  
   {  
      var nDispID = window.external.FindSymbol("DISPID");  
      if (!nDispID.length)  
      {  
         nDispID = GetMaxID(oInterface) + 1;  
         window.external.AddSymbol("DISPID", nDispID);  
      }  
   }  
```  
  
## Siehe auch  
 [Anpassen von C\+\+\-Assistenten mit allgemeinen JScript\-Funktionen](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [JScript\-Funktionen für C\+\+\-Assistenten](../ide/jscript-functions-for-cpp-wizards.md)   
 [Erstellen eines benutzerdefinierten Assistenten](../ide/creating-a-custom-wizard.md)   
 [Entwerfen eines Assistenten](../ide/designing-a-wizard.md)