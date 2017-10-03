---
title: '&lt;scoped_allocator&gt;-Operatoren | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- scoped_allocator/std::operator!=
- scoped_allocator/std::operator==
dev_langs:
- C++
ms.assetid: 4dfe0805-cc6e-479f-887f-a1c164f73837
caps.latest.revision: 10
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: d29a5a99f261776468364717a13b90a1ddde5216
ms.contentlocale: de-de
ms.lasthandoff: 10/03/2017

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


