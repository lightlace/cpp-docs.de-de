---
title: '&lt;sstream&gt;-Typdefinitionen | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d102edd2-ecea-4a35-a398-cf96e58dd422
caps.latest.revision: 9
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 19af112017c3f6e9700a87f1d482fc4f319fb235
ms.lasthandoff: 02/24/2017

---
# <a name="ltsstreamgt-typedefs"></a>&lt;sstream&gt;-Typdefinitionen
||||  
|-|-|-|  
|[istringstream](#istringstream)|[ostringstream](#ostringstream)|[stringbuf](#stringbuf)|  
|[stringstream](#stringstream)|[wistringstream](#wistringstream)|[wostringstream](#wostringstream)|  
|[wstringbuf](#wstringbuf)|[wstringstream](#wstringstream)|  
  
##  <a name="a-nameistringstreama--istringstream"></a><a name="istringstream"></a> istringstream  
 Erstellt einen `basic_istringstream`-Typ, der auf einen `char`-Vorlagenparameter spezialisiert ist.  
  
```  
typedef basic_istringstream<char> istringstream;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für die Vorlagenklasse [basic_istringstream](../standard-library/basic-istringstream-class.md), die auf Elemente des Typs `char`* spezialisiert ist.*  
  
##  <a name="a-nameostringstreama--ostringstream"></a><a name="ostringstream"></a> ostringstream  
 Erstellt einen `basic_ostringstream`-Typ, der auf einen `char`-Vorlagenparameter spezialisiert ist.  
  
```  
typedef basic_ostringstream<char> ostringstream;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für die Vorlagenklasse [basic_ostringstream](../standard-library/basic-ostringstream-class.md), die auf Elemente des Typs `char`* spezialisiert ist.*  
  
##  <a name="a-namestringbufa--stringbuf"></a><a name="stringbuf"></a> stringbuf  
 Erstellt einen `basic_stringbuf`-Typ, der auf einen `char`-Vorlagenparameter spezialisiert ist.  
  
```  
typedef basic_stringbuf<char> stringbuf;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für die Vorlagenklasse [basic_stringbuf](../standard-library/basic-stringbuf-class.md), die auf Elemente des Typs `char`* spezialisiert ist.*  
  
##  <a name="a-namestringstreama--stringstream"></a><a name="stringstream"></a> stringstream  
 Erstellt einen `basic_stringstream`-Typ, der auf einen `char`-Vorlagenparameter spezialisiert ist.  
  
```  
typedef basic_stringstream<char> stringstream;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für die Vorlagenklasse [basic_stringstream](../standard-library/basic-stringstream-class.md), die auf Elemente des Typs `char`* spezialisiert ist.*  
  
##  <a name="a-namewistringstreama--wistringstream"></a><a name="wistringstream"></a> wistringstream  
 Erstellt einen `basic_istringstream`-Typ, der auf einen `wchar_t`-Vorlagenparameter spezialisiert ist.  
  
```  
typedef basic_istringstream<wchar_t> wistringstream;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für die Vorlagenklasse [basic_istringstream](../standard-library/basic-istringstream-class.md), die auf Elemente des Typs `wchar_t` spezialisiert ist.  
  
##  <a name="a-namewostringstreama--wostringstream"></a><a name="wostringstream"></a> wostringstream  
 Erstellt einen `basic_ostringstream`-Typ, der auf einen `wchar_t`-Vorlagenparameter spezialisiert ist.  
  
```  
typedef basic_ostringstream<wchar_t> wostringstream;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für die Vorlagenklasse [basic_ostringstream](../standard-library/basic-ostringstream-class.md), die auf Elemente des Typs `wchar_t` spezialisiert ist.  
  
##  <a name="a-namewstringbufa--wstringbuf"></a><a name="wstringbuf"></a> wstringbuf  
 Erstellt einen `basic_stringbuf`-Typ, der auf einen `wchar_t`-Vorlagenparameter spezialisiert ist.  
  
```  
typedef basic_stringbuf<wchar_t> wstringbuf;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für die Vorlagenklasse [basic_stringbuf](../standard-library/basic-stringbuf-class.md), die auf Elemente des Typs `wchar_t` spezialisiert ist.  
  
##  <a name="a-namewstringstreama--wstringstream"></a><a name="wstringstream"></a> wstringstream  
 Erstellt einen `basic_stringstream`-Typ, der auf einen `wchar_t`-Vorlagenparameter spezialisiert ist.  
  
```  
typedef basic_stringstream<wchar_t> wstringstream;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für die Vorlagenklasse [basic_stringstream](../standard-library/basic-stringstream-class.md), die auf Elemente des Typs `wchar_t` spezialisiert ist.  
  
## <a name="see-also"></a>Siehe auch  
 [\<sstream>](../standard-library/sstream.md)


