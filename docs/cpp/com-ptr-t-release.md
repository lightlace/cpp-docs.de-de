---
title: "_com_ptr_t::Release"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "_com_ptr_t.Release"
  - "_com_ptr_t::Release"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Release-Methode"
ms.assetid: db448b34-0efa-4f02-b701-ad1ca3ae6ca5
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# _com_ptr_t::Release
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Ruft die **Release**\-Memberfunktion von **IUnknown** für den gekapselten Schnittstellenzeiger auf.  
  
## Syntax  
  
```  
  
void Release( );  
  
```  
  
## Hinweise  
 Ruft `IUnknown::Release` für den gekapselten Schnittstellenzeiger auf und löst einen `E_POINTER`\-Fehler aus, wenn dieser Schnittstellenzeiger **NULL** ist.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [\_com\_ptr\_t\-Klasse](../cpp/com-ptr-t-class.md)