---
title: "Gewusst wie: Hinzuf&#252;gen einer systemeigenen DLL zum globalen Assemblycache"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DLLs [C++], Systemeigen"
  - "GAC (Globaler Assembly-Cache), Laden von systemeigenen DLLs"
  - "Systemeigene DLLs [C++]"
ms.assetid: 25e8d78a-b197-4269-b4e9-237a544ab3c8
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Hinzuf&#252;gen einer systemeigenen DLL zum globalen Assemblycache
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie können eine systemeigene DLL \(nicht COM\) im globalen Assemblycache ablegen.  
  
## Beispiel  
 Mit **\/ASSEMBLYLINKRESOURCE** können Sie eine systemeigene DLL in eine Assembly einbetten.  
  
 Weitere Informationen finden Sie unter [\/ASSEMBLYLINKRESOURCE \(Mit .NET Framework\-Ressource verknüpfen\)](../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md).  
  
```  
/ASSEMBLYLINKRESOURCE:MyComponent.dll  
```  
  
## Siehe auch  
 [Verwenden von C\+\+\-Interop \(implizites PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)