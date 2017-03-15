---
title: '&lt;chrono&gt;-Funktionen | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d6800e15-77a1-4df3-900e-d8b2fee190c7
caps.latest.revision: 10
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 9824bdc37d1ae2d1d3a8e42c727986fd2a194514
ms.lasthandoff: 02/24/2017

---
# <a name="ltchronogt-functions"></a>&lt;chrono&gt;-Funktionen
||||  
|-|-|-|  
|[duration_cast-Funktion](#duration_cast_function)|[time_point_cast-Funktion](#time_point_cast_function)|  
  

##  <a name="a-namedurationcastfunctiona--durationcast-function"></a><a name="duration_cast_function"></a> duration_cast-Funktion  
 Wandelt einen `duration`-Objekt in einen angegebenen Typ um.  
  
```  
template <class To, class Rep, class Period>  
constexpr To duration_cast(const duration<Rep, Period>& Dur);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `duration`-Objekt des Typs `To`, der das `Dur` Zeitintervall darstellt, das abgeschnitten wird, wenn es in den Zieltyp passen muss.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `To` eine Instanziierung von `duration` ist, wird diese Funktion nicht an der Überladungsauflösung beteiligt.  
  
##  <a name="a-nametimepointcastfunctiona--timepointcast-function"></a><a name="time_point_cast_function"></a> time_point_cast-Funktion  
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


