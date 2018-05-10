---
title: _lock | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- _lock
apilocation:
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr100.dll
- msvcr90.dll
- msvcr80.dll
- msvcr110.dll
- msvcrt.dll
- msvcr120_clr0400.dll
apitype: DLLExport
f1_keywords:
- lock
- _lock
dev_langs:
- C++
helpviewer_keywords:
- lock function
- _lock function
ms.assetid: 29f77c37-30de-4b3d-91b6-030216e645a6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f9a518402d027ae128fcf403752fafb448461628
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="lock"></a>_lock
Ruft eine Multi-Thread-Sperre ab.  
  
> [!IMPORTANT]
>  Diese Funktion ist veraltet. Von Visual Studio 2015 an ist sie nicht in der CRT verfügbar.  
  
## <a name="syntax"></a>Syntax  
  
```  
void __cdecl _lock  
   int locknum  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 [in] `locknum`  
 Der Bezeichner der abzurufenden Sperre.  
  
## <a name="remarks"></a>Hinweise  
 Wenn die Sperre bereits abgerufen wurde, ruft diese Methode die Sperre dennoch ab und verursacht einen internen C-Laufzeitfehler (CRT). Wenn die Methode keine Sperre abrufen kann, wird sie mit einem schwerwiegenden Fehler beendet und der Fehlercode auf `_RT_LOCK`festgelegt.  
  
## <a name="requirements"></a>Anforderungen  
 **Quelle:** mlock.c  
  
## <a name="see-also"></a>Siehe auch  
 [Alphabetical Function Reference (Alphabetische Funktionsreferenz)](../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [_unlock](../c-runtime-library/unlock.md)