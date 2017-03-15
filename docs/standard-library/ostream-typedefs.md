---
title: '&lt;ostream&gt;-Typdefinitionen | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2ec4dc52-a01f-4654-bd65-dd5288777c48
caps.latest.revision: 11
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 310954b0965be071c288f09de058e3cebe3ce27d
ms.lasthandoff: 02/24/2017

---
# <a name="ltostreamgt-typedefs"></a>&lt;ostream&gt;-Typdefinitionen
|||  
|-|-|  
|[ostream](#ostream)|[wostream](#wostream)|  
  
##  <a name="a-nameostreama--ostream"></a><a name="ostream"></a> ostream  
 Erstellt einen Typ aus basic_ostream, der auf `char` und `char_traits` auf `char` spezialisiert ist.  
  
```
typedef basic_ostream<char, char_traits<char>> ostream;
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für die Vorlagenklasse [basic_ostream](../standard-library/basic-ostream-class.md), die für Elemente des Typs `char` mit Standardzeichenmerkmalen spezialisiert ist.  
  
##  <a name="a-namewostreama--wostream"></a><a name="wostream"></a> wostream  
 Erstellt einen Typ aus basic_ostream, der auf `wchar_t` und `char_traits` auf `wchar_t` spezialisiert ist.  
  
```
typedef basic_ostream<wchar_t, char_traits<wchar_t>> wostream;
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für die Vorlagenklasse [basic_ostream](../standard-library/basic-ostream-class.md), die für Elemente des Typs `wchar_t` mit Standardzeichenmerkmalen spezialisiert ist.  
  
## <a name="see-also"></a>Siehe auch  
 [\<ostream>](../standard-library/ostream.md)




