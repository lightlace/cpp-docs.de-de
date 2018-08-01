---
title: _com_ptr_t::AddRef | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::AddRef
dev_langs:
- C++
helpviewer_keywords:
- AddRef method [C++], interface pointers
ms.assetid: c104dac3-aad3-40bb-a298-75c6cd0e63a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4bf56e87b8b7949048b1e6006d3aa32f00af1462
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2018
ms.locfileid: "39404258"
---
# <a name="comptrtaddref"></a>_com_ptr_t::AddRef
**Microsoft-spezifisch**  
  
 Ruft die `AddRef` Memberfunktion `IUnknown` für den gekapselten Schnittstellenzeiger auf.  
  
## <a name="syntax"></a>Syntax  
  
```  
void AddRef( );  
```  
  
## <a name="remarks"></a>Hinweise  
 Aufrufe `IUnknown::AddRef` für den gekapselten Schnittstellenzeiger, Auslösen einer `E_POINTER` Fehler, wenn der Zeiger NULL ist.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_com_ptr_t-Klasse](../cpp/com-ptr-t-class.md)