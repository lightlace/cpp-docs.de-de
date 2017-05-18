---
title: fgetpos | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- fgetpos
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
- fgetpos
dev_langs:
- C++
helpviewer_keywords:
- fgetpos function
- streams, file position indicator
ms.assetid: bfa05c38-1135-418c-bda1-d41be51acb62
caps.latest.revision: 14
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
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: c53e5742a518934ad0afcfaa06ad4e5905c484e3
ms.contentlocale: de-de
ms.lasthandoff: 03/29/2017

---
# <a name="fgetpos"></a>fgetpos
Ruft den Dateipositionsindikator eines Streams ab  
  
## <a name="syntax"></a>Syntax  
  
```  
int fgetpos(   
   FILE *stream,  
   fpos_t *pos   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `stream`  
 Der Zielstream  
  
 `pos`  
 Speicher des Positionsindikators  
  
## <a name="return-value"></a>Rückgabewert  
 `fgetpos` gibt bei Erfolg 0 zurück. Bei einem Fehler wird ein Wert ungleich 0 zurückgegeben und `errno` auf eine der folgenden Manifestkonstanten festgelegt (definiert in STDIO.H): `EBADF`, d.h., der angegebene Stream ist kein gültiger Dateizeiger oder nicht zugreifbar, oder `EINVAL`, d.h., dass die Werte `stream` und `pos` ungültig sind, als wären beide ein NULL-Zeiger. Wenn `stream` oder `pos` ein `NULL`-Zeiger sind, ruft die Funktion, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben, den Handler für ungültige Parameter auf.  
  
## <a name="remarks"></a>Hinweise  
 Die Funktion `fgetpos` ruft den aktuellen Wert des Dateipositionsindikators des `stream`-Arguments ab und speichert es in dem Objekt, auf das `pos` verweist. Die Funktion `fsetpos` kann die in `pos` gespeicherten Informationen später verwenden, um den Zeiger des `stream`-Arguments auf die Position zurückzusetzen, die er zum Zeitpunkt des Aufrufs von `fgetpos` inne hatte. Der Wert `pos` wird in einem internen Format gespeichert und dient nur zur Verwendung durch `fgetpos` und `fsetpos`.  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------|  
|`fgetpos`|\<stdio.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_fgetpos.c  
// This program uses fgetpos and fsetpos to  
// return to a location in a file.  
  
#include <stdio.h>  
  
int main( void )  
{  
   FILE   *stream;  
   fpos_t pos;  
   char   buffer[20];  
  
   if( fopen_s( &stream, "crt_fgetpos.txt", "rb" ) ) {  
      perror( "Trouble opening file" );  
      return -1;  
   }  
  
   // Read some data and then save the position.   
   fread( buffer, sizeof( char ), 8, stream );  
   if( fgetpos( stream, &pos ) != 0 ) {  
      perror( "fgetpos error" );  
      return -1;  
   }  
  
   fread( buffer, sizeof( char ), 13, stream );  
   printf( "after fgetpos: %.13s\n", buffer );  
  
   // Restore to old position and read data   
   if( fsetpos( stream, &pos ) != 0 ) {  
      perror( "fsetpos error" );  
      return -1;  
   }  
  
   fread( buffer, sizeof( char ), 13, stream );  
   printf( "after fsetpos: %.13s\n", buffer );  
   fclose( stream );  
}  
```  
  
## <a name="input-crtfgetpostxt"></a>Eingabe: crt_fgetpos.txt  
  
```  
fgetpos gets a stream's file-position indicator.  
```  
  
### <a name="output-crtfgetpostxt"></a>Ausgabe: crt_fgetpos.txt  
  
```  
after fgetpos: gets a stream  
after fsetpos: gets a stream  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Stream-E/A](../../c-runtime-library/stream-i-o.md)   
 [fsetpos](../../c-runtime-library/reference/fsetpos.md)
