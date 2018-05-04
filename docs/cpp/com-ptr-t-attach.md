---
title: _com_ptr_t::Attach | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::Attach
dev_langs:
- C++
helpviewer_keywords:
- COM interfaces, attach pointer
- Attach method [C++]
ms.assetid: 94c18e0a-06be-4ca7-bdaf-cd54ec0a645e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7341695ad0cbc8384da859b80a72a63d8d52215f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
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