---
title: "InterfaceTraits::FillArrayWithIid-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::InterfaceTraits::FillArrayWithIid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "FillArrayWithIid-Methode"
ms.assetid: 73583177-adc9-4fcb-917d-fa7e6d07c990
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# InterfaceTraits::FillArrayWithIid-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL\-Infrastruktur und nicht beabsichtigt, direkt im Code verwendet werden.  
  
## Syntax  
  
```  
__forceinline static void FillArrayWithIid(  
   _Inout_ unsigned long &index,  
   _In_ IID* iids  
);  
  
```  
  
#### Parameter  
 `index`  
 Zeiger auf ein Feld, das einen nullbasierten Indexwert enthält.  
  
 `iids`  
 Ein Array Schnittstellen\-IDs.  
  
## Hinweise  
 Weist die Schnittstellen\-ID von `Base` z Arrayelement zu, das vom Indexargument angegeben wird.  
  
 Umkehrung zum Namen dieser API, nur ein Arrayelement wird geändert; nicht das gesamte Array.  
  
 Weitere Informationen zu `Base`, finden Sie den öffentlichen typedef\-Abschnitt in [InterfaceTraits\-Struktur](../windows/interfacetraits-structure.md).  
  
## Anforderungen  
 **Header:** implements.h  
  
 **Namespace:**  Microsoft::WRL::Details  
  
## Siehe auch  
 [InterfaceTraits\-Struktur](../windows/interfacetraits-structure.md)   
 [Microsoft::WRL::Details\-Namespace](../windows/microsoft-wrl-details-namespace.md)