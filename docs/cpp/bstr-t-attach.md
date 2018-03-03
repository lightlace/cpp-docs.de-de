---
title: _bstr_t::Attach | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _bstr_t::Attach
dev_langs:
- C++
helpviewer_keywords:
- Attach method [C++]
ms.assetid: 8cad867e-40fc-435b-841f-0d412c2f58d3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0c6d60347b9b5be10923e23e839d99ddd0f1cee4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="bstrtattach"></a>_bstr_t::Attach
**Microsoft-spezifisch**  
  
 Verknüpft einen `_bstr_t`-Wrapper mit einem `BSTR`.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      void Attach(  
   BSTR s  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 *s*  
 Eine `BSTR`-Variable, die `_bstr_t` zugeordnet oder zugewiesen werden soll.  
  
## <a name="remarks"></a>Hinweise  
 Wenn `_bstr_t` zuvor an einen anderen `BSTR` angefügt war, bereinigt `_bstr_t` die `BSTR`-Ressource, wenn keine anderen `_bstr_t`-Variablen den `BSTR` verwenden.  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [_bstr_t:: Assign](../cpp/bstr-t-assign.md) ein Beispiel mit **Anfügen**.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_bstr_t-Klasse](../cpp/bstr-t-class.md)