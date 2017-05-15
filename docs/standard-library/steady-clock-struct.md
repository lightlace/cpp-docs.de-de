---
title: steady_clock struct | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- chrono/std::chrono::steady_clock
dev_langs:
- C++
ms.assetid: 970d12ec-fc80-4391-a2f7-b57b2aec668d
caps.latest.revision: 14
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
ms.sourcegitcommit: 4ecf60434799708acab4726a95380a2d3b9dbb3a
ms.openlocfilehash: 332008ed313eeae7f04f39165424a9280c2aed8c
ms.contentlocale: de-de
ms.lasthandoff: 04/19/2017

---
# <a name="steadyclock-struct"></a>steady_clock-Struktur
Stellt eine `steady` Uhr dar.  
  
## <a name="syntax"></a>Syntax  
  
```  
struct steady_clock;  
```  
  
## <a name="remarks"></a>Hinweise  
 Unter Windows umfasst steady_clock QueryPerformanceCounter-Funktion.  
  
 Eine Uhr ist *monoton*, wenn der von einem ersten Aufruf von `now()` zurückgegebene Wert immer kleiner oder gleich dem Wert ist, der über einen nachfolgenden Aufruf von `now()` zurückgegeben wird.  
  
 Eine Uhr ist *gleichmäßig*, wenn sie *monoton* und die Zeit zwischen den Teilstrichen konstant ist.  
  
 High_resolution_clock ist eine Typdef für steady_clock.  
  
## <a name="public-functions"></a>Öffentliche Funktionen  
  
|Funktion|Beschreibung|  
|--------------|-----------------|  
|now|Gibt die aktuelle Uhrzeit als time_point-Wert zurück.|  
  
## <a name="public-constants"></a>Öffentliche Konstanten  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`system_clock::is_steady`|Ist `true`. Eine `steady_clock` ist *gleichmäßig*.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Chrono >  
  
 **Namespace:** std::chrono  
  
## <a name="see-also"></a>Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [\<chrono>](../standard-library/chrono.md)   
 [system_clock-Struktur](../standard-library/system-clock-structure.md)

