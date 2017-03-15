---
title: "_com_ptr_t::GetInterfacePtr | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_ptr_t::GetInterfacePtr"
  - "_com_ptr_t.GetInterfacePtr"
  - "GetInterfacePtr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetInterfacePtr-Methode"
ms.assetid: 55e3e2c7-c939-48b5-a905-4b9cbefeea7e
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _com_ptr_t::GetInterfacePtr
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Gibt den gekapselten Schnittstellenzeiger zurück.  
  
## Syntax  
  
```  
  
      Interface* GetInterfacePtr( ) const throw( );   
Interface*& GetInterfacePtr() throw();  
```  
  
## Hinweise  
 Gibt den gekapselten Schnittstellenzeiger zurück, der möglicherweise **NULL** ist.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [\_com\_ptr\_t\-Klasse](../cpp/com-ptr-t-class.md)