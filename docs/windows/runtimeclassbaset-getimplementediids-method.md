---
title: "RuntimeClassBaseT::GetImplementedIIDS-Methode"
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
  - "implements/Microsoft::WRL::Details::RuntimeClassBaseT::GetImplementedIIDS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetImplementedIIDS-Methode"
ms.assetid: adae54da-521d-4add-87f5-242fbd85f33b
caps.latest.revision: 4
caps.handback.revision: "4"
ms.author: "mblome"
manager: "ghogen"
---
# RuntimeClassBaseT::GetImplementedIIDS-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL\-Infrastruktur und nicht beabsichtigt, direkt im Code verwendet werden.  
  
## Syntax  
  
```  
template<  
   typename T  
>  
__forceinline static HRESULT GetImplementedIIDS(  
   _In_ T* implements,  
   _Out_ ULONG *iidCount,  
   _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids  
);  
```  
  
#### Parameter  
 `T`  
 Der Typ des `implements`\-Parameters.  
  
 `implements`  
 Zeiger auf den Typ angegeben durch Parameter `T`.  
  
 `iidCount`  
 Die maximale Anzahl von Schnittstellen\-IDs abzurufen.  
  
 `iids`  
 Wenn dieser Vorgang erfolgreich abgeschlossen wird, implementiert ein Array der Schnittstellen\-IDs durch Typ `T`.  
  
## Rückgabewert  
 S\_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler beschreibt.  
  
## Hinweise  
 Ruft ein Array Schnittstellen\-IDs ab, die von einem angegebenen Typ implementiert werden.  
  
## Anforderungen  
 **Header:** implements.h  
  
 **Namespace:**  Microsoft::WRL::Details  
  
## Siehe auch  
 [RuntimeClassBaseT\-Struktur](../windows/runtimeclassbaset-structure.md)