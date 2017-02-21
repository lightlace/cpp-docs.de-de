---
title: "InterfaceTraits::CastToBase-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::InterfaceTraits::CastToBase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CastToBase-Methode"
ms.assetid: 0591a017-0adf-4358-b946-eb0a307ce7f2
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# InterfaceTraits::CastToBase-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL\-Infrastruktur und nicht beabsichtigt, direkt im Code verwendet werden.  
  
## Syntax  
  
```  
template<  
   typename T  
>  
static __forceinline Base* CastToBase(  
   _In_ T* ptr  
);  
```  
  
#### Parameter  
 `T`  
 Der Typ des Parameters `ptr`.  
  
 `ptr`  
 Zeiger auf einen Typ `T`.  
  
## Rückgabewert  
 Ein Zeiger auf `Base`.  
  
## Hinweise  
 Wandelt den angegebenen Zeiger auf Zeiger in `Base` um.  
  
 Weitere Informationen zu `Base`, finden Sie den öffentlichen typedef\-Abschnitt in [InterfaceTraits\-Struktur](../windows/interfacetraits-structure.md).  
  
## Anforderungen  
 **Header:** implements.h  
  
 **Namespace:**  Microsoft::WRL::Details  
  
## Siehe auch  
 [InterfaceTraits\-Struktur](../windows/interfacetraits-structure.md)   
 [Microsoft::WRL::Details\-Namespace](../windows/microsoft-wrl-details-namespace.md)