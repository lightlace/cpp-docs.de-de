---
title: "IsSame::value-Konstante | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "internal/Microsoft::WRL::Details::IsSame::value"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Wertkonstante"
ms.assetid: ee72deff-54a2-4482-9967-49a86d07f834
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# IsSame::value-Konstante
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL\-Infrastruktur und nicht beabsichtigt, direkt im Code verwendet werden.  
  
## Syntax  
  
```  
template <typename T1, typename T2>  
    struct IsSame  
    {  
        static const bool value = false;  
    };  
  
    template <typename T1>  
    struct IsSame<T1, T1>  
    {  
        static const bool value = true;  
    };  
  
```  
  
## Hinweise  
 Gibt an, ob ein Typ der gleiche wie andere.  
  
 `value` ist **true**, wenn die Vorlagenparameter identisch sind, und **false**, wenn die Vorlagenparameter unterschiedlich sind.  
  
## Anforderungen  
 **Header:**  internal.h  
  
 **Namespace:**  Microsoft::WRL::Details  
  
## Siehe auch  
 [IsSame\-Struktur](../windows/issame-structure.md)   
 [Microsoft::WRL::Details\-Namespace](../windows/microsoft-wrl-details-namespace.md)