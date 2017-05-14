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
- chrono/std::chrono::duration_values::max
- chrono/std::chrono::duration_values::min
- chrono/std::chrono::duration_values::zero
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: b170debfdb4759b41963bc0faca13b3db11ad39a
ms.contentlocale: de-de
ms.lasthandoff: 04/29/2017

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
|[max](#max)|Statisch Gibt die Obergrenze für einen Wert des Typs `Rep` an.|  
|[min](#min)|Statisch Gibt die Untergrenze für einen Wert des Typs `Rep` an.|  
|[0 (null)](#zero)|Statisch Gibt `Rep(0)`zurück.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Chrono >  
  
 **Namespace:** std::chrono  
  
##  <a name="max"></a> duration_values::max  
 Statische Methode, von der die Obergrenze für Werte vom Typ `Ref` zurückgegeben wird.  
  
```  
static constexpr Rep max();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Tatsächlich wird `numeric_limits<Rep>::max()` zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `Rep` ein benutzerdefinierter Typ ist, muss der Rückgabewert größer als [duration_values::zero](#zero) sein.  
  
##  <a name="min"></a> duration_values::min  
 Statische Methode, von der die Untergrenze für Werte vom Typ `Ref` zurückgegeben wird.  
  
```  
static constexpr Rep min();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Tatsächlich wird `numeric_limits<Rep>::lowest()` zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `Rep` ein benutzerdefinierter Typ ist, muss der Rückgabewert kleiner oder gleich [duration_values::zero](#zero) sein.  
  
##  <a name="zero"></a> duration_values::zero  
 Gibt `Rep(0)`zurück.  
  
```  
static constexpr Rep zero();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn `Rep` ein benutzerdefinierter Typ ist, muss der Rückgabewert die additive Infinity darstellen.  
  
## <a name="see-also"></a>Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [\<chrono>](../standard-library/chrono.md)


