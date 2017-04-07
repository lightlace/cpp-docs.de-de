---
title: '&lt;istream&gt;-Funktionen | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0301ea0d-4ded-4841-83dd-4253b55b3188
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: aa35f177bcb986e141d0e46e48dc007a96f94498
ms.lasthandoff: 02/24/2017

---
# <a name="ltistreamgt-functions"></a>&lt;istream&gt;-Funktionen
|||  
|-|-|  
|[swap](#istream_swap)|[ws](#ws)|  
  
##  <a name="istream_swap"></a> swap  
 Tauscht die Elemente zweier Streamobjekte.  
  
```  
template <class Elem, class Tr>  
void swap(
    basic_istream<Elem, Tr>& left,  
    basic_istream<Elem, Tr>& right);

template <class Elem, class Tr>  
void swap(
    basic_iostream<Elem, Tr>& left,  
    basic_iostream<Elem, Tr>& right);
```  
  
### <a name="parameters"></a>Parameter  
 `left`  
 Ein Stream  
  
 `right`  
 Ein Stream  
  
##  <a name="ws"></a> ws  
 Überspringt Leerraum im Datenstrom.  
  
```  
template class<Elem, Tr> basic_istream<Elem, Tr>& ws(basic_istream<Elem, Tr>& _Istr);
```  
  
### <a name="parameters"></a>Parameter  
 `_Istr`  
 Ein Stream.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Stream (Datenstrom).  
  
### <a name="remarks"></a>Hinweise  
 Der Manipulator extrahiert und verwirft Elemente `ch` für die [use_facet](../standard-library/basic-filebuf-class.md#basic_filebuf__open)< **ctype**\< **Elem**> >( [getloc](../standard-library/ios-base-class.md#ios_base__getloc)). **is**(**ctype**\< **Elem**>:: **space**, **ch**) ist TRUE.  
  
 Die Funktion ruft [setstate](../standard-library/basic-ios-class.md#basic_ios__setstate)( **eofbit**) auf, wenn sie beim Extrahieren der Elemente auf das Ende der Datei stößt. Er gibt `_Istr` zurück.  
  
### <a name="example"></a>Beispiel  
  Unter [Operator>>](../standard-library/istream-operators.md#operator_gt__gt_) finden Sie ein Beispiel für die Verwendung von `ws`.  
  
## <a name="see-also"></a>Siehe auch  
 [\<istream>](../standard-library/istream.md)


