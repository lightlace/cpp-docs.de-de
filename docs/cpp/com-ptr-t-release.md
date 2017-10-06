---
title: _com_ptr_t::Release | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_ptr_t.Release
- _com_ptr_t::Release
dev_langs:
- C++
helpviewer_keywords:
- Release method [C++]
ms.assetid: db448b34-0efa-4f02-b701-ad1ca3ae6ca5
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 6f3875a48977b047dfd8706369d448838626e5c6
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="comptrtrelease"></a>_com_ptr_t::Release
**Microsoft-spezifisch**  
  
 Ruft die **Release** Memberfunktion von **IUnknown** für den gekapselten Schnittstellenzeiger auf.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
void Release( );  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Aufrufe `IUnknown::Release` für den gekapselten Schnittstellenzeiger auf, durch das Auslösen einer `E_POINTER` Fehlermeldung, wenn dieser Schnittstellenzeiger **NULL**.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_com_ptr_t-Klasse](../cpp/com-ptr-t-class.md)
