---
title: _get_osfhandle | Microsoft-Dokumentation
ms.custom: 
ms.date: 09/11/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _get_osfhandle
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- get_osfhandle
- _get_osfhandle
dev_langs: C++
helpviewer_keywords:
- operating systems, getting file handles
- get_osfhandle function
- _get_osfhandle function
- file handles [C++], operating system
ms.assetid: 0bdd728a-4fd8-410b-8c9f-01a121135196
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4e3b15b4577d1d8c0b24df82acff76494474c4e6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="getosfhandle"></a>_get_osfhandle

Holt das Betriebssystem-Dateihandle, das dem angegebenen Dateideskriptor zugeordnet ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
intptr_t _get_osfhandle(   
   int fd   
);  
```  
  
### <a name="parameters"></a>Parameter

*Fd* einer vorhandenen Dateideskriptor.  
  
## <a name="return-value"></a>Rückgabewert

Ein Betriebssystem-Dateihandle Wenn *fd* gültig ist. Ansonsten wird der ungültige Parameterhandler, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben, aufgerufen. Diese Funktion gibt zurück, wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, `INVALID_HANDLE_VALUE` (-1) und legt `errno` zu `EBADF`, der angibt, eines ungültiges Dateihandle.  
  
## <a name="remarks"></a>Hinweise

Um eine Datei zu schließen, deren Betriebssystem Dateihandle erhalten, indem Sie `_get_osfhandle`, rufen Sie [ \_schließen](../../c-runtime-library/reference/close.md) auf den Dateideskriptor *fd*. Durch einen Aufruf von `_close` wird auch das zugrunde liegende Handle geschlossen; daher ist es nicht notwendig die Win32-Funktion `CloseHandle` am ursprünglichen Handle aufzurufen.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_get_osfhandle`|\<io.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="see-also"></a>Siehe auch

[File Handling (Dateibehandlung)](../../c-runtime-library/file-handling.md)   
[_close](../../c-runtime-library/reference/close.md)   
[_creat, _wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
[_dup, _dup2](../../c-runtime-library/reference/dup-dup2.md)   
[_open, _wopen](../../c-runtime-library/reference/open-wopen.md)
