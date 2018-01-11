---
title: duration_values-Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- chrono/std::chrono::duration_values
- chrono/std::chrono::duration_values::max
- chrono/std::chrono::duration_values::min
- chrono/std::chrono::duration_values::zero
dev_langs: C++
ms.assetid: 7f66d2e3-1faf-47c3-b47e-08f2a87f20e8
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a0f06646975d694ab76477a64642c03c20769c54
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="durationvalues-structure"></a>duration_values-Struktur
Stellt bestimmte Werte für den [duration](../standard-library/duration-class.md)-Vorlagenparameter `Rep` bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class Rep>  
struct duration_values;  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[max](#max)|Statisch Gibt die Obergrenze für einen Wert des Typs `Rep` an.|  
|[Min.](#min)|Statisch Gibt die Untergrenze für einen Wert des Typs `Rep` an.|  
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

