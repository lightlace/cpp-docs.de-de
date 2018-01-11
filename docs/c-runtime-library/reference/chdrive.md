---
title: _chdrive | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _chdrive
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
- chdrive
- _chdrive
dev_langs: C++
helpviewer_keywords:
- drives, changing
- _chdrive function
- chdrive function
ms.assetid: 212a1a4b-4fa8-444e-9677-7fca4c8c47e3
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b7733a366ade87dd937eb20eab97a5258db8787a
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="chdrive"></a>_chdrive
Ändert das aktuelle Laufwerk.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie unter [In /ZW nicht unterstützte CRT-Funktionen](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntax  
  
```  
int _chdrive(   
   int drive   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `drive`  
 Eine ganze Zahl von 1 bis 26, die das aktuelle Laufwerk angibt (1=A, 2=B usw.).  
  
## <a name="return-value"></a>Rückgabewert  
 Null (0), wenn das aktuelle Laufwerk erfolgreich geändert wurde; andernfalls – 1.  
  
## <a name="remarks"></a>Hinweise  
 Wenn `drive` nicht im Bereich von 1 bis 26 liegt, wird der Handler für ungültige Parameter aufgerufen, wie dies in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben wird. Wenn die weitere Ausführung zugelassen wird, gibt die Funktion **_chdrive** -1 zurück, `errno` wird auf `EACCES` gesetzt und `_doserrno` auf `ERROR_INVALID_DRIVE`.  
  
 Die Funktion **_chdrive** ist nicht threadsicher, da sie von der Funktion **SetCurrentDirectory** abhängt, die selbst nicht threadsicher ist. Um **_chdrive** sicher in einer Multithreadanwendung zu verwenden, müssen Sie eine eigene Threadsynchronisierung bereitstellen. Weitere Informationen finden Sie in der [MSDN Library](http://go.microsoft.com/fwlink/p/?linkid=150542). Suchen Sie dort nach **SetCurrentDirectory**.  
  
 Die Funktion **_chdrive** ändert nur das aktuelle Arbeitslaufwerk; **_chdir** ändert das aktuelle Arbeitsverzeichnis.  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|**_chdrive**|\<direct.h>|  
  
 Weitere Informationen finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Beispiel  
 Beachten Sie das Beispiel für [_getdrive](../../c-runtime-library/reference/getdrive.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Directory Control (Verzeichnissteuerung)](../../c-runtime-library/directory-control.md)   
 [_chdir, _wchdir](../../c-runtime-library/reference/chdir-wchdir.md)   
 [_fullpath, _wfullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)   
 [_getcwd, _wgetcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md)   
 [_getdrive](../../c-runtime-library/reference/getdrive.md)   
 [_mkdir, _wmkdir](../../c-runtime-library/reference/mkdir-wmkdir.md)   
 [_rmdir, _wrmdir](../../c-runtime-library/reference/rmdir-wrmdir.md)   
 [system, _wsystem](../../c-runtime-library/reference/system-wsystem.md)