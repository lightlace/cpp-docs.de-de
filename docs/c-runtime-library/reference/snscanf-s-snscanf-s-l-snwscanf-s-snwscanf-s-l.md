---
title: "_snscanf_s, _snscanf_s_l, _snwscanf_s, _snwscanf_s_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_snwscanf_s_l"
  - "_snwscanf_s"
  - "_snscanf_s"
  - "_snscanf_s_l"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_sntscanf_s"
  - "snscanf_s"
  - "_snwscanf_s_l"
  - "sntscanf_s_l"
  - "snwscanf_s_l"
  - "snwscanf_s"
  - "_snscanf_s"
  - "_snwscanf_s"
  - "snscanf_s_l"
  - "_sntscanf_s_l"
  - "_snscanf_s_l"
  - "sntscanf_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_snscanf_s-Funktion"
  - "_snscanf_s_l-Funktion"
  - "_sntscanf_s-Funktion"
  - "_sntscanf_s_l-Funktion"
  - "_snwscanf_s-Funktion"
  - "_snwscanf_s_l-Funktion"
  - "Lesen von Daten, Zeichenfolgen"
  - "snscanf_s-Funktion"
  - "snscanf_s_l-Funktion"
  - "sntscanf_s-Funktion"
  - "sntscanf_s_l-Funktion"
  - "snwscanf_s-Funktion"
  - "snwscanf_s_l-Funktion"
  - "Zeichenfolgen [C++], Lesen"
  - "Zeichenfolgen [C++], Lesen von Daten aus"
ms.assetid: 72356653-7362-461a-af73-597b9c0a8094
caps.latest.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 24
---
# _snscanf_s, _snscanf_s_l, _snwscanf_s, _snwscanf_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Liest formatierte Daten einer angegebenen Länge von einer Zeichenfolge.  Diese Versionen von [\_snscanf, \_snscanf\_l, \_snwscanf, \_snwscanf\_l](../../c-runtime-library/reference/snscanf-snscanf-l-snwscanf-snwscanf-l.md) enthalten Sicherheitserweiterungen wie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
## Syntax  
  
```  
int __cdecl _snscanf_s(  
   const char * input,  
   size_t length,  
   const char * format,  
   ...  
);  
int __cdecl _snscanf_s_l(  
   const char * input,  
   size_t length,  
   const char * format,  
   locale_t locale,  
   ...  
);  
int __cdecl _snwscanf_s(  
   const wchar_t * input,  
   size_t length,  
   const wchar_t * format,  
   ...  
);  
int __cdecl _snwscanf_s_l(  
   const wchar_t * input,  
   size_t length,  
   const wchar_t * format,  
   locale_t locale,  
   …  
);  
```  
  
#### Parameter  
 `input`  
 So überprüfen Eingabezeichenfolge.  
  
 `length`  
 Zahl in `input` zu überprüfen, Zeichen.  
  
 `format`  
 Mindestens ein Formatbezeichner.  
  
 `... (optional)`  
 Variablen, die verwendet werden, um Werte zu speichern, extrahierten der Eingabezeichenfolge von die Formatbezeichner in `format`.  
  
 `locale`  
 Das zu verwendende Gebietsschema.  
  
## Rückgabewert  
 Beide Funktionen gibt die Anzahl der erfolgreichen konvertierten und zugewiesenen Felder zurück; der Rückgabewert enthält Felder, die nicht gelesen wurden, jedoch nicht zugewiesen.  Ein Rückgabewert von 0 gibt an, dass keine Felder zugewiesen wurden.  Der Rückgabewert bei einem Fehler oder beim Erreichen des Endes der Zeichenfolge vor der ersten Konvertierung lautet `EOF`.  Weitere Informationen finden Sie unter [sscanf\_s, \_sscanf\_s\_l, swscanf\_s, \_swscanf\_s\_l](../../c-runtime-library/reference/sscanf-s-sscanf-s-l-swscanf-s-swscanf-s-l.md).  
  
 Wenn `input` oder `format` ein `NULL`\-Zeiger ist, wird, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben, der Handler für ungültige Parameter aufgerufen.  Wenn die weitere Ausführung zugelassen wird, geben diese Funktionen `EOF` zurück und stellen `errno` auf `EINVAL` ein.  
  
 Weitere Informationen über diese und andere Fehlercodes finden Sie unter [\_doserrno, errno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 Diese Funktion entspricht `sscanf_s`, außer dass sie bietet die Möglichkeit, einer festen Anzahl von Zeichen an, aus der Eingabezeichenfolge zu überprüfen.  Weitere Informationen finden Sie unter [sscanf\_s, \_sscanf\_s\_l, swscanf\_s, \_swscanf\_s\_l](../../c-runtime-library/reference/sscanf-s-sscanf-s-l-swscanf-s-swscanf-s-l.md).  
  
 Der Puffergrößenparameter ist den Typfeldzeichen `c`, `C`, `s`, `S` und `[` erfordert.  Weitere Informationen finden Sie unter [scanf\-Typenfeldzeichen](../../c-runtime-library/scanf-type-field-characters.md).  
  
> [!NOTE]
>  Der Größenparameter ist vom Typ `unsigned` und nicht vom Typ `size_t`.  
  
 Die Versionen dieser Funktionen mit dem `_l`\-Suffix sind beinahe identisch, verwenden jedoch den ihnen übergebenen Gebietsschemaparameter anstelle des aktuellen Threadgebietsschemas.  
  
### Zuordnung generischer Textroutinen  
  
|Tchar.h\-Routine|\_UNICODE und \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|------------------------------------------|----------------------|-------------------------|  
|`_sntscanf_s`|`_snscanf_s`|`_snscanf_s`|`_snwscanf_s`|  
|`_sntscanf_s_l`|`_snscanf_s_l`|`_snscanf_s_l`|`_snwscanf_s_l`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_snscanf_s`, \_`snscanf_s_l`|\<stdio.h\>|  
|`_snwscanf_s`, `_snwscanf_s_l`|\<stdio.h\> oder \<wchar.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_snscanf_s.c  
// This example scans a string of   
// numbers, using both the character  
// and wide character secure versions  
// of the snscanf function.  
  
#include <stdio.h>  
  
int main( )  
{  
    char        str1[] = "15 12 14...";  
    wchar_t     str2[] = L"15 12 14...";  
    char        s1[3];  
    wchar_t     s2[3];  
    int         i;  
    float       fp;  
  
    i = _snscanf_s( str1, 6,  "%s %f", s1, 3, &fp);  
    printf_s("_snscanf_s converted %d fields: ", i);  
    printf_s("%s and %f\n", s1, fp);  
  
    i = _snwscanf_s( str2, 6,  L"%s %f", s2, 3, &fp);  
    wprintf_s(L"_snwscanf_s converted %d fields: ", i);  
    wprintf_s(L"%s and %f\n", s2, fp);  
}  
```  
  
  **\_snscanf\_s konvertierten 2 Felder: 15 und 12,000000**  
**\_snwscanf\_s konvertierten 2 Felder: 15 und 12,000000**   
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [scanf\-Breitenangabe](../../c-runtime-library/scanf-width-specification.md)