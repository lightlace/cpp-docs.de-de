---
title: '&lt;system_error&gt;-Operatoren | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- system_error/std::operator!=
- system_error/std::operator==
dev_langs:
- C++
ms.assetid: c14edefb-bd8a-4e90-88d3-c59c98e6f73c
caps.latest.revision: 11
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: ed01a5abeb54f5071968555b563849e2cd4ac1af
ms.contentlocale: de-de
ms.lasthandoff: 10/03/2017

---
# <a name="ltsystemerrorgt-operators"></a>&lt;system_error&gt;-Operatoren
||||  
|-|-|-|  
|[operator!=](#op_neq)|[operator&lt;](#op_lt)|[operator==](#op_eq_eq)|  
  
##  <a name="op_eq_eq"></a> operator==  
 Testet, ob das Objekt links vom Operator gleich dem Objekt rechts vom Operator ist.  
  
```
bool operator==(const error_code& left,
    const error_condition& right);

bool operator==(const error_condition& left,
    const error_code& right);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`left`|Das Objekt, das auf Gleichheit getestet werden soll.|  
|`right`|Das Objekt, das auf Gleichheit getestet werden soll.|  
  
### <a name="return-value"></a>Rückgabewert  
 **TRUE**, wenn die Objekte gleich sind; **FALSE**, wenn die Objekte nicht gleich sind.  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion gibt `left.category() == right.category() && left.value() == right.value()`zurück.  
  
##  <a name="op_neq"></a> operator!=  
 Testet, ob das Objekt links vom Operator ungleich dem Objekt rechts vom Operator ist.  
  
```
bool operator!=(const error_code& left,
    const error_condition& right);

bool operator!=(const error_condition& left,
    const error_code& right);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`left`|Das Objekt, das auf Ungleichheit geprüft werden soll.|  
|`right`|Das Objekt, das auf Ungleichheit geprüft werden soll.|  
  
### <a name="return-value"></a>Rückgabewert  
 **TRUE**, wenn das in `left` übergebene Objekt nicht gleich dem in `right` übergebenen Objekt ist, andernfalls **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion gibt `!(left == right)`zurück.  
  
##  <a name="op_lt"></a> operator&lt;  
 Testet, ob ein Objekt kleiner ist als das Objekt, das für den Vergleich übergeben wurde.  
  
```
template <class _Enum>  
inline bool operator<(
    _Enum left,
    typename enable_if<is_error_code_enum<_Enum>::value,
    const error_code&>::type right);

template <class _Enum>  
inline bool operator<(
    typename enable_if<is_error_code_enum<_Enum>::value,
    const error_code&>::type left, _Enum right);

template <class _Enum>  
inline bool operator<(
    _Enum left,
    typename enable_if<is_error_condition_enum<_Enum>::value,
    const error_condition&>::type right);

template <class _Enum>  
inline bool operator<(
    typename enable_if<is_error_condition_enum<_Enum>::value,
    const error_condition&>::type left, _Enum right);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`left`|Das zu vergleichende Objekt.|  
|`right`|Das zu vergleichende Objekt.|  
  
### <a name="return-value"></a>Rückgabewert  
 **TRUE**, wenn das in `left` übergebene Objekt kleiner als das in `right` übergebene ist; andernfalls **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion wird die Fehlerreihenfolge getestet.  
  
## <a name="see-also"></a>Siehe auch  
 [<system_error>](../standard-library/system-error.md)




