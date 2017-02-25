---
title: "RuntimeClassBaseT::AsIID-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::RuntimeClassBaseT::AsIID"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AsIID-Methode"
ms.assetid: 90d7df8a-cf9e-4eef-8837-bc1a25f3fa1a
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
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