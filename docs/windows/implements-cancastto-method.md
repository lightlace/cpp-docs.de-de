---
title: "Implements::CanCastTo-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Implements::CanCastTo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CanCastTo-Methode"
ms.assetid: a8e85c7d-4dcd-446d-bebc-a97da46ce44a
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# Implements::CanCastTo-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ruft einen Zeiger auf die angegebene Schnittstelle.  
  
## Syntax  
  
```  
__forceinline HRESULT CanCastTo(  
   REFIID riid,  
   _Deref_out_ void **ppv  
);  
```  
  
#### Parameter  
 `riid`  
 Ein Verweis auf eine Schnittstelle ID  
  
 `ppv`  
 Wenn erfolgreich, ein Zeiger zur Schnittstelle angegeben durch `riid`.  
  
## Rückgabewert  
 S\_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt, z E\_NOINTERFACE.  
  
## Hinweise  
 Dies ist eine interne Hilfsfunktion, die einen QueryInterface\-Vorgang ausführt.  
  
## Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [Implements\-Struktur](../windows/implements-structure.md)