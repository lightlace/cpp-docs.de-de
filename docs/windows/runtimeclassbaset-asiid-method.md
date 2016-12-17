---
title: "RuntimeClassBaseT::AsIID-Methode"
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
  - "implements/Microsoft::WRL::Details::RuntimeClassBaseT::AsIID"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AsIID-Methode"
ms.assetid: 90d7df8a-cf9e-4eef-8837-bc1a25f3fa1a
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# RuntimeClassBaseT::AsIID-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL\-Infrastruktur und nicht beabsichtigt, direkt im Code verwendet werden.  
  
## Syntax  
  
```  
template<  
   typename T  
>  
__forceinline static HRESULT AsIID(  
   _In_ T* implements,  
   REFIID riid,  
   _Deref_out_ void **ppvObject  
);  
```  
  
#### Parameter  
 `T`  
 Ein Typ, der die Schnittstellen\-ID implementiert, wurde durch Parameter `riid` an.  
  
 `implements`  
 Eine Variable des Typs angegeben durch Vorlagenparameter `T`.  
  
 `riid`  
 Die die Schnittstellen\-ID abzurufen.  
  
 `ppvObject`  
 Wenn dieser Vorgang erfolgreich ist, hat ein Zeiger\-zu\-einZeiger zur Schnittstelle durch Parameter `riid` an.  
  
## Rückgabewert  
 S\_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler beschreibt.  
  
## Hinweise  
 Ruft einen Zeiger der angegebenen ID Schnittstelle ab  
  
## Anforderungen  
 **Header:** implements.h  
  
 **Namespace:**  Microsoft::WRL::Details  
  
## Siehe auch  
 [RuntimeClassBaseT\-Struktur](../windows/runtimeclassbaset-structure.md)   
 [Microsoft::WRL::Details\-Namespace](../windows/microsoft-wrl-details-namespace.md)