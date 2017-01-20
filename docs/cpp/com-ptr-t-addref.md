---
title: "_com_ptr_t::AddRef"
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
  - "_com_ptr_t::AddRef"
  - "_com_ptr_t.AddRef"
  - "AddRef"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AddRef-Methode [C++], Schnittstellenzeiger"
ms.assetid: c104dac3-aad3-40bb-a298-75c6cd0e63a2
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# _com_ptr_t::AddRef
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Ruft die `AddRef`\-Memberfunktion von **IUnknown** für den gekapselten Schnittstellenzeiger auf.  
  
## Syntax  
  
```  
  
void AddRef( );  
  
```  
  
## Hinweise  
 Ruft `IUnknown::AddRef` für den gekapselten Schnittstellenzeiger und löst einen `E_POINTER`\-Fehler aus, sofern der Zeiger den Wert **NULL** aufweist.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [\_com\_ptr\_t\-Klasse](../cpp/com-ptr-t-class.md)