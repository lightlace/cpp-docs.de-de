---
title: "ImplementsHelper::FillArrayWithIid-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::ImplementsHelper::FillArrayWithIid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "FillArrayWithIid-Methode"
ms.assetid: f60035ee-b7d6-4a08-966d-f88c646944c3
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ImplementsHelper::FillArrayWithIid-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL\-Infrastruktur und nicht beabsichtigt, direkt im Code verwendet werden.  
  
## Syntax  
  
```  
void FillArrayWithIid(  
   _Inout_ unsigned long *index,   
   _Inout_ IID* iids) throw();  
```  
  
#### Parameter  
 `index`  
 Ein nullbasierter Index, der den Ausgangsbedingungen Arrayelement für diesen Vorgang angibt.  Wenn dieser Vorgang abgeschlossen ist, wird `index` durch. 1 erhöht.  
  
 `iids`  
 Ein Array Typ IID.  
  
## Hinweise  
 Fügt die Schnittstellen\-ID ein, die durch den aktuellen zeroth Vorlagenparameter in das angegebene Arrayelement angegeben wird.  
  
## Anforderungen  
 **Header:** implements.h  
  
 **Namespace:**  Microsoft::WRL::Details  
  
## Siehe auch  
 [ImplementsHelper\-Struktur](../windows/implementshelper-structure.md)   
 [Microsoft::WRL::Details\-Namespace](../windows/microsoft-wrl-details-namespace.md)