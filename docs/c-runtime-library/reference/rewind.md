---
title: rewind | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: rewind
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
f1_keywords: rewind
dev_langs: C++
helpviewer_keywords:
- rewind function
- repositioning file pointers
- file pointers [C++], repositioning
- file pointers [C++]
ms.assetid: 1a460ce1-28d8-4b5e-83a6-633dca29c28a
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 78cb2d761e7625dac7073927b7b7f1a06fcf1759
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="rewind"></a>rewind
Setzt den Dateizeiger einer Datei wieder an den Anfang.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      void rewind(  
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `stream`  
 Zeiger auf die **FILE**-Struktur.  
  
## <a name="remarks"></a>Hinweise  
 Die Funktion **rewind** verschiebt den Dateizeiger, der `stream` dem Anfang der Datei zuordnet. Der Aufruf **rewind** ist vergleichbar mit  
  
 **(void) fseek(** `stream`**, 0L,** `SEEK_SET` **);**  
  
 Im Unterschied zu `fseek` löscht **rewind** die Fehlerindikatoren für den Stream und für den Dateiendeindikator. Im Unterschied zu `fseek` gibt **rewind** keinen Wert zurück, der anzeigt, ob der Zeiger erfolgreich verschoben wurde.  
  
 Um den Tastaturpuffer zu löschen, verwenden Sie **rewind** mit dem Datenstrom `stdin`, der der Tastatur standardmäßig zugeordnet ist.  
  
 Wenn Stream ein `NULL`-Zeiger ist, wird der ungültige Parameterhandler aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, wird diese Funktion zurückgegeben und `errno` auf `EINVAL` festgesetzt.  
  
 Weitere Informationen über diese und andere Fehlercodes finden Sie unter [_doserrno, errno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|**rewind**|\<stdio.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="libraries"></a>Bibliotheken  
 Alle Versionen [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_rewind.c  
/* This program first opens a file named  
 * crt_rewind.out for input and output and writes two  
 * integers to the file. Next, it uses rewind to  
 * reposition the file pointer to the beginning of  
 * the file and reads the data back in.  
 */  
#include <stdio.h>  
  
int main( void )  
{  
   FILE *stream;  
   int data1, data2;  
  
   data1 = 1;  
   data2 = -37;  
  
   fopen_s( &stream, "crt_rewind.out", "w+" );  
   if( stream != NULL )  
   {  
      fprintf( stream, "%d %d", data1, data2 );  
      printf( "The values written are: %d and %d\n", data1, data2 );  
      rewind( stream );  
      fscanf_s( stream, "%d %d", &data1, &data2 );  
      printf( "The values read are: %d and %d\n", data1, data2 );  
      fclose( stream );  
   }  
}  
```  
  
## <a name="output"></a>Ausgabe  
  
```  
The values written are: 1 and -37  
The values read are: 1 and -37  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Stream-E/A](../../c-runtime-library/stream-i-o.md)