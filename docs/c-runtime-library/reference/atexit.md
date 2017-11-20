---
title: atexit | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: atexit
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
apitype: DLLExport
f1_keywords: atexit
dev_langs: C++
helpviewer_keywords:
- processing, at exit
- atexit function
ms.assetid: 92c156d2-8052-4e58-96dc-00128baac6f9
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a385ebeba2d9dd58b59df179884f7add02b03a42
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="atexit"></a>atexit
Verarbeitet die angegebene Funktion beim Beenden.  
  
## <a name="syntax"></a>Syntax  
  
```  
int atexit(  
   void (__cdecl *func )( void )  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `func`  
 Die aufzurufende Funktion.  
  
## <a name="return-value"></a>Rückgabewert  
 Bei Erfolg gibt `atexit` 0 zurück oder bei einem Fehler einen Wert ungleich 0.  
  
## <a name="remarks"></a>Hinweise  
 Wenn das Programm normal beendet wird, wird die Adresse einer aufzurufenden Funktion (`func`) der `atexit`-Funktion übergeben. Aufeinanderfolgende Aufrufe von `atexit` führen zur Erstellung eines Registers von Funktion, die in LIFO-Reihenfolge (last-in, first-out) ausgeführt werden. Die an `atexit` übergebenen Funktionen können keine Parameter verwenden. `atexit` und `_onexit` verwenden den Heap, um das Funktionsregister zu halten. Dementsprechend wird die Anzahl an Funktionen, die verzeichnet werden können, nur durch den Heapspeicher eingeschränkt.  
  
 Der Code in der `atexit`-Funktion sollte keine Abhängigkeiten von einer DLL enthalten, die möglicherweise schon zum Zeitpunkt des Aufrufs der `atexit`-Funktion entladen wurde.  
  
 Verwenden Sie statt der ähnlichen `_onexit`-Funktion die ANSI-Standardfunktion `atexit`, um eine ANSI-konforme Anwendung zu generieren.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`atexit`|\<stdlib.h>|  
  
## <a name="example"></a>Beispiel  
 Dieses Programm legt vier neue Funktionen, die ausgeführt werden sollen, wenn `atexit` aufgerufen wird, auf einen Stapel aus Funktionen ab. Wenn das Programm beendet wird, werden die Programme nach dem Last In, First Out-Prinzip ausgeführt.  
  
```  
// crt_atexit.c  
#include <stdlib.h>  
#include <stdio.h>  
  
void fn1( void ), fn2( void ), fn3( void ), fn4( void );  
  
int main( void )  
{  
   atexit( fn1 );  
   atexit( fn2 );  
   atexit( fn3 );  
   atexit( fn4 );  
   printf( "This is executed first.\n" );  
}  
  
void fn1()  
{  
   printf( "next.\n" );  
}  
  
void fn2()  
{  
   printf( "executed " );  
}  
  
void fn3()  
{  
   printf( "is " );  
}  
  
void fn4()  
{  
   printf( "This " );  
}  
```  
  
```Output  
This is executed first.  
This is executed next.  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Prozess- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [exit, _Exit, _exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [_onexit, _onexit_m](../../c-runtime-library/reference/onexit-onexit-m.md)