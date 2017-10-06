---
title: _com_ptr_t::Attach | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::Attach
dev_langs:
- C++
helpviewer_keywords:
- COM interfaces, attach pointer
- Attach method [C++]
ms.assetid: 94c18e0a-06be-4ca7-bdaf-cd54ec0a645e
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
ms.openlocfilehash: aa14a5fb0e54971e19de1b46317d768e7fc06a2e
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="comptrtattach"></a>_com_ptr_t::Attach
**Microsoft-spezifisch**  
  
 Kapselt einen unformatierten Schnittstellenzeiger vom Typ dieses intelligenten Zeigers.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      void Attach(  
   Interface* pInterface   
) throw( );  
void Attach(  
   Interface* pInterface,  
   bool fAddRef   
) throw( );  
```  
  
#### <a name="parameters"></a>Parameter  
 `pInterface`  
 Ein unformatierter Schnittstellenzeiger.  
  
 `fAddRef`  
 Ist er **"true"**, klicken Sie dann `AddRef` aufgerufen wird. Ist er **"false"**, `_com_ptr_t` Objekt übernimmt den Besitz des unformatierten Schnittstellenzeigers ohne Aufruf `AddRef`.  
  
## <a name="remarks"></a>Hinweise  
  
-   **Fügen Sie (**`pInterface`**)** `AddRef` wird nicht aufgerufen.     Der Besitz der Schnittstelle wird an dieses `_com_ptr_t`-Objekt übergeben. **Version** wird aufgerufen, um den Verweiszähler für den zuvor gekapselten Zeiger zu verringern.  
  
-   **Fügen Sie (** `pInterface` **,**`fAddRef`**)** Wenn `fAddRef` ist **"true"**, `AddRef` wird aufgerufen, um den Verweis zu erhöhen. Anzahl der für den gekapselten Schnittstellenzeiger auf.       Wenn `fAddRef` ist **"false"**, gibt diese `_com_ptr_t` Objekt übernimmt den Besitz des unformatierten Schnittstellenzeigers ohne Aufruf `AddRef`. **Version** wird aufgerufen, um den Verweiszähler für den zuvor gekapselten Zeiger zu verringern.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_com_ptr_t-Klasse](../cpp/com-ptr-t-class.md)
