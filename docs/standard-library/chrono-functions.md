---
title: '&lt;chrono&gt;-Funktionen | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- chrono/std::duration_cast
- chrono/std::time_point_cast
ms.assetid: d6800e15-77a1-4df3-900e-d8b2fee190c7
caps.latest.revision: 10
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 2df866e0f6fec9833c67e4d4ea405a826996dedf
ms.contentlocale: de-de
ms.lasthandoff: 10/03/2017

---
# <a name="ltchronogt-functions"></a>&lt;chrono&gt;-Funktionen
||||  
|-|-|-|  
|[duration_cast](#duration_cast)|[time_point_cast](#time_point_cast)|  
  

##  <a name="duration_cast"></a>duration_cast
 Wandelt einen `duration`-Objekt in einen angegebenen Typ um.  
  
```  
template <class To, class Rep, class Period>  
constexpr To duration_cast(const duration<Rep, Period>& Dur);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `duration`-Objekt des Typs `To`, der das `Dur` Zeitintervall darstellt, das abgeschnitten wird, wenn es in den Zieltyp passen muss.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `To` eine Instanziierung von `duration` ist, wird diese Funktion nicht an der Überladungsauflösung beteiligt.  
  
##  <a name="time_point_cast"></a>time_point_cast
 Wandelt ein [time_point](../standard-library/time-point-class.md)-Objekt in einen angegebenen Typ um.  
  
```  
template <class To, class Clock, class Duration>  
time_point<Clock, To> time_point_cast(const time_point<Clock, Duration>& Tp);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `time_point`-Objekt, das über eine Dauer des Typs `To` verfügt.  
  
### <a name="remarks"></a>Hinweise  
 Sofern `To` keine Instanziierung von [Dauer](../standard-library/duration-class.md) ist, wird diese Funktion nicht an der Überladungsauflösung beteiligt.  
  
## <a name="see-also"></a>Siehe auch  
 [\<chrono>](../standard-library/chrono.md)


