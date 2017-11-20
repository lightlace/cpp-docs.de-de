---
title: tmpnam_s, _wtmpnam_s | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- tmpnam_s
- _wtmpnam_s
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
- tmpnam_s
- _wtmpnam_s
- L_tmpnam_s
dev_langs: C++
helpviewer_keywords:
- tmpnam_s function
- file names [C++], creating temporary
- _wtmpnam_s function
- L_tmpnam_s constant
- temporary files, creating
- file names [C++], temporary
- wtmpnam_s function
ms.assetid: e70d76dc-49f5-4aee-bfa2-f1baa2bcd29f
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b19cbd69d5045ee51b3a1a8ae621300b0ba4b545
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="tmpnams-wtmpnams"></a>tmpnam_s, _wtmpnam_s
Generiert Namen, die Sie verwenden können, um temporäre Dateien zu erstellen. Dabei handelt es sich um Versionen von [tmpnam und _wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md) mit den unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschriebenen Erweiterungen.  
  
## <a name="syntax"></a>Syntax  
  
```  
errno_t tmpnam_s(  
   char * str,  
   size_t sizeInChars   
);  
errno_t _wtmpnam_s(  
   wchar_t *str,  
   size_t sizeInChars   
);  
template <size_t size>  
errno_t tmpnam_s(  
   char (&str)[size]  
); // C++ only  
template <size_t size>  
errno_t _wtmpnam_s(  
   wchar_t (&str)[size]  
); // C++ only  
```  
  
#### <a name="parameters"></a>Parameter  
 [out] `str`  
 Zeiger, der den generierten Namen enthalten wird.  
  
 [in] `sizeInChars`  
 Größe des Puffers in Zeichen.  
  
## <a name="return-value"></a>Rückgabewert  
 Beide Funktionen geben bei Erfolg 0 zurück und bei einem Fehler eine Fehlernummer zurück.  
  
### <a name="error-conditions"></a>Fehlerbedingungen  
  
|||||  
|-|-|-|-|  
|`str`|`sizeInChars`|**Rückgabewert**|**Inhalt** `str`|  
|`NULL`|alle|`EINVAL`|nicht geändert|  
|nicht `NULL` (verweist auf gültigen Speicher)|zu kurz|`ERANGE`|nicht geändert|  
  
 Wenn `str` `NULL` ist, wird der ungültige Parameterhandler wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben aufgerufen. Wenn die weitere Ausführung zugelassen wird, stellen diese Funktionen `errno` auf `EINVAL` ein und geben `EINVAL` zurück.  
  
## <a name="remarks"></a>Hinweise  
 Jede dieser Funktionen gibt den Namen einer Datei zurück, die derzeit nicht vorhanden ist. `tmpnam_s` gibt einen Namen zurück, der im aktuellen Arbeitsverzeichnis nur einmal vorkommt. Wenn einem Dateinamen ohne Pfadinformationen ein umgekehrter Schrägstrich vorangestellt ist wie z.B. \fname21, weist dies darauf hin, dass der Name für das aktuelle Arbeitsverzeichnis gültig ist.  
  
 Für `tmpnam_s` können Sie diesen generierten Dateinamen in `str` speichern. Die maximale Länge einer Zeichenfolge, die von `tmpnam_s` zurückgegeben wird, ist `L_tmpnam_s`, definiert in STDIO.H. Wenn `str` `NULL` ist, dann hinterlässt `tmpnam_s` das Ergebnis in einem internen statischen Puffer. Alle nachfolgenden Aufrufe zerstören deshalb diesen Wert. Der von `tmpnam_s` generierte Name besteht aus einem vom Programm generierten Dateinamen und nach dem ersten Aufruf von `tmpnam_s` aus einer Dateierweiterung aus aufeinanderfolgenden Zahlen mit Basis 32 (.1-.1vvvvvu wenn `TMP_MAX_S` in STDIO.H INT_MAX ist).  
  
 `tmpnam_s` behandelt Multibyte-Zeichenfolgenargumente automatisch als richtig. Die Erkennung von Multibyte-Zeichenfolgen erfolgt auf der Grundlage der Codepage des OEM aus dem Betriebssystem. `_wtmpnam_s` ist eine Breitzeichenversion von `tmpnam_s`. Das Argument und der Rückgabewert von `_wtmpnam_s` sind Zeichenfolgen mit Breitzeichen. `_wtmpnam_s` und `tmpnam_s` verhalten sich identisch, mit dem Unterschied, dass `_wtmpnam_s` keine Multibyte-Zeichenfolgen verarbeitet.  
  
 Die Verwendung dieser Funktionen in C++ wird durch Überladungen (als Vorlagen vorhanden) vereinfacht. Überladungen können automatisch die Pufferlänge ableiten, sodass kein Größenargument angegeben werden muss. Weitere Informationen finden Sie unter [Secure Template Overloads (Sichere Vorlagenüberladungen)](../../c-runtime-library/secure-template-overloads.md).  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_ttmpnam_s`|`tmpnam_s`|`tmpnam_s`|`_wtmpnam_s`|  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`tmpnam_s`|\<stdio.h>|  
|`_wtmpnam_s`|\<stdio.h> oder \<wchar.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_tmpnam_s.c  
// This program uses tmpnam_s to create a unique filename in the  
// current working directory.   
//  
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{     
   char name1[L_tmpnam_s];  
   errno_t err;  
   int i;  
  
   for (i = 0; i < 15; i++)  
   {  
      err = tmpnam_s( name1, L_tmpnam_s );  
      if (err)  
      {  
         printf("Error occurred creating unique filename.\n");  
         exit(1);  
      }  
      else  
      {  
         printf( "%s is safe to use as a temporary file.\n", name1 );  
      }  
   }    
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Stream-E/A](../../c-runtime-library/stream-i-o.md)   
 [_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [tmpfile_s](../../c-runtime-library/reference/tmpfile-s.md)