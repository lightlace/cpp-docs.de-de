---
title: _pclose | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _pclose
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
- _pclose
- pclose
dev_langs: C++
helpviewer_keywords:
- _pclose function
- pclose function
- pipes, closing
ms.assetid: e2e31a9e-ba3a-4124-bcbb-c4040110b3d3
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 13609bbe4dae9b493b8467fd0ac9fe7d1437fa83
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="pclose"></a>_pclose
Wartet auf einen neuen Befehlsprozessor und schließt den Stream auf der zugeordneten Pipe.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie unter [In /ZW nicht unterstützte CRT-Funktionen](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      int _pclose(  
FILE *stream   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `stream`  
 Gibt den Wert vom vorherigen Aufruf von `_popen` zurück.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt den Beendigungsstatus des beendenden Befehlsprozessors oder-1 zurück, wenn ein Fehler auftritt. Das Format des Rückgabewerts ist nahezu mit dem von `_cwait` identisch. Der einzige Unterschied ist, dass die niederwertigen und höherwertigen Bytes vertauscht sind. Wenn der Stream **NULL** ist, legt `_pclose` `errno` auf `EINVAL` fest und gibt –1 zurück.  
  
 Weitere Informationen über diese und andere Fehlercodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Hinweise  
 Die `_pclose`-Funktion sucht die Prozess-ID des Befehlsprozessors (Cmd.exe), der von dem zugeordneten `_popen`-Aufruf gestartet wurde, führt einen [_cwait](../../c-runtime-library/reference/cwait.md)-Aufruf im neuen Befehlsprozessor aus und schließt den Stream auf der zugeordneten Pipe.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_pclose`|\<stdio.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Bibliotheken  
 Alle Versionen der [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Prozess- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)   
 [_pipe](../../c-runtime-library/reference/pipe.md)   
 [_popen, _wpopen](../../c-runtime-library/reference/popen-wpopen.md)