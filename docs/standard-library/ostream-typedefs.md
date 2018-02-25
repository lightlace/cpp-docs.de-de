---
title: '&lt;ostream&gt;-Typdefinitionen | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- iosfwd/std::ostream
- iosfwd/std::wostream
ms.assetid: 2ec4dc52-a01f-4654-bd65-dd5288777c48
caps.latest.revision: 
manager: ghogen
ms.openlocfilehash: c9ab11cf6436888605a07c91051bf27c45e10fcf
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="ltostreamgt-typedefs"></a>&lt;ostream&gt;-Typdefinitionen
|||  
|-|-|  
|[ostream](#ostream)|[wostream](#wostream)|  
  
##  <a name="ostream"></a> ostream  
 Erstellt einen Typ aus basic_ostream, der auf `char` und `char_traits` auf `char` spezialisiert ist.  
  
```
typedef basic_ostream<char, char_traits<char>> ostream;
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für die Vorlagenklasse [basic_ostream](../standard-library/basic-ostream-class.md), die für Elemente des Typs `char` mit Standardzeichenmerkmalen spezialisiert ist.  
  
##  <a name="wostream"></a> wostream  
 Erstellt einen Typ aus basic_ostream, der auf `wchar_t` und `char_traits` auf `wchar_t` spezialisiert ist.  
  
```
typedef basic_ostream<wchar_t, char_traits<wchar_t>> wostream;
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für die Vorlagenklasse [basic_ostream](../standard-library/basic-ostream-class.md), die für Elemente des Typs `wchar_t` mit Standardzeichenmerkmalen spezialisiert ist.  
  
## <a name="see-also"></a>Siehe auch  
 [\<ostream>](../standard-library/ostream.md)



