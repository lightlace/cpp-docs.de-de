---
title: _bstr_t::Operator = | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _bstr_t::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator = [C++], bstr
- operator= [C++], bstr
ms.assetid: fb31bb1b-ce29-4388-b5fd-8dac830cf18a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ed1de7a529d8c4c1b0d7ae8623d0f1c4a58b5075
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="bstrtoperator-"></a>_bstr_t::operator =
**Microsoft-spezifisch**  
  
 Weist einem vorhandenen `_bstr_t`-Objekt einen neuen Wert zu.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      _bstr_t& operator=(  
   const _bstr_t& s1   
) throw ( );  
_bstr_t& operator=(  
   const char* s2   
);  
_bstr_t& operator=(  
   const wchar_t* s3   
);  
_bstr_t& operator=(  
   const _variant_t& var   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 *s1*  
 Ein `_bstr_t`-Objekt, das einem vorhandenen `_bstr_t`-Objekt zugewiesen werden soll.  
  
 *s2*  
 Eine Multibyte-Zeichenfolge, die einem vorhandenen `_bstr_t` Objekt zugewiesen werden soll.  
  
 `s3`  
 Eine Unicode-Zeichenfolge, die einem vorhandenen `_bstr_t` Objekt zugewiesen werden soll.  
  
 `var`  
 Ein `_variant_t`-Objekt, das einem vorhandenen `_bstr_t`-Objekt zugewiesen werden soll.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [_bstr_t:: Assign](../cpp/bstr-t-assign.md) ein Beispiel der Verwendung von `operator=`.  
  
## <a name="see-also"></a>Siehe auch  
 [_bstr_t-Klasse](../cpp/bstr-t-class.md)