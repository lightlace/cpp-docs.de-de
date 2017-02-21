---
title: "_com_ptr_t::QueryInterface | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_ptr_t::QueryInterface"
  - "_com_ptr_t.QueryInterface"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "QueryInterface-Methode"
ms.assetid: d03292f1-6b02-40db-9756-8b0837a97319
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _com_ptr_t::QueryInterface
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Ruft die `QueryInterface`\-Memberfunktion von **IUnknown** für den gekapselten Schnittstellenzeiger auf.  
  
## Syntax  
  
```  
  
      template<typename _InterfaceType> HRESULT QueryInterface (  
   const IID& iid,  
   _InterfaceType*& p   
) throw ( );  
template<typename _InterfaceType> HRESULT QueryInterface (  
   const IID& iid,  
   _InterfaceType** p  
) throw( );  
```  
  
#### Parameter  
 `iid`  
 **IID** eines Schnittstellenzeigers.  
  
 `p`  
 Nicht formatierter Schnittstellenzeiger.  
  
## Hinweise  
 Ruft **IUnknown::QueryInterface** für den gekapselten Schnittstellenzeiger mit der festgelegten **IID** auf und gibt den resultierenden unformatierten Schnittstellenzeiger in `p` zurück.  Diese Routine gibt `HRESULT` zurück, um einen Erfolg oder Fehler anzuzeigen.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [\_com\_ptr\_t\-Klasse](../cpp/com-ptr-t-class.md)