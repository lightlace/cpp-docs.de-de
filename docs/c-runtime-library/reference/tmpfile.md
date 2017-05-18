---
title: tmpfile | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- tmpfile
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
- tmpfile
dev_langs:
- C++
helpviewer_keywords:
- temporary files
- tmpfile function
- temporary files, creating
ms.assetid: c4a4dc24-70da-438d-ae4e-98352d88e375
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: efb6cd7868a393d4c946382c59b071de138ff55b
ms.contentlocale: de-de
ms.lasthandoff: 03/29/2017

---
# <a name="tmpfile"></a>tmpfile
Erstellt eine temporäre Datei. Diese Funktion ist veraltet, da eine sicherere Version verfügbar ist. Sie finden sie unter [tmpfile_s](../../c-runtime-library/reference/tmpfile-s.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
FILE *tmpfile( void );  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Im Erfolgsfall gibt `tmpfile` einen Streamzeiger zurück. Andernfalls wird ein `NULL`-Zeiger zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 Die Funktion `tmpfile` erstellt eine temporäre Datei und gibt diesem Stream einen Zeiger zurück. Die temporäre Datei wird im Stammverzeichnis erstellt. Verwenden Sie zum Erstellen einer temporären Datei in einem anderen Verzeichnis als dem Stammverzeichnis [tmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md) oder [tempnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md) in Verbindung mit [fopen](../../c-runtime-library/reference/fopen-wfopen.md).  
  
 Wenn die Datei nicht geöffnet werden kann, gibt `tmpfile` einen `NULL`-Zeiger zurück. Diese temporäre Datei wird automatisch gelöscht, wenn die Datei geschlossen wird, wenn das Programm normal beendet wird oder wenn `_rmtmp` aufgerufen wird, vorausgesetzt, dass sich das aktuelle Arbeitsverzeichnis nicht ändert. Die temporäre Datei wird im (binären Lese-/Schreib-) Modus `w+b` geöffnet.  
  
 Ein Fehler kann auftreten, wenn Sie mehr als TMP_MAX (siehe STDIO.H) Aufrufe mit `tmpfile` versuchen.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`tmpfile`|\<stdio.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
  
> [!NOTE]
>  Für dieses Beispiel benötigen Sie Administratorrechte, um es unter Windows Vista auszuführen.  
  
```  
// crt_tmpfile.c  
// compile with: /W3  
// This program uses tmpfile to create a  
// temporary file, then deletes this file with _rmtmp.  
#include <stdio.h>  
  
int main( void )  
{  
   FILE *stream;  
   int  i;  
  
   // Create temporary files.  
   for( i = 1; i <= 3; i++ )  
   {  
      if( (stream = tmpfile()) == NULL ) // C4996  
      // Note: tmpfile is deprecated; consider using tmpfile_s instead  
         perror( "Could not open new temporary file\n" );  
      else  
         printf( "Temporary file %d was created\n", i );  
   }  
  
   // Remove temporary files.  
   printf( "%d temporary files deleted\n", _rmtmp() );  
}  
```  
  
```Output  
Temporary file 1 was created  
Temporary file 2 was created  
Temporary file 3 was created  
3 temporary files deleted  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Stream-E/A](../../c-runtime-library/stream-i-o.md)   
 [_rmtmp](../../c-runtime-library/reference/rmtmp.md)   
 [_tempnam, _wtempnam, tmpnam, _wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)
