---
title: _commit | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _commit
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
- _commit
- commit
dev_langs: C++
helpviewer_keywords:
- files [C++], flushing
- flushing files to disk
- commit function
- _commit function
- committing files to disk
ms.assetid: d0c74d3a-4f2d-4fb0-b140-2d687db3d233
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9e4a195566479f9e7e9f5b68a46069701462bb2b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="commit"></a>_commit
Leert eine Datei direkt auf den Datenträger.  
  
## <a name="syntax"></a>Syntax  
  
```  
int _commit(   
   int fd   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `fd`  
 Dateideskriptor, der auf die geöffnete Datei verweist.  
  
## <a name="return-value"></a>Rückgabewert  
 `_commit` gibt 0 zurück, wenn die Datei erfolgreich auf den Datenträger geleert wurde. Ein Rückgabewert von – 1 zeigt einen Fehler.  
  
## <a name="remarks"></a>Hinweise  
 Die `_commit`-Funktion zwingt das Betriebssystem, die mit `fd` verknüpfte Datei auf den Datenträger zu schreiben. Dieser Aufruf stellt sicher, dass die angegebene Datei sofort geleert wird (und nicht nach Ermessen des Betriebssystems).  
  
 Wenn `fd` ein ungültiger Dateideskriptor ist, wird – wie unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben – der Handler für ungültige Parameter aufgerufen. Wenn die weitere Ausführung zugelassen wird, gibt die Funktion -1 zurück und setzt `errno` auf `EBADF`.  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|Optionale Header|  
|-------------|---------------------|----------------------|  
|`_commit`|\<io.h>|\<errno.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="see-also"></a>Siehe auch  
 [E/A auf niedriger Ebene](../../c-runtime-library/low-level-i-o.md)   
 [_creat, _wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_read](../../c-runtime-library/reference/read.md)   
 [_write](../../c-runtime-library/reference/write.md)