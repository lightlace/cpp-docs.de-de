---
title: "BoolStruct-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "internal/Microsoft::WRL::Details::BoolStruct"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BoolStruct-Struktur"
ms.assetid: 666eae78-e81d-4fb7-a9e4-1ba617d6d4cd
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# BoolStruct-Struktur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL\-Infrastruktur und nicht beabsichtigt, direkt im Code verwendet werden.  
  
## Syntax  
  
```  
struct BoolStruct;  
```  
  
## Hinweise  
 Die BoolStruct\-Struktur definiert, ob ein ComPtr die Objektlebensdauer einer Schnittstelle verwaltet.  BoolStruct wird intern vom Operator [BoolType\(\)](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md) verwendet.  
  
## Member  
  
### Öffentliche Datenmember  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[BoolStruct::Member\-Datenmember](../windows/boolstruct-member-data-member.md)|Gibt an, dass, [ComPtr](../windows/comptr-class.md) ist, oder nicht und verwaltet die Objektlebensdauer einer Schnittstelle.|  
  
## Vererbungshierarchie  
 `BoolStruct`  
  
## Anforderungen  
 **Header:**  internal.h  
  
 **Namespace:**  Microsoft::WRL::Details  
  
## Siehe auch  
 [Microsoft::WRL::Details\-Namespace](../windows/microsoft-wrl-details-namespace.md)   
 [ComPtr::operator Microsoft::WRL::Details::BoolType\-Operator](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md)