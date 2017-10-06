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
ms.openlocfilehash: 445c18ece9b998d5cfa75a1c9fe5bde3b60b2e52
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

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
