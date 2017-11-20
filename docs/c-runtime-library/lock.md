---
title: _lock | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _lock
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
dev_langs: C++
helpviewer_keywords:
- lock function
- _lock function
ms.assetid: 29f77c37-30de-4b3d-91b6-030216e645a6
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 851c4a72a4313867f06985e2c77a7035c6a5e9ae
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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
 [Alphabetische Funktionsreferenz](../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [_unlock](../c-runtime-library/unlock.md)