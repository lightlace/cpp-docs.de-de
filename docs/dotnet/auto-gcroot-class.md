---
title: "auto_gcroot-Klasse"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "msclr::auto_gcroot"
  - "msclr.auto_gcroot"
  - "auto_gcroot"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "auto_gcroot"
ms.assetid: b5790912-265d-463e-a486-47302e91042a
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# auto_gcroot-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Automatische Ressourcenverwaltung \(wie [auto\_ptr\-Klasse](../standard-library/auto-ptr-class.md)\) die verwendet werden kann, um ein virtuelles Handle in einen systemeigenen Typ einbetten.  
  
## Syntax  
  
```  
template<typename _element_type>  
class auto_gcroot;  
```  
  
#### Parameter  
 `_element_type`  
 Der eingebettet werden verwaltete Typ.  
  
## Anforderungen  
 **Headerdatei** \<msclr\\auto\_gcroot.h\>  
  
 **Namespace** msclr  
  
## Siehe auch  
 [auto\_gcroot](../dotnet/auto-gcroot.md)   
 [auto\_gcroot Members](../dotnet/auto-gcroot-members.md)   
 [Gewusst wie: Deklarieren von Handles in systemeigenen Typen](../dotnet/how-to-declare-handles-in-native-types.md)   
 [auto\_handle\-Klasse](../dotnet/auto-handle-class.md)