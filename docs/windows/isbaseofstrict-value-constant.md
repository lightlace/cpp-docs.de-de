---
title: "IsBaseOfStrict::value-Konstante | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "internal/Microsoft::WRL::Details::IsBaseOfStrict::value"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Wertkonstante"
ms.assetid: 4a0cdab0-ba03-482b-babf-eeec519ba687
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# IsBaseOfStrict::value-Konstante
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL\-Infrastruktur und nicht beabsichtigt, direkt im Code verwendet werden.  
  
## Syntax  
  
```  
static const bool value = __is_base_of(Base, Derived);  
```  
  
## Hinweise  
 Gibt an, ob ein Typ Grundlage von anderen ist.  
  
 `value` ist `true`, wenn Typ `Base` eine Basisklasse Typ `Derived` ist; andernfalls ist er `false`.  
  
## Anforderungen  
 **Header:**  internal.h  
  
 **Namespace:**  Microsoft::WRL::Details  
  
## Siehe auch  
 [IsBaseOfStrict\-Struktur](../windows/isbaseofstrict-structure.md)   
 [Microsoft::WRL::Details\-Namespace](../windows/microsoft-wrl-details-namespace.md)