---
title: "strnlen, strnlen_s, wcsnlen, wcsnlen_s, _mbsnlen, _mbsnlen_l, _mbstrnlen, _mbstrnlen_l"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "wcsnlen"
  - "strnlen_s"
  - "_mbstrnlen"
  - "_mbsnlen_l"
  - "_mbstrnlen_l"
  - "strnlen"
  - "wcsnlen_s"
  - "_mbsnlen"
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
  - "api-ms-win-crt-multibyte-l1-1-0.dll"
  - "api-ms-win-crt-string-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "wcsnlen"
  - "strnlen_s"
  - "_mbsnlen"
  - "_mbsnlen_l"
  - "_tcsnlen"
  - "_tcscnlen"
  - "_mbstrnlen_l"
  - "wcsnlen_s"
  - "_mbstrnlen"
  - "strnlen"
  - "_tcscnlen_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mbsnlen-Funktion"
  - "_mbsnlen_l-Funktion"
  - "_mbstrnlen-Funktion"
  - "_mbstrnlen_l-Funktion"
  - "_tcscnlen-Funktion"
  - "_tcscnlen_l-Funktion"
  - "_tcsnlen-Funktion"
  - "Längen, Zeichenfolgen"
  - "mbsnlen-Funktion"
  - "mbsnlen_l-Funktion"
  - "mbstrnlen-Funktion"
  - "mbstrnlen_l-Funktion"
  - "Zeichenfolgenlänge"
  - "strnlen-Funktion"
  - "strnlen_l-Funktion"
  - "strnlen_s-Funktion"
  - "wcsnlen-Funktion"
  - "wcsnlen_l-Funktion"
  - "wcsnlen_s-Funktion"
ms.assetid: cc05ce1c-72ea-4ae4-a7e7-4464e56e5f80
caps.latest.revision: 35
caps.handback.revision: "33"
ms.author: "corob"
manager: "ghogen"
---
# strnlen, strnlen_s, wcsnlen, wcsnlen_s, _mbsnlen, _mbsnlen_l, _mbstrnlen, _mbstrnlen_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft die Länge einer Zeichenfolge durch Verwendung des aktuellen oder einen übergebenen Gebietsschemas ab.  Dies sind sicherere Versionen von [strlen, wcslen, \_mbslen, \_mbslen\_l, \_mbstrlen, \_mbstrlen\_l](../../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md).  
  
> [!IMPORTANT]
>  `_mbsnlen`, `_mbsnlen_l`, `_mbstrnlen` und `_mbstrnlen_l` können nicht in Anwendungen eingesetzt werden, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausgeführt werden.  Weitere Informationen finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
size_t strnlen(  
   const char *str,  
   size_t numberOfElements   
);  
size_t strnlen_s(  
   const char *str,  
   size_t numberOfElements   
);  
size_t wcsnlen(  
   const wchar_t *str,  
   size_t numberOfElements  
);  
size_t wcsnlen_s(  
   const wchar_t *str,  
   size_t numberOfElements  
);  
size_t _mbsnlen(  
   const unsigned char *str,  
   size_t numberOfElements  
);  
size_t _mbsnlen_l(  
   const unsigned char *str,  
   size_t numberOfElements,  
   _locale_t locale  
);  
size_t _mbstrnlen(  
   const char *str,  
   size_t numberOfElements  
);  
size_t _mbstrnlen_l(  
   const char *str,  
   size_t numberOfElements,  
   _locale_t locale  
);  
```  
  
#### Parameter  
 `str`  
 Mit NULL endende Zeichenfolge.  
  
 `numberOfElements`  
 Die Größe des Zeichenfolgenpuffers.  
  
 `locale`  
 Zu verwendendes Gebietsschema.  
  
## Rückgabewert  
 Diese Funktionen geben die Anzahl von Zeichen in der Zeichenfolge zurück \(ohne das abschließende Nullzeichen\).  Wenn in den ersten `numberOfElements` Bytes der Zeichenfolge \(oder Breitzeichen für `wcsnlen`\) kein NULL\-Terminator auftritt, wird `numberOfElements` zurückgegeben, um den Fehlerzustand anzuzeigen; Zeichenfolgen mit NULL\-Terminatoren sind in jedem Falle kürzer als `numberOfElements`.  
  
 `_mbstrnlen` und `_mbstrnlen_l` geben \-1 zurück, wenn die Zeichenfolge ein ungültiges Multibytezeichen enthält.  
  
## Hinweise  
  
> [!NOTE]
>  `strnlen` ist kein Ersatz für `strlen`; `strnlen` ist nur für eine Verwendung zur Berechnung der Größe nicht vertrauenswürdiger eingehender Daten in einem Puffer von bekannter Größe gedacht – z. B. eines Netzwerkpakets.  `strnlen` berechnet die Länge, geht jedoch nicht hinter das Ende des Puffers zurück, wenn die Zeichenfolge keinen Terminator aufweist.  Verwenden Sie in anderen Situationen `strlen`.  \(Dasselbe gilt für `wcsnlen`, `_mbsnlen` und `_mbstrnlen`.\)  
  
 Jede dieser Funktionen gibt die Anzahl von Zeichen in `str` zurück, jedoch ohne das NULL\-Terminatorzeichen.  `strnlen` und `strnlen_s` interpretieren die Zeichenfolge allerdings als Einzelbytezeichenfolge, sodass der Rückgabewert immer der Anzahl von Bytes entspricht, selbst wenn die Zeichenfolge Multibytezeichen enthält.  `wcsnlen` und `wcsnlen_s` sind Breitzeichenversionen von `strnlen` bzw. `strnlen_s`; die Argumente für `wcsnlen` und `wcsnlen_s` sind Breitzeichen\-Zeichenfolgen, und die Zeichenzählung erfolgt in Breitzeicheneinheiten.  Andernfalls verhalten sich `wcsnlen` und `strnlen` identisch, ebenso `strnlen_s` und `wcsnlen_s`.  
  
 `strnlen`, `wcsnlen,` und `_mbsnlen` überprüfen ihre Parameter nicht.  Wenn `str` gleich `NULL` ist, tritt eine Zugriffsverletzung auf.  
  
 `strnlen_s` und `wcsnlen_s` überprüfen die eigenen Parameter.  Wenn `str` gleich `NULL` ist, geben die Funktionen 0 zurück.  
  
 `_mbstrnlen` überprüft auch die eigenen Parameter.  Wenn `str` gleich `NULL` ist, oder wenn `numberOfElements` größer als `INT_MAX` ist, generiert `_mbstrnlen` eine Ausnahme wegen eines ungültigen Parameters, wie unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, setzt `_mbstrnlen` `errno` auf `EINVAL` und gibt \-1 zurück.  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE und \_MBCS nicht definiert.|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|-------------------------------------------|----------------------|-------------------------|  
|`_tcsnlen`|`strnlen`|`strnlen`|`wcsnlen`|  
|`_tcscnlen`|`strnlen`|`_mbsnlen`|`wcsnlen`|  
|`_tcscnlen_l`|`strnlen`|`_mbsnlen_l`|`wcsnlen`|  
  
 `_mbsnlen` und `_mbstrnlen` geben die Anzahl von Multibytezeichen in einer Multibytezeichenfolge zurück.  `_mbsnlen` erkennt Multibytezeichensequenzen anhand der Multibyte\-Codepage, die aktuell in Verwendung ist, oder anhand des übergebenen Gebietsschemas, überprüft jedoch nicht die Gültigkeit der Multibytezeichen.  `_mbstrnlen` überprüft die Gültigkeit von Multibytezeichen und erkennt Multibytezeichensequenzen.  Wenn die an `_mbstrnlen` übergebene Zeichenfolge ein ungültiges Multibytezeichen enthält, wird `errno` auf `EILSEQ` gesetzt.  
  
 Der Ausgabewert ist von der `LC_CTYPE`\-Kategorieneinstellung des Gebietsschemas betroffen; weitere Informationen finden Sie unter [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).  Die Versionen dieser Funktionen sind nahezu identisch, außer dass diejenigen ohne das `_l`\-Suffix für dieses Gebietsschema\-abhängige Verhalten das aktuelle Gebietsschema verwenden, und diejenigen mit `_l`\-Suffix den übergebenen Gebietsschemaparameter.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`strnlen`, `strnlen_s`|\<string.h\>|  
|`wcsnlen`, `wcsnlen_s`|\<string.h\> oder \<wchar.h\>|  
|`_mbsnlen`, `_mbsnlen_l`|\<mbstring.h\>|  
|`_mbstrnlen`, `_mbstrnlen_l`|\<stdlib.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
```  
// crt_strnlen.c  
  
#include <string.h>  
  
int main()  
{  
   // str1 is 82 characters long. str2 is 159 characters long   
  
   char* str1 = "The length of a string is the number of characters\n"  
               "excluding the terminating null.";  
   char* str2 = "strnlen takes a maximum size. If the string is longer\n"  
                "than the maximum size specified, the maximum size is\n"  
                "returned rather than the actual size of the string.";  
   size_t len;  
   size_t maxsize = 100;  
  
   len = strnlen(str1, maxsize);  
   printf("%s\n Length: %d \n\n", str1, len);  
  
   len = strnlen(str2, maxsize);  
   printf("%s\n Length: %d \n", str2, len);  
}  
```  
  
  **Die Länge einer Zeichenfolge ist die Anzahl ihrer Zeichen**  
**ohne den NULL\-Terminator.  Länge: 82**   
**strnlen hat die maximale Größe.  Wenn die Zeichenfolge länger**  
**ist als die festgelegte maximale Länge, wird statt der**  
**tatsächlichen Länge der Zeichenfolge die maximale Länge zurückgegeben.  Länge: 100**    
## .NET Framework-Entsprechung  
 [System::String::Length](https://msdn.microsoft.com/en-us/library/system.string.length.aspx)  
  
## Siehe auch  
 [Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [Interpretation von Mehrbytezeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [strncat, \_strncat\_l, wcsncat, \_wcsncat\_l, \_mbsncat, \_mbsncat\_l](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)   
 [strncmp, wcsncmp, \_mbsncmp, \_mbsncmp\_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [strcoll\-Funktionen](../../c-runtime-library/strcoll-functions.md)   
 [strncpy\_s, \_strncpy\_s\_l, wcsncpy\_s, \_wcsncpy\_s\_l, \_mbsncpy\_s, \_mbsncpy\_s\_l](../../c-runtime-library/reference/strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)   
 [strrchr, wcsrchr, \_mbsrchr, \_mbsrchr\_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [\_strset, \_strset\_l, \_wcsset, \_wcsset\_l, \_mbsset, \_mbsset\_l](../../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)   
 [strspn, wcsspn, \_mbsspn, \_mbsspn\_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)