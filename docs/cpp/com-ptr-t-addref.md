---
title: _com_ptr_t::AddRef | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _com_ptr_t::AddRef
dev_langs: C++
helpviewer_keywords: AddRef method [C++], interface pointers
ms.assetid: c104dac3-aad3-40bb-a298-75c6cd0e63a2
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e1230ac8bcf210e519420e8fb4ef84e77bcd4869
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="comptrtaddref"></a>_com_ptr_t::AddRef
**Microsoft-spezifisch**  
  
 Ruft die `AddRef` Memberfunktion von **IUnknown** für den gekapselten Schnittstellenzeiger auf.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
void AddRef( );  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Aufrufe `IUnknown::AddRef` für den gekapselten Schnittstellenzeiger auf, durch das Auslösen einer `E_POINTER` Fehler, wenn der Zeiger **NULL**.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_com_ptr_t-Klasse](../cpp/com-ptr-t-class.md)