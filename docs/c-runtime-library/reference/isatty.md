---
title: _isatty | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _isatty
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
f1_keywords: _isatty
dev_langs: C++
helpviewer_keywords:
- isatty function
- character device checking
- _isatty function
- checking character devices
ms.assetid: 9f1b2e87-0cd7-4079-b187-f2b7ca15fcbe
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4e3c845cf9fc1fec0031ebca94e65ef82445fdff
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="isatty"></a>_isatty
Bestimmt, ob ein Dateideskriptor einem Zeichengerät zugeordnet ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      int _isatty(  
int fd   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `fd`  
 Dateideskriptor, der auf das zu testende Gerät verweist.  
  
## <a name="return-value"></a>Rückgabewert  
 `_isatty` gibt einen Wert ungleich 0 (null) zurück, wenn ein Deskriptor einem Zeichengerät zugeordnet ist. Andernfalls gibt `_isatty` 0 zurück.  
  
## <a name="remarks"></a>Hinweise  
 Die `_isatty`-Funktion bestimmt, ob `fd` einem Zeichengerät zugeordnet ist (Terminal, Konsole, Drucker oder serieller Anschluss).  
  
 Diese Funktion überprüft den `fd`-Parameter. Wenn `fd` ein ungültiger Dateizeiger ist, wird der ungültige Parametertyphandler aufgerufen, wie unter[Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, gibt die Funktion 0 zurück und stellt `errno` auf `EBADF` ein.  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`_isatty`|\<io.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Bibliotheken  
 Alle Versionen [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_isatty.c  
/* This program checks to see whether  
 * stdout has been redirected to a file.  
 */  
  
#include <stdio.h>  
#include <io.h>  
  
int main( void )  
{  
   if( _isatty( _fileno( stdout ) ) )  
      printf( "stdout has not been redirected to a file\n" );  
   else  
      printf( "stdout has been redirected to a file\n");  
}  
```  
  
## <a name="sample-output"></a>Beispielausgabe  
  
```  
stdout has not been redirected to a file  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Dateibehandlung](../../c-runtime-library/file-handling.md)