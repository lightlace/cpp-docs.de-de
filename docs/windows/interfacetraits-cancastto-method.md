---
title: "InterfaceTraits::CanCastTo-Methode"
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
  - "implements/Microsoft::WRL::Details::InterfaceTraits::CanCastTo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CanCastTo-Methode"
ms.assetid: 275847cb-69ea-42bf-910f-05ba6ef8b48d
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# InterfaceTraits::CanCastTo-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL\-Infrastruktur und nicht beabsichtigt, direkt im Code verwendet werden.  
  
## Syntax  
  
```  
  
template<typename T>  
static __forceinline bool CanCastTo(  
   _In_ T* ptr,  
   REFIID riid,  
   _Deref_out_ void **ppv  
);  
  
```  
  
#### Parameter  
 `ptr`  
 Der Name eines Zeigers in einen Typ.  
  
 `riid`  
 Die die Schnittstellen\-ID von `Base`.  
  
 `ppv`  
 Wenn dieser Vorgang erfolgreich ist, wird `ppv` auf der Schnittstelle, die von `Base` angegeben wird.  Andernfalls wird `ppv` auf `nullptr` festgelegt.  
  
## Rückgabewert  
 `true`, wenn der Vorgang erfolgreich ist und `ptr` wurde ein Zeiger zu `Base` umgewandelt; andernfalls `false`.  
  
## Hinweise  
 Gibt an, ob der angegebene Zeiger auf Zeiger zu `Base` umgewandelt werden kann.  
  
 Weitere Informationen zu `Base`, finden Sie den öffentlichen typedef\-Abschnitt in [InterfaceTraits\-Struktur](../windows/interfacetraits-structure.md).  
  
## Anforderungen  
 **Header:** implements.h  
  
 **Namespace:**  Microsoft::WRL::Details  
  
## Siehe auch  
 [InterfaceTraits\-Struktur](../windows/interfacetraits-structure.md)   
 [Microsoft::WRL::Details\-Namespace](../windows/microsoft-wrl-details-namespace.md)