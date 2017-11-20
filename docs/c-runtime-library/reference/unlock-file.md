---
title: _unlock_file | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _unlock_file
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _unlock_file
- unlock_file
dev_langs: C++
helpviewer_keywords:
- files [C++], unlocking
- unlock_file function
- _unlock_file function
- unlocking files
ms.assetid: cf380a51-6d3a-4f38-bd64-2d4fb57b4369
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 246fd73cdc3b380dae7ea9a6a3d02fcd9290ba1d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="unlockfile"></a>_unlock_file
Hebt die Sperre einer Datei auf, sodass andere Prozesse auf die Datei zugreifen können.  
  
## <a name="syntax"></a>Syntax  
  
```  
void _unlock_file(  
   FILE* file  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `file`  
 Dateihandle.  
  
## <a name="remarks"></a>Hinweise  
 Die `_unlock_file`-Funktion hebt die Sperre der von `file` angegebenen Datei auf. Das Entsperren einer Datei ermöglicht anderen Prozessen den Zugriff auf die Datei. Diese Funktion sollte nur aufgerufen werden, wenn zuvor `_lock_file` auf dem `file`-Zeiger aufgerufen wurde. Das Aufrufen von `_unlock_file` auf einer Datei, die nicht gesperrt ist, kann zu einem Deadlock führen. Ein Beispiel finden Sie unter [_lock_file](../../c-runtime-library/reference/lock-file.md).  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_unlock_file`|\<stdio.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="see-also"></a>Siehe auch  
 [Dateibehandlung](../../c-runtime-library/file-handling.md)   
 [_creat, _wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_lock_file](../../c-runtime-library/reference/lock-file.md)