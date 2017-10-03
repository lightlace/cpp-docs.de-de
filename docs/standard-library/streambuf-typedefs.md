---
title: '&lt;streambuf&gt;-Typdefinitionen | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- iosfwd/std::streambuf
- iosfwd/std::wstreambuf
ms.assetid: 2678e18f-f0f0-4995-bc53-f1bc7dfc4ec6
caps.latest.revision: 11
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 932b5ce7a664f75eb92f19fdbf32363b9300fb09
ms.contentlocale: de-de
ms.lasthandoff: 10/03/2017

---
# <a name="ltstreambufgt-typedefs"></a>&lt;streambuf&gt;-Typdefinition
|||  
|-|-|  
|[streambuf](#streambuf)|[wstreambuf](#wstreambuf)|  
  
##  <a name="streambuf"></a> streambuf  
 Eine Spezialisierung von `basic_streambuf`, die `char` als Vorlagenparameter verwendet.  
  
```
typedef basic_streambuf<char, char_traits<char>> streambuf;
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für die Vorlagenklasse [basic_filebuf](../standard-library/basic-streambuf-class.md), die auf Elemente vom Typ `char` mit Standardzeichenmerkmalen spezialisiert ist.  
  
##  <a name="wstreambuf"></a> wstreambuf  
 Eine Spezialisierung von `basic_streambuf`, die `wchar_t` als Vorlagenparameter verwendet.  
  
```
typedef basic_streambuf<wchar_t, char_traits<wchar_t>> wstreambuf;
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für die Vorlagenklasse [basic_filebuf](../standard-library/basic-streambuf-class.md), die auf Elemente vom Typ `wchar_t` mit Standardzeichenmerkmalen spezialisiert ist.  
  
## <a name="see-also"></a>Siehe auch  
 [\<streambuf>](../standard-library/streambuf.md)




