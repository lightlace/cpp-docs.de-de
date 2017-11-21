---
title: vfscanf, vfwscanf | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- vfwscanf
- vfscanf
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
f1_keywords:
- vfwscanf
- _vftscanf
- vfscanf
dev_langs: C++
ms.assetid: c06450ef-03f1-4d24-a8ac-d2dd98847918
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ebb7c268f5f721fce3ce4d6aee4175cd2484fb05
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="vfscanf-vfwscanf"></a>vfscanf, vfwscanf
Liest formatierte Daten aus einem Stream. Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [vfscanf_s, vfwscanf_s](../../c-runtime-library/reference/vfscanf-s-vfwscanf-s.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
int vfscanf(   
   FILE *stream,  
   const char *format,  
   va_list argptr   
);  
int vfwscanf(   
   FILE *stream,  
   const wchar_t *format,  
   va_list argptr   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `stream`  
 Zeiger zur `FILE` -Struktur.  
  
 `format`  
 Formatsteuerzeichenfolge.  
  
 `arglist`  
 Variablenargumentenliste.  
  
## <a name="return-value"></a>Rückgabewert  
 Jede dieser Funktionen gibt die Anzahl der Felder zurück, die erfolgreich konvertiert und zugewiesen wurden; der Rückgabewert umfasst keine Felder, die gelesen, aber nicht zugewiesen wurden. Ein Rückgabewert von 0 gibt an, dass keine Felder zugewiesen wurden. Wenn ein Fehler auftritt oder das Ende des Dateistreams vor der ersten Konvertierung erreicht wird, ist der Rückgabewert `EOF` für `vfscanf` und `vfwscanf`.  
  
 Diese Funktionen überprüfen ihre Parameter. Wenn `stream` oder `format` ein NULL-Zeiger ist, wird der Handler für ungültige Parameter aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, geben diese Funktionen `EOF` zurück und stellen `errno` auf `EINVAL` ein.  
  
## <a name="remarks"></a>Hinweise  
 Die `vfscanf`-Funktion liest Daten aus der aktuellen Position von `stream` in die Speicherorte ein, die von der `arglist`-Argumentliste angegeben werden. Jedes Argument in der Liste muss ein Zeiger auf einen Variablentyp sein, der einem Typspezifizierer in `format` entspricht. `format` steuert die Interpretation der Eingabefelder und hat die gleiche Form und Funktion wie das `format`-Argument für `scanf`. Unter [scanf](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md) finden Sie eine Beschreibung von `format`.  
  
 `vfwscanf` ist eine Breitzeichenversion von `vfscanf`. Das `vfwscanf`-Formatargument ist eine Breitzeichenfolge. Diese Funktionen verhalten sich identisch, wenn der Stream im ANSI-Modus geöffnet ist. `vfscanf` unterstützt nicht die Eingabe aus einem UNICODE-Stream.  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_vftscanf`|`vfscanf`|`vfscanf`|`vfwscanf`|  
  
 Weitere Informationen finden Sie unter [Format Specification Fields: scanf and wscanf Functions (Formatspezifikationsfelder: Funktionen scanf und wscanf)](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md).  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------|  
|`vfscanf`|\<stdio.h>|  
|`vfwscanf`|\<stdio.h> oder \<wchar.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_vfscanf.c  
// compile with: /W3  
// This program writes formatted  
// data to a file. It then uses vfscanf to  
// read the various data back from the file.  
  
#include <stdio.h>  
#include <stdarg.h>  
  
FILE *stream;  
  
int call_vfscanf(FILE * istream, char * format, ...)  
{  
    int result;  
    va_list arglist;  
    va_start(arglist, format);  
    result = vfscanf(istream, format, arglist);  
    va_end(arglist);  
    return result;  
}  
  
int main(void)  
{  
    long l;  
    float fp;  
    char s[81];  
    char c;  
  
    if (fopen_s(&stream, "vfscanf.out", "w+") != 0)  
    {  
        printf("The file vfscanf.out was not opened\n");  
    }  
    else  
    {  
        fprintf(stream, "%s %ld %f%c", "a-string",  
            65000, 3.14159, 'x');  
        // Security caution!  
        // Beware loading data from a file without confirming its size,  
        // as it may lead to a buffer overrun situation.  
  
        // Set pointer to beginning of file:  
        fseek(stream, 0L, SEEK_SET);  
  
        // Read data back from file:  
        call_vfscanf(stream, "%s %ld %f%c", s, &l, &fp, &c);  
  
        // Output data read:   
        printf("%s\n", s);  
        printf("%ld\n", l);  
        printf("%f\n", fp);  
        printf("%c\n", c);  
  
        fclose(stream);  
    }  
}  
  
```  
  
```Output  
a-string  
65000  
3.141590  
x  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Stream-E/A](../../c-runtime-library/stream-i-o.md)   
 [_cscanf, _cscanf_l, _cwscanf, _cwscanf_l](../../c-runtime-library/reference/cscanf-cscanf-l-cwscanf-cwscanf-l.md)   
 [fprintf, _fprintf_l, fwprintf, _fwprintf_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [scanf, _scanf_l, wscanf, _wscanf_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [sscanf, _sscanf_l, swscanf, _swscanf_l](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)   
 [fscanf_s, _fscanf_s_l, fwscanf_s, _fwscanf_s_l](../../c-runtime-library/reference/fscanf-s-fscanf-s-l-fwscanf-s-fwscanf-s-l.md)   
 [vfscanf_s, vfwscanf_s](../../c-runtime-library/reference/vfscanf-s-vfwscanf-s.md)