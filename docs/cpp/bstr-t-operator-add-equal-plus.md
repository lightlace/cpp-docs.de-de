---
title: _bstr_t::Operator +=, + | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _bstr_t::operator+
- _bstr_t::operator+=
dev_langs:
- C++
helpviewer_keywords:
- += operator [C++], appending strings
- + operator [C++], _bstr_t objects
ms.assetid: d28316ce-c2c8-4a38-bdb3-44fa4e582c44
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1ceeec1461b05b25d4bb0b42321cb9b3988ce4b0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="bstrtoperator--"></a>_bstr_t::operator +=, +
**Microsoft-spezifisch**  
  
 Fügt Zeichen am Ende des `_bstr_t`-Objekts hinzu oder verkettet zwei Zeichenfolgen.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      _bstr_t& operator+=(  
   const _bstr_t& s1   
);  
_bstr_t operator+(  
   const _bstr_t& s1   
);  
friend _bstr_t operator+(  
   const char* s2,  
   const _bstr_t& s1   
);  
friend _bstr_t operator+(  
   const wchar_t* s3,  
   const _bstr_t& s1   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 *s1*  
 Ein `_bstr_t`-Objekt.  
  
 *s2*  
 Eine Mehrbytezeichenfolge.  
  
 `s3`  
 Eine Unicode-Zeichenfolge.  
  
## <a name="remarks"></a>Hinweise  
 Diese Operatoren führen eine Zeichenfolgenverkettung aus:  
  
-   **Operator += (***s1***)** fügt die Zeichen in das gekapselte `BSTR` von *s1* am Ende dieses Objekts gekapselten `BSTR`.  
  
-   **Operator + (***s1***)** gibt die neue `_bstr_t` , wird gebildet, indem Sie dieses Objekt verketten `BSTR` mit der *s1*.  
  
-   **Operator + (***s2***&#124;** *s1***)** gibt eine neue `_bstr_t` , wird gebildet, indem eine multibyte-Zeichenfolge verketten *s2*, umgewandelt in Unicode, mit der `BSTR` in den gekapselt *s1*.  
  
-   **Operator + (** `s3` **,***s1***)** gibt eine neue `_bstr_t` , wird gebildet, indem Sie eine Unicode-Zeichenfolge verketten `s3` mit der `BSTR` in gekapselt *s1*.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_bstr_t-Klasse](../cpp/bstr-t-class.md)