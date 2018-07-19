---
title: _bstr_t-Operatoren (relational) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _bstr_t::operator>
- _bstr_t::operator==
- _bstr_t::operator>=
- _bstr_t::operator!=
- _bstr_t::operator<
- _bstr_t::operator<=
- _bstr_t::operator!
dev_langs:
- C++
helpviewer_keywords:
- '>= operator [C++], comparing specific objects'
- operator<= [C++], bstr
- '!= operator'
- operator == [C++], bstr
- operator!= [C++], relational operators
- < operator [C++], comparing specific objects
- relational operators [C++], _bstr_t class
- operator== [C++], bstr
- <= operator [C++], with specific objects
- operator <= [C++], bstr
- operator >= [C++], bstr
- operator != [C++], relational operators
- '> operator [C++], comparing specific objects'
- operator< [C++], bstr
- == operator [C++], with specific Visual C++ objects
- operator>= [C++], bstr
- operator < [C++], bstr
- operator > [C++], bstr
ms.assetid: e153da72-37c3-4d8a-b8eb-730d65da64dd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 40834c7c41bc19b395958b4a173a68bd014b2e70
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2018
ms.locfileid: "37943633"
---
# <a name="bstrt-relational-operators"></a>_bstr_t-Operatoren (relational)
**Microsoft-spezifisch**  
  
 Vergleicht zwei `_bstr_t`-Objekte.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
bool operator!( ) const throw( );   
bool operator==(const _bstr_t& str) const throw( );  
bool operator!=(const _bstr_t& str) const throw( );  
bool operator<(const _bstr_t& str) const throw( );  
bool operator>(const _bstr_t& str) const throw( );  
bool operator<=(const _bstr_t& str) const throw( );  
bool operator>=(const _bstr_t& str) const throw( );  
```  
  
## <a name="remarks"></a>Hinweise  
 Diese Operatoren vergleichen zwei `_bstr_t`-Objekte auf lexikografischer Ebene. Die Operatoren geben "true" zurück, wenn die Vergleiche stimmen; andernfalls "false" zurückgegeben.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_bstr_t-Klasse](../cpp/bstr-t-class.md)