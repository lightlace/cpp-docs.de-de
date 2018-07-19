---
title: _com_ptr_t::Attach | Microsoft-Dokumentation
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
ms.openlocfilehash: f8e982ebd9a09d4dfcb5e4b5e150b42a1e8d5c75
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2018
ms.locfileid: "37943792"
---
# <a name="comptrtattach"></a>_com_ptr_t::Attach
**Microsoft-spezifisch**  
  
 Kapselt einen unformatierten Schnittstellenzeiger vom Typ dieses intelligenten Zeigers.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
void Attach( Interface* pInterface ) throw( );  
void Attach( Interface* pInterface, bool fAddRef ) throw( );  
```  
  
#### <a name="parameters"></a>Parameter  
 *pInterface*  
 Ein unformatierter Schnittstellenzeiger.  
  
 *fAddRef*  
 Wenn "true", dann ist `AddRef` aufgerufen wird. Wenn es auf "FALSE" ist die `_com_ptr_t` Objekt übernimmt den Besitz des unformatierten Schnittstellenzeigers, ohne `AddRef`.  
  
## <a name="remarks"></a>Hinweise  
  
-   **Anfügen (***pInterface***)** `AddRef` wird nicht aufgerufen.     Der Besitz der Schnittstelle wird an dieses `_com_ptr_t`-Objekt übergeben. `Release` wird aufgerufen, um den Verweiszähler für den zuvor gekapselten Zeiger zu verringern.  
  
-   **Anfügen (***pInterface* **,***fAddRef***)** Wenn *fAddRef* ist "true", `AddRef`aufgerufen, um den Verweiszähler für den gekapselten Schnittstellenzeiger zu inkrementieren.       Wenn *fAddRef* ist "false", dies `_com_ptr_t` Objekt übernimmt den Besitz des unformatierten Schnittstellenzeigers, ohne `AddRef`. `Release` wird aufgerufen, um den Verweiszähler für den zuvor gekapselten Zeiger zu verringern.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_com_ptr_t-Klasse](../cpp/com-ptr-t-class.md)