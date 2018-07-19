---
title: +=,-_bstr_t::Operator + | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4a2ea7cd3b93f7445190f16a92a580fe9628a976
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2018
ms.locfileid: "37943267"
---
# <a name="bstrtoperator--"></a>_bstr_t::operator +=, +
**Microsoft-spezifisch**  
  
 Fügt Zeichen am Ende des `_bstr_t`-Objekts hinzu oder verkettet zwei Zeichenfolgen.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
_bstr_t& operator+=( const _bstr_t& s1 );  
_bstr_t operator+( const _bstr_t& s1 );  
friend _bstr_t operator+( const char* s2, const _bstr_t& s1);  
friend _bstr_t operator+( const wchar_t* s3, const _bstr_t& s1);  
```  
  
#### <a name="parameters"></a>Parameter  
 *s1*  
 Ein `_bstr_t`-Objekt.  
  
 *s2*  
 Eine Mehrbytezeichenfolge.  
  
 *s3*  
 Eine Unicode-Zeichenfolge.  
  
## <a name="remarks"></a>Hinweise  
 Diese Operatoren führen eine Zeichenfolgenverkettung aus:  
  
-   **Operator += (***s1***)** fügt die Zeichen im gekapselten `BSTR` von *s1* am Ende dieses Objekts gekapselten `BSTR`.      
  
-   **Operator + (***s1***)** gibt die neue `_bstr_t` sein, der durch die Verkettung dieses Objekts `BSTR` mit dem *s1*.      
  
-   **Operator + (***s2***&#124;***s1***)** gibt ein neues `_bstr_t` sein, der durch die Verkettung ein Multibyte-Zeichenfolge *s2*, umgewandelt in Unicode, mit der `BSTR` in gekapselt *s1*.          
  
-   **Operator + (***s3* **,***s1***)** gibt ein neues `_bstr_t` sein, der durch die Verkettung einer Unicode-Zeichenfolge *s3* mit der `BSTR` in gekapselt *s1*.        
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_bstr_t-Klasse](../cpp/bstr-t-class.md)