---
title: '&lt;Allocators&gt;-Operatoren | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- allocators/std::operator!=
- allocators/std::operator==
dev_langs:
- C++
ms.assetid: b55d67cb-3c69-46bf-ad40-e845fb096c4e
caps.latest.revision: 11
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: c6b19eb0c4f8d63ce288ce47a759e949714daf5e
ms.contentlocale: de-de
ms.lasthandoff: 10/03/2017

---
# <a name="ltallocatorsgt-operators"></a>&lt;Allocators&gt;-Operatoren
|||  
|-|-|  
|[operator!=](#op_neq)|[operator==](#op_eq_eq)|  
  
##  <a name="op_neq"></a> operator!=  
 Es wird auf Ungleichheit zwischen Zuweisungsobjekten einer bestimmten Klasse getestet.  
  
```
template <class Type, class Sync>  
bool operator!=(
    const allocator_base<Type, Sync>& left,
    const allocator_base<Type, Sync>& right);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`left`|Eines der Zuweisungsobjekte, die auf Ungleichheit geprüft werden sollen.|  
|`right`|Eines der Zuweisungsobjekte, die auf Ungleichheit geprüft werden sollen.|  
  
### <a name="return-value"></a>Rückgabewert  
 **TRUE**, wenn die Zuweisungsobjekte nicht gleich sind; **FALSE**, wenn die Zuweisungsobjekte gleich sind.  
  
### <a name="remarks"></a>Hinweise  
 Der Vorlagenoperator gibt `!(left == right)` zurück.  
  
##  <a name="op_eq_eq"></a> operator==  
 Es wird auf Gleichheit zwischen Zuweisungsobjekten einer bestimmten Klasse getestet.  
  
```
template <class Type, class Sync>  
bool operator==(
    const allocator_base<Type, Sync>& left,
    const allocator_base<Type, Sync>& right);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`left`|Eines der Zuweisungsobjekte, die auf Gleichheit geprüft werden sollen.|  
|`right`|Eines der Zuweisungsobjekte, die auf Gleichheit geprüft werden sollen.|  
  
### <a name="return-value"></a>Rückgabewert  
 **TRUE**, wenn die Zuweisungsobjekte gleich sind; **FALSE**, wenn die Zuweisungsobjekte nicht gleich sind.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Vorlagenoperator gibt `left.equals(right)` zurück.  
  
## <a name="see-also"></a>Siehe auch  
 [\<allocators>](../standard-library/allocators-header.md)




