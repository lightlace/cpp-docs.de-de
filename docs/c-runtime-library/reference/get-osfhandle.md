---
title: _get_osfhandle | Microsoft-Dokumentation
ms.custom: 
ms.date: 12/12/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _get_osfhandle
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
dev_langs:
- C++
helpviewer_keywords:
- operating systems, getting file handles
- get_osfhandle function
- _get_osfhandle function
- file handles [C++], operating system
ms.assetid: 0bdd728a-4fd8-410b-8c9f-01a121135196
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4ffc65e12c4a9023d0ef649bbf2cb5e8f7e76808
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
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

*fd*  
Eine vorhandener Dateideskriptor.  
  
## <a name="return-value"></a>Rückgabewert

Gibt einen Betriebssystem Dateihandle zurück, wenn *fd* gültig ist. Ansonsten wird der ungültige Parameterhandler, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben, aufgerufen. Diese Funktion gibt zurück, wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, `INVALID_HANDLE_VALUE` (-1) und legt `errno` zu `EBADF`, der angibt, eines ungültiges Dateihandle.  
  
## <a name="remarks"></a>Hinweise

Um eine Datei zu schließen, deren Dateihandle des Betriebssystems (BS) erhalten, indem Sie `_get_osfhandle`, rufen Sie [ \_schließen](../../c-runtime-library/reference/close.md) auf den Dateideskriptor *fd*. Rufen Sie nicht `CloseHandle` für den Rückgabewert dieser Funktion. Das zugrunde liegende Betriebssystem-Dateihandle ist im Besitz der *fd* Dateideskriptor und wird geschlossen, wenn `_close` heißt auf *fd*. Wenn der Dateideskriptor Besitz ist ein `FILE *` Stream und anschließend durch Aufrufen [Fclose](../../c-runtime-library/reference/fclose-fcloseall.md) darauf `FILE *` Stream geschlossen wird, den Dateideskriptor und das zugrunde liegende Betriebssystem-Dateihandle. Rufen Sie in diesem Fall nicht `_close` auf den Dateideskriptor.
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`_get_osfhandle`|\<io.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="see-also"></a>Siehe auch

[File Handling (Dateibehandlung)](../../c-runtime-library/file-handling.md)   
[_schließen](../../c-runtime-library/reference/close.md)   
[_creat, _wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
[_dup, _dup2](../../c-runtime-library/reference/dup-dup2.md)   
[_open, _wopen](../../c-runtime-library/reference/open-wopen.md)
