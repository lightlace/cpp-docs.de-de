---
title: "_snscanf, _snscanf_l, _snwscanf, _snwscanf_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_snwscanf"
  - "_snscanf_l"
  - "_snscanf"
  - "_snwscanf_l"
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
  - "_snscanf"
  - "_snscanf_l"
  - "_snwscanf"
  - "snscanf_l"
  - "snscanf"
  - "_sntscanf_l"
  - "_sntscanf"
  - "_snwscanf_l"
  - "sntscanf_l"
  - "sntscanf"
  - "snwscanf"
  - "snwscanf_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_snscanf-Funktion"
  - "_snscanf_l-Funktion"
  - "_sntscanf-Funktion"
  - "_sntscanf_l-Funktion"
  - "_snwscanf-Funktion"
  - "_snwscanf_l-Funktion"
  - "Lesen von Daten, Zeichenfolgen"
  - "snscanf-Funktion"
  - "snscanf_l-Funktion"
  - "sntscanf-Funktion"
  - "sntscanf_l-Funktion"
  - "snwscanf-Funktion"
  - "snwscanf_l-Funktion"
  - "Zeichenfolgen [C++], Lesen"
  - "Zeichenfolgen [C++], Lesen von Daten aus"
ms.assetid: da1ac890-f905-4cd7-954b-3c90957b5551
caps.latest.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 24
---
# _snscanf, _snscanf_l, _snwscanf, _snwscanf_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Liest formatierte Daten einer angegebenen Länge von einer Zeichenfolge.  Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [\_snscanf\_s, \_snscanf\_s\_l, \_snwscanf\_s, \_snwscanf\_s\_l](../../c-runtime-library/reference/snscanf-s-snscanf-s-l-snwscanf-s-snwscanf-s-l.md).  
  
## Syntax  
  
```  
int __cdecl _snscanf(  
   const char * input,  
   size_t length,  
   const char * format,  
   ...  
);  
int __cdecl _snscanf_l(  
   const char * input,  
   size_t length,  
   const char * format,  
   locale_t locale,  
   ...  
);  
int __cdecl _snwscanf(  
   const wchar_t * input,  
   size_t length,  
   const wchar_t * format,  
   ...  
);  
int __cdecl _snwscanf_l(  
   const wchar_t * input,  
   size_t length,  
   const wchar_t * format,  
   locale_t locale,  
   ...  
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
 Beide Funktionen gibt die Anzahl der erfolgreichen konvertierten und zugewiesenen Felder zurück; der Rückgabewert enthält Felder, die nicht gelesen wurden, jedoch nicht zugewiesen.  Ein Rückgabewert von 0 gibt an, dass keine Felder zugewiesen wurden.  Der Rückgabewert bei einem Fehler oder beim Erreichen des Endes der Zeichenfolge vor der ersten Konvertierung lautet `EOF`.  Weitere Informationen finden Sie unter [sscanf](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md).  
  
 Wenn `input` oder `format` ein `NULL` Zeiger ist oder wenn `length` kleiner oder gleich null ist, wird der ungültige Parameterhandler aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, geben diese Funktionen `EOF` zurück und stellen `errno` auf `EINVAL` ein.  
  
 Weitere Informationen über diese und andere Fehlercodes finden Sie unter [\_doserrno, errno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 Diese Funktion entspricht `sscanf`, außer dass sie bietet die Möglichkeit, einer festen Anzahl von Zeichen an, aus der Eingabezeichenfolge zu überprüfen.  Weitere Informationen finden Sie unter [sscanf](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md).  
  
 Die Versionen dieser Funktionen mit dem `_l`\-Suffix sind beinahe identisch, verwenden jedoch den ihnen übergebenen Gebietsschemaparameter anstelle des aktuellen Threadgebietsschemas.  
  
### Zuordnung generischer Textroutinen  
  
|Tchar.h\-Routine|\_UNICODE und \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|------------------------------------------|----------------------|-------------------------|  
|`_sntscanf`|`_snscanf`|`_snscanf`|`_snwscanf`|  
|`_sntscanf_l`|`_snscanf_l`|`_snscanf_l`|`_snwscanf_l`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_snscanf`, `_snscanf_l`|\<stdio.h\>|  
|`_snwscanf`, `_snwscanf_l`|\<stdio.h\> oder \<wchar.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_snscanf.c  
// compile with: /W3  
  
#include <stdio.h>  
int main( )  
{  
   char  str1[] = "15 12 14...";  
   wchar_t  str2[] = L"15 12 14...";  
   char  s1[3];  
   wchar_t  s2[3];  
   int   i;  
   float fp;  
  
   i = _snscanf( str1, 6,  "%s %f", s1, &fp); // C4996  
   // Note: _snscanf is deprecated; consider using _snscanf_s instead  
   printf("_snscanf converted %d fields: ", i);  
   printf("%s and %f\n", s1, fp);  
  
   i = _snwscanf( str2, 6,  L"%s %f", s2, &fp); // C4996  
   // Note: _snwscanf is deprecated; consider using _snwscanf_s instead  
   wprintf(L"_snwscanf converted %d fields: ", i);  
   wprintf(L"%s and %f\n", s2, fp);  
}  
```  
  
  **\_snscanf konvertierte 2 Felder: 15 und 12,000000**  
**\_snwscanf konvertierte 2 Felder: 15 und 12,000000**   
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [scanf\-Breitenangabe](../../c-runtime-library/scanf-width-specification.md)