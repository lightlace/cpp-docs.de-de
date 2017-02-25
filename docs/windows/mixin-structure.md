---
title: "MixIn-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::MixIn"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MixIn-Struktur"
ms.assetid: 47e2df9b-3a2e-4ae8-8ba3-b1fd3aa73566
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# MixIn-Struktur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Stellt sicher, dass einer Laufzeitklasse von [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]\-Schnittstellen, wenn überhaupt und dann von den klassischen COM\-Schnittstellen abgeleitet.  
  
## Syntax  
  
```  
template<  
   typename Derived,  
   typename MixInType,  
   bool hasImplements = __is_base_of(Details::ImplementsBase,  
   MixInType)  
>  
struct MixIn;  
```  
  
#### Parameter  
 `Derived`  
 Ein Typ ist von [Implementiert](../windows/implements-structure.md) der Struktur.  
  
 `MixInType`  
 Ein Basistyp.  
  
 `hasImplements`  
 `true`, wenn `MixInType` aus der aktuellen Implementierung der Basistyp abgeleitet wird; andernfalls `false`.  
  
## Hinweise  
 Wenn eine Klasse von [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] als auch von Klasse COM\-Schnittstellen abgeleitet ist, muss die Klassendeklarationsliste alle [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]\-Schnittstellen und anschließend eine klassischen COM\-Schnittstellen zuerst aufzeigen.  MixIn gewährleistet, dass Schnittstellen in der richtigen Reihenfolge angegeben werden.  
  
## Vererbungshierarchie  
 `MixIn`  
  
## Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [Microsoft::WRL\-Namespace](../windows/microsoft-wrl-namespace.md)