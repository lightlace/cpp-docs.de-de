---
title: _callnewh | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _callnewh
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords: _callnewh
dev_langs: C++
helpviewer_keywords: _callnewh
ms.assetid: 4dcb73e9-6384-4d12-a973-a8807d4de7a8
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 86085472c63d2ad3fbc1cf53d893bd8da2f8c244
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="callnewh"></a>_callnewh
Ruft den aktuell installierten *neuen Handler* auf.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
int _callnewh(  
   size_t size  
   )  
```  
  
#### <a name="parameters"></a>Parameter  
 `size`  
 Der Speicherplatz, den der [neue Operator](../../cpp/new-operator-cpp.md) zu belegen versucht hat.  
  
## <a name="return-value"></a>Rückgabewert  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|0|Fehler: Entweder wurde kein neuer Handler installiert oder der neue Handler ist nicht aktiv.|  
|1|Erfolg: Der neue Handler wurde installiert und ist aktiv. Die Speicherbelegung kann wiederholt werden.|  
  
## <a name="exceptions"></a>Ausnahmen  
 Diese Funktion löst [bad_alloc](../../standard-library/bad-alloc-class.md) aus, wenn der *neue Handler* nicht gefunden werden kann.  
  
## <a name="remarks"></a>Hinweise  
 Der *neue Handler* wird aufgerufen, wenn der [neue Operator](../../cpp/new-operator-cpp.md) die Speicherbelegung nicht erfolgreich durchführen kann. Der neue Handler initialisiert dann möglicherweise einige entsprechende Aktionen, z. B. die Freigabe des Speichers, sodass nachfolgende Belegungen erfolgreich sind.  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|_callnewh|internal.h|  
  
## <a name="see-also"></a>Siehe auch  
 [_set_new_handler](../../c-runtime-library/reference/set-new-handler.md)   
 [_set_new_mode](../../c-runtime-library/reference/set-new-mode.md)