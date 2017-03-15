---
title: "InterfaceTraits::CastToUnknown-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::InterfaceTraits::CastToUnknown"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CastToUnknown-Methode"
ms.assetid: aca47fa0-3c60-47f2-a73c-258f7160adff
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# InterfaceTraits::CastToUnknown-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL\-Infrastruktur und nicht beabsichtigt, direkt im Code verwendet werden.  
  
## Syntax  
  
```  
template<  
   typename T  
>  
static __forceinline IUnknown* CastToUnknown(  
   _In_ T* ptr  
);  
```  
  
#### Parameter  
 `T`  
 Der Typ des Parameters `ptr`.  
  
 `ptr`  
 Zeiger, um `T` einzugeben.  
  
## Rückgabewert  
 Zeiger auf IUnknown, von denen `Base` abgeleitet wird.  
  
## Hinweise  
 Wandelt den angegebenen Zeiger auf einen Zeiger auf IUnknown um.  
  
 Weitere Informationen zu `Base`, finden Sie den öffentlichen typedef\-Abschnitt in [InterfaceTraits\-Struktur](../windows/interfacetraits-structure.md).  
  
## Anforderungen  
 **Header:** implements.h  
  
 **Namespace:**  Microsoft::WRL::Details  
  
## Siehe auch  
 [InterfaceTraits\-Struktur](../windows/interfacetraits-structure.md)   
 [Microsoft::WRL::Details\-Namespace](../windows/microsoft-wrl-details-namespace.md)