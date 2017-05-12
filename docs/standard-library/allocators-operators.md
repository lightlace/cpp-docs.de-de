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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 0a2da6c72e8900c0cea86c30c6b8511e6b256ff9
ms.contentlocale: de-de
ms.lasthandoff: 04/29/2017

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




