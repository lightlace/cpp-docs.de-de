---
title: "VerifyInheritanceHelper::Verify-Methode"
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
  - "implements/Microsoft::WRL::Details::VerifyInheritanceHelper::Verify"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Verify-Methode"
ms.assetid: 3360082b-81ad-4191-9ec3-b4372f7207d7
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# VerifyInheritanceHelper::Verify-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL\-Infrastruktur und nicht beabsichtigt, direkt im Code verwendet werden.  
  
## Syntax  
  
```  
static void Verify();  
```  
  
## Hinweise  
 Testet die beiden Schnittstellen, die von der aktuellen Vorlagenparameter angegeben werden und bestimmt, ob eine Schnittstelle von anderen abgeleitet wird.  
  
 Ein Fehler wird ausgegeben, wenn eine Schnittstelle nicht aus der anderen abgeleitet wird.  
  
## Anforderungen  
 **Header:** implements.h  
  
 **Namespace:**  Microsoft::WRL::Details  
  
## Siehe auch  
 [VerifyInheritanceHelper\-Struktur](../windows/verifyinheritancehelper-structure.md)   
 [Microsoft::WRL::Details\-Namespace](../windows/microsoft-wrl-details-namespace.md)