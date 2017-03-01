---
title: duration_values-Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- chrono/std::chrono::duration_values
dev_langs:
- C++
ms.assetid: 7f66d2e3-1faf-47c3-b47e-08f2a87f20e8
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 8b0c02d4edc3a460f166cb65b312ef78337d403f
ms.lasthandoff: 02/24/2017

---
# <a name="durationvalues-structure"></a>duration_values-Struktur
Stellt bestimmte Werte für den [duration](../standard-library/duration-class.md)-Vorlagenparameter `Rep` bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class Rep>  
struct duration_values;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[duration_values::max](#duration_values__max_method)|Statisch Gibt die Obergrenze für einen Wert des Typs `Rep` an.|  
|[duration_values::min](#duration_values__min_method)|Statisch Gibt die Untergrenze für einen Wert des Typs `Rep` an.|  
|[duration_values::zero](#duration_values__zero_method)|Statisch Gibt `Rep(0)`zurück.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** chrono  
  
 **Namespace:** std::chrono  
  
##  <a name="a-namedurationvaluesmaxmethoda--durationvaluesmax"></a><a name="duration_values__max_method"></a> duration_values::max  
 Statische Methode, von der die Obergrenze für Werte vom Typ `Ref` zurückgegeben wird.  
  
```  
static constexpr Rep max();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Tatsächlich wird `numeric_limits<Rep>::max()` zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `Rep` ein benutzerdefinierter Typ ist, muss der Rückgabewert größer als [duration_values::zero](#duration_values__zero_method) sein.  
  
##  <a name="a-namedurationvaluesminmethoda--durationvaluesmin"></a><a name="duration_values__min_method"></a> duration_values::min  
 Statische Methode, von der die Untergrenze für Werte vom Typ `Ref` zurückgegeben wird.  
  
```  
static constexpr Rep min();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Tatsächlich wird `numeric_limits<Rep>::lowest()` zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `Rep` ein benutzerdefinierter Typ ist, muss der Rückgabewert kleiner oder gleich [duration_values::zero](#duration_values__zero_method) sein.  
  
##  <a name="a-namedurationvalueszeromethoda--durationvalueszero"></a><a name="duration_values__zero_method"></a> duration_values::zero  
 Gibt `Rep(0)`zurück.  
  
```  
static constexpr Rep zero();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn `Rep` ein benutzerdefinierter Typ ist, muss der Rückgabewert die additive Infinity darstellen.  
  
## <a name="see-also"></a>Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [\<chrono>](../standard-library/chrono.md)


