---
title: "VerifyInterfaceHelper-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::VerifyInterfaceHelper"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VerifyInterfaceHelper-Struktur"
ms.assetid: ea95b641-199a-4fdf-964b-186b40cb3ba7
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# VerifyInterfaceHelper-Struktur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die Infrastruktur von [!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)] und ist nicht für die direkte Verwendung im Code bestimmt.  
  
## Syntax  
  
```  
template <  
   bool isWinRTInterface,  
   typename I  
>  
struct VerifyInterfaceHelper;  
  
template <  
   typename I  
>  
struct VerifyInterfaceHelper<false, I>;  
```  
  
#### Parameter  
 `I`  
 Eine Schnittstelle zu überprüfen.  
  
 `isWinRTInterface`  
  
## Hinweise  
 Überprüft, ob die Schnittstelle, die von dem Vorlagenparameter angegebene, bestimmte Anforderungen erfüllt.  
  
## Member  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[VerifyInterfaceHelper::Verify\-Methode](../windows/verifyinterfacehelper-verify-method.md)||  
  
## Vererbungshierarchie  
 `VerifyInterfaceHelper`  
  
## Anforderungen  
 **Header:** implements.h  
  
 **Namespace:**  Microsoft::WRL::Details  
  
## Siehe auch  
 [Microsoft::WRL::Details\-Namespace](../windows/microsoft-wrl-details-namespace.md)