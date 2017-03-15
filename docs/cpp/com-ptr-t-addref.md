---
title: "_com_ptr_t::AddRef | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
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
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
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