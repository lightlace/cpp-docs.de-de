---
title: '&lt;scoped_allocator&gt;-Operatoren | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: []
ms.assetid: 4dfe0805-cc6e-479f-887f-a1c164f73837
caps.latest.revision: 10
manager: ghogen
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: d4602aa94b41a278edaff72f4e7bce6a6ea53407
ms.contentlocale: de-de
ms.lasthandoff: 04/29/2017

---
# <a name="ltscopedallocatorgt-operators"></a>&lt;scoped_allocator&gt;-Header
|||  
|-|-|  
|[operator!=](#op_neq)|[operator==](#op_eq_eq)|  
  
##  <a name="op_neq"></a> operator!=  
 Überprüft zwei `scoped_allocator_adaptor`-Objekte auf Ungleichheit.  
  
```cpp  
template <class Outer, class... Inner>  
bool operator!=(
    const scoped_allocator_adaptor<Outer, Inner...>& left,  
    const scoped_allocator_adaptor<Outer, Inner...>& right) noexcept;  
```  
  
### <a name="parameters"></a>Parameter  
 `left`  
 Das linke `scoped_allocator_adaptor`-Objekt.  
  
 `right`  
 Das rechte `scoped_allocator_adaptor`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 `!(left == right)`  
  
##  <a name="op_eq_eq"></a> operator==  
 Überprüft zwei `scoped_allocator_adaptor`-Objekte auf Gleichheit.  
  
```cpp  
template <class Outer, class... Inner>  
bool operator==(
    const scoped_allocator_adaptor<Outer, Inner...>& left,  
    const scoped_allocator_adaptor<Outer, Inner...>& right) noexcept;  
```  
  
### <a name="parameters"></a>Parameter  
 `left`  
 Das linke `scoped_allocator_adaptor`-Objekt.  
  
 `right`  
 Das rechte `scoped_allocator_adaptor`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 `left.outer_allocator() == right.outer_allocator() && left.inner_allocator() == right.inner_allocator()`  
  
## <a name="see-also"></a>Siehe auch  
 [<scoped_allocator>](../standard-library/scoped-allocator.md)


