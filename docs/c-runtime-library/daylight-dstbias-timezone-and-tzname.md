---
title: _daylight, _dstbias, _timezone und _tzname | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- tzname
- _timezone
- timezone
- _daylight
- _tzname
- daylight
dev_langs:
- C++
helpviewer_keywords:
- time zones
- time adjustments
- timezone variables
- _tzname function
- _daylight function
- _timezone function
- daylight function
- local time adjustments
- timezone function
- tzname function
- time-zone variables
ms.assetid: d06c7292-6b99-4aba-b284-16a96570c856
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 0b2b40db8d478eeb1570022bd1c901c2c28a883b
ms.contentlocale: de-de
ms.lasthandoff: 05/18/2017

---
# <a name="daylight-dstbias-timezone-and-tzname"></a>_daylight, _dstbias, _timezone und _tzname
`_daylight`, `_dstbias`, `_timezone` und `_tzname` werden in einigen Uhrzeit- und Datumsroutinen zur Anpassung an die jeweilige Ortszeit verwendet. Diese globalen Variablen wurden gegen die sichereren Funktionsversionen ausgetauscht, die anstelle der globalen Variablen verwendet werden sollen.  
  
|Globale Variable|Funktionale Entsprechung|  
|---------------------|---------------------------|  
|`_daylight`|[_get_daylight](../c-runtime-library/reference/get-daylight.md)|  
|`_dstbias`|[_get_dstbias](../c-runtime-library/reference/get-dstbias.md)|  
|`_timezone`|[_get_timezone](../c-runtime-library/reference/get-timezone.md)|  
|`_tzname`|[_get_tzname](../c-runtime-library/reference/get-tzname.md)|  
  
 Sie werden in Time.h wie folgt deklariert.  
  
## <a name="syntax"></a>Syntax  
  
```  
extern int _daylight;   
extern int _dstbias;   
extern long _timezone;   
extern char *_tzname[2];  
```  
  
## <a name="remarks"></a>Hinweise  
 Bei einem Aufruf von `_ftime`, `localtime` oder `_tzset` werden die Werte von `_daylight`, `_dstbias`, `_timezone` und `_tzname` aus dem Wert der Umgebungsvariablen `TZ` ermittelt. Wenn der Wert von `TZ` nicht explizit festgelegt wird, weisen `_tzname[0]` und `_tzname[1]` die Standardeinstellungen „PST“ bzw. „PDT“ auf.  Mit den Funktionen zur Verarbeitung von Zeitangaben ([_tzset](../c-runtime-library/reference/tzset.md), [_ftime](../c-runtime-library/reference/ftime-ftime32-ftime64.md) und [localtime](../c-runtime-library/reference/localtime-localtime32-localtime64.md)) wird der Wert von `_daylight`, `_dstbias` und `_timezone` festgelegt, indem das Betriebssystem nach dem Standardwert für die einzelnen Variablen abgefragt wird. Die Werte für die globalen Zeitzonenvariablen werden in der folgenden Tabelle aufgeführt.  
  
|Variable|Wert|  
|--------------|-----------|  
|`_daylight`|Nicht null, wenn in `TZ` eine Zone mit Sommerzeit angegeben ist oder diese über das Betriebssystem ermittelt wird; andernfalls 0. Der Standardwert ist 1.|  
|`_dstbias`|Zeitverschiebung durch Sommerzeit.|  
|`_timezone`|Unterschied in Sekunden zwischen koordinierter Weltzeit (Universal Time Coordinated, UTC) und Ortszeit. Der Standardwert beträgt 28.800.|  
|`_tzname[0]`|Der von der Umgebungsvariablen `TZ` abgeleitete Name der Zeitzone. Der Standardwert lautet „PST“.|  
|`_tzname[1]`|Der von der Umgebungsvariablen `TZ` abgeleitete Name der Zone mit Sommerzeit. Der Standardwert lautet „PDT“ (Pacific Daylight Time, Sommerzeit Pazifik).|  
  
## <a name="see-also"></a>Siehe auch  
 [Global Variables (Globale Variablen)](../c-runtime-library/global-variables.md)   
 [_get_daylight](../c-runtime-library/reference/get-daylight.md)   
 [_get_dstbias](../c-runtime-library/reference/get-dstbias.md)   
 [_get_timezone](../c-runtime-library/reference/get-timezone.md)   
 [_get_tzname](../c-runtime-library/reference/get-tzname.md)
