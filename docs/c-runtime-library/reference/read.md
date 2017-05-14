---
title: _read | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _read
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
- _read
dev_langs:
- C++
helpviewer_keywords:
- data [CRT]
- _read function
- read function
- data [C++], reading
- reading data [C++]
- files [C++], reading
ms.assetid: 2ce9c433-57ad-47fe-9ac1-4a7d4c883d30
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 6387edb05977f90fe9fb2419a1eccb47ac0b7b43
ms.contentlocale: de-de
ms.lasthandoff: 04/01/2017

---
# <a name="read"></a>_read
Liest Daten aus einer Datei.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      int _read(  
   int fd,  
   void *buffer,  
   unsigned int count   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `fd`  
 Dateideskriptor, der auf die geöffnete Datei verweist.  
  
 *buffer*  
 Speicherort für Daten.  
  
 *count*  
 Die maximale Anzahl von Bytes.  
  
## <a name="return-value"></a>Rückgabewert  
 _**lesen** gibt die Anzahl der Bytes, die gelesen, die kann geringer sein als *Anzahl* Wenn weniger als *Anzahl* Bytes Links in der Datei, oder wenn die Datei im Textmodus geöffnet wurde, wobei jede Wagenrücklauf-(CR-LF) Paar Zeilenvorschub wird durch ein einzelnes Zeilenvorschubzeichen ersetzt. Nur das einzelne Zeilenvorschubzeichen wird im Rückgabewert gezählt. Der Ersatz hat keine Auswirkung auf den Rückgabezeiger.  
  
 Wenn die Funktion versucht, am Ende der Datei zu lesen, wird 0 zurückgegeben. Wenn `fd` ungültig ist, kann die Datei nicht zum Lesen geöffnet werden, oder sie ist gesperrt und der ungültige Parameterhandler wird aufgerufen, wie unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, gibt die Funktion -1 zurück und stellt `errno` auf `EBADF`ein.  
  
 Wenn *buffer* **NULL** ist, wird der ungültige Parameterhandler aufgerufen. Wenn die weitere Ausführung zugelassen wird, gibt die Funktion –1 zurück und setzt `errno` auf `EINVAL`.  
  
 Weitere Informationen zu diesem und anderen Rückgabecodes finden Sie unter [_doserrno, errno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Hinweise  
 Die `_read`-Funktion liest maximal *count*-Bytes in *buffer* aus der `fd` zugeordneten Datei. Der Lesevorgang beginnt an der aktuellen Position des Dateizeigers für die betreffende Datei. Nach dem Lesevorgang zeigt der Dateizeiger auf das nächste ungelesene Zeichen.  
  
 Wenn die Datei im Textmodus geöffnet wurde, wird der Lesevorgang beendet, wenn `_read` ein STRG + Z-Zeichen findet, das als Dateiende-Indikator behandelt wird. Verwenden Sie [_lseek](../../c-runtime-library/reference/lseek-lseeki64.md), um den Dateiende-Indikator zu löschen.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_read`|\<io.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="libraries"></a>Bibliotheken  
 Alle Versionen der [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_read.c  
/* This program opens a file named crt_read.txt  
 * and tries to read 60,000 bytes from  
 * that file using _read. It then displays the  
 * actual number of bytes read.  
 */  
  
#include <fcntl.h>      /* Needed only for _O_RDWR definition */  
#include <io.h>  
#include <stdlib.h>  
#include <stdio.h>  
#include <share.h>  
  
char buffer[60000];  
  
int main( void )  
{  
   int fh;  
   unsigned int nbytes = 60000, bytesread;  
  
   /* Open file for input: */  
   if( _sopen_s( &fh, "crt_read.txt", _O_RDONLY, _SH_DENYNO, 0 ) )  
   {  
      perror( "open failed on input file" );  
      exit( 1 );  
   }  
  
   /* Read in input: */  
   if( ( bytesread = _read( fh, buffer, nbytes ) ) <= 0 )  
      perror( "Problem reading file" );  
   else  
      printf( "Read %u bytes from file\n", bytesread );  
  
   _close( fh );  
}  
```  
  
## <a name="input-crtreadtxt"></a>Eingabe: crt_read.txt  
  
```  
Line one.  
Line two.  
```  
  
## <a name="output"></a>Ausgabe  
  
```  
Read 19 bytes from file  
```  
  
## <a name="see-also"></a>Siehe auch  
 [E/A auf niedriger Ebene](../../c-runtime-library/low-level-i-o.md)   
 [_creat, _wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [fread](../../c-runtime-library/reference/fread.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_write](../../c-runtime-library/reference/write.md)
