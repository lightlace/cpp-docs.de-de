---
title: fgets, fgetws | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- fgets
- fgetws
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
- _fgetts
- fgetws
- fgets
dev_langs: C++
helpviewer_keywords:
- _fgetts function
- streams, getting strings from
- streams, reading from
- fgets function
- fgetws function
- fgetts function
ms.assetid: ad549bb5-df98-4ccd-a53f-95114e60c4fc
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 70cccdc8dea6abb032fbf6170ca84ad866ddd491
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="fgets-fgetws"></a>fgets, fgetws
Ruft eine Zeichenfolge aus einem Stream ab  
  
## <a name="syntax"></a>Syntax  
  
```  
char *fgets(   
   char *str,  
   int n,  
   FILE *stream   
);  
wchar_t *fgetws(   
   wchar_t *str,  
   int n,  
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `str`  
 Speicherort für Daten.  
  
 `n`  
 Die maximale Anzahl der zu lesenden Zeichen  
  
 `stream`  
 Zeiger zur `FILE` -Struktur.  
  
## <a name="return-value"></a>Rückgabewert  
 Jede dieser Funktion gibt `str` zurück. `NULL` wird zurückgegeben, um einen Fehler oder eine Dateiendebedingung anzugeben. Verwenden Sie `feof` oder `ferror`, um zu bestimmen, ob ein Fehler aufgetreten ist. Wenn `str` oder `stream` ein NULL-Zeiger sind oder `n` kleiner gleich null ist, ruft diese Funktion einen Handler für ungültige Parameter auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, wird `errno` auf `EINVAL` gesetzt, und die Funktion gibt `NULL`zurück.  
  
 Weitere Informationen zu diesen und anderen Fehlercodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Hinweise  
 Die Funktion `fgets` liest eine Zeichenfolge aus dem `stream`-Argument der Eingabe und speichert es in `str`. `fgets`Liest Zeichen aus der aktuellen Streamposition bis einschließlich des ersten Zeilenumbruchzeichens bis zum Ende des Streams oder bis die Anzahl der gelesenen Zeichen entspricht `n` - 1, je nachdem, was zuerst eintritt. Dem in `str` gespeicherte Ergebnis wird ein Zeichen NULL angefügt. Das Zeilenumbruchzeichen wird, wenn es gelesen wird, in die Zeichenfolge aufgenommen.  
  
 `fgetws` ist eine Breitzeichenversion von `fgets`.  
  
 `fgetws` liest das Breitzeichenargument `str` als Multibyte-oder Breitzeichen-Zeichenfolge. Die Zeichenfolgenart wird dadurch bestimmt, ob `stream` im Textmodus oder Binärmodus geöffnet ist. Weitere Informationen zur Anwendung von Text- und Binärmodi in Unicode- und Multibyte-Stream-E/A finden Sie unter [Text- und Binärmodus-Datei-E/A](../../c-runtime-library/text-and-binary-mode-file-i-o.md) und [Unicode-Stream-E/A in Text- und Binärmodi](../../c-runtime-library/unicode-stream-i-o-in-text-and-binary-modes.md).  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_fgetts`|`fgets`|`fgets`|`fgetws`|  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------|  
|`fgets`|\<stdio.h>|  
|`fgetws`|\<stdio.h> oder \<wchar.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_fgets.c  
// This program uses fgets to display  
// a line from a file on the screen.  
//  
  
#include <stdio.h>  
  
int main( void )  
{  
   FILE *stream;  
   char line[100];  
  
   if( fopen_s( &stream, "crt_fgets.txt", "r" ) == 0 )  
   {  
      if( fgets( line, 100, stream ) == NULL)  
         printf( "fgets error\n" );  
      else  
         printf( "%s", line);  
      fclose( stream );  
   }  
}  
```  
  
## <a name="input-crtfgetstxt"></a>Eingabe: crt_fgets.txt  
  
```  
Line one.  
Line two.  
```  
  
### <a name="output"></a>Ausgabe  
  
```  
Line one.  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Stream-E/A](../../c-runtime-library/stream-i-o.md)   
 [fputs, fputws](../../c-runtime-library/reference/fputs-fputws.md)   
 [gets, _getws](../../c-runtime-library/gets-getws.md)   
 [puts, _putws](../../c-runtime-library/reference/puts-putws.md)