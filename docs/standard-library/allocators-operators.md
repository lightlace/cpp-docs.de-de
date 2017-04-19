---
title: '&lt;Allocators&gt;-Operatoren | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: []
ms.assetid: b55d67cb-3c69-46bf-ad40-e845fb096c4e
caps.latest.revision: 11
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 6185bc74c530d6327d0ac37a5425a7653ba36841
ms.lasthandoff: 02/24/2017

---
# <a name="ltallocatorsgt-operators"></a>&lt;Allocators&gt;-Operatoren
|||  
|-|-|  
|[operator!=](#operator_neq)|[operator==](#operator_eq_eq)|  
  
##  <a name="operator_neq"></a> operator!=  
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
  
##  <a name="operator_eq_eq"></a> operator==  
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




