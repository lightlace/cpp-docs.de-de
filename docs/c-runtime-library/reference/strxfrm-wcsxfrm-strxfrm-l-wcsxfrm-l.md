---
title: "strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "strxfrm"
  - "_wcsxfrm_l"
  - "_strxfrm_l"
  - "wcsxfrm"
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
  - "api-ms-win-crt-string-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "strxfrm"
  - "_tcsxfrm"
  - "wcsxfrm"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_strxfrm_l-Funktion"
  - "_tcsxfrm-Funktion"
  - "_wcsxfrm_l-Funktion"
  - "Zeichenfolgenvergleich [C++], Transformieren von Zeichenfolgen"
  - "Zeichenfolgen [C++], Vergleichen des Gebietsschemas"
  - "strxfrm-Funktion"
  - "strxfrm_l-Funktion"
  - "tcsxfrm-Funktion"
  - "wcsxfrm-Funktion"
  - "wcsxfrm_l-Funktion"
ms.assetid: 6ba8e1f6-4484-49aa-83b8-bc2373187d9e
caps.latest.revision: 18
caps.handback.revision: "18"
ms.author: "corob"
manager: "ghogen"
---
# strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Transformieren Sie eine Zeichenfolge auf Grundlage gebietsschemaspezifische Informationen.  
  
## Syntax  
  
```  
size_t strxfrm(  
   char *strDest,  
   const char *strSource,  
   size_t count   
);  
size_t wcsxfrm(  
   wchar_t *strDest,  
   const wchar_t *strSource,  
   size_t count   
);  
size_t _strxfrm_l(  
   char *strDest,  
   const char *strSource,  
   size_t count,  
   _locale_t locale  
);  
size_t wcsxfrm_l(  
   wchar_t *strDest,  
   const wchar_t *strSource,  
   size_t count,  
   _locale_t locale  
);  
```  
  
#### Parameter  
 `strDest`  
 Zielzeichenfolge.  
  
 `strSource`  
 Quellzeichenfolge.  
  
 `count`  
 Maximale Anzahl in `strDest` zu legen, Zeichen *.*  
  
 `locale`  
 Das zu verwendende Gebietsschema.  
  
## Rückgabewert  
 Gibt die Länge der transformierten Zeichenfolge zurück und nicht angerechnet das NULL.  Falls der Rückgabewert größer oder gleich `count` ist, ist der Inhalt eines `strDest` unvorhersehbar.  Bei einem Fehler wird jeder Funktion `errno` festgelegt und `INT_MAX` zurückgegeben.  Ein ungültiges Zeichen wird `errno` auf `EILSEQ` festgelegt.  
  
## Hinweise  
 Die `strxfrm`\-Funktion umwandelt die Zeichenfolge, die von `strSource` in ein neues sortiertes Formular angezeigt wird, das im `strDest` gespeichert wird.  Nicht mehr als `count` Zeichen, einschließlich das Nullzeichen, werden in die Ergebniszeichenfolge transformiert und platziert.  Die Transformation wird mithilfe der `LC_COLLATE` Kategorieneinstellung des Gebietsschemas gemacht.  Weitere Informationen zu `LC_COLLATE` finden Sie unter [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).  `strxfrm` verwendet das aktuelle Gebietsschema sein gebietsschemaabhängiges Verhalten; `_strxfrm_l` ist identisch, es werden in das Gebietsschema, das statt des aktuellen Gebietsschemas übergeben wird.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
 Nach der Transformation angewendet hat ein Aufruf von `strcmp` mit den beiden transformierten Zeichenfolgen, zurückgehalten identisch mit denen eines Anrufs `strcoll` entsteht, mit den ursprünglichen zwei Zeichenfolgen.  Wie bei `strcoll` und `stricoll`, behandelt `strxfrm` automatisch Mehrbyte\-Zeichenfolgen entsprechend.  
  
 `wcsxfrm` ist eine Breitzeichen\-Version von `strxfrm`; die Zeichenfolgenargumente von `wcsxfrm` sind Breitzeichenzeiger.  Für `wcsxfrm` nach der Zeichenfolgentransformation, ein Aufruf von `wcscmp` mit den beiden Zeichenfolgenerträgen transformierten identisch mit denen eines Anrufs `wcscoll` entsteht, auf den ursprünglich zwei Zeichenfolgen.  `wcsxfrm` und `strxfrm` verhalten sich andernfalls identisch.  `wcsxfrm` verwendet das aktuelle Gebietsschema sein gebietsschemaabhängiges Verhalten; `_wcsxfrm_l` verwendet das Gebietsschema, das in statt des aktuellen Gebietsschemas übergeben wird.  
  
 Diese Funktionen überprüfen ihre Parameter.  Wenn `strSource` ein NULL\-Zeiger ist oder `strDest` ein NULL\-Zeiger ist \(es sei denn, Anzahl \(null\) oder wenn `count` größer als `INT_MAX` ist, wird der ungültige Parameterhandler aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, stellen diese Funktionen `errno` auf `EINVAL` ein und geben `INT_MAX` zurück.  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_tcsxfrm`|`strxfrm`|`strxfrm`|`wcsxfrm`|  
|`_tcsxfrm_l`|`_strxfrm_l`|`_strxfrm_l`|`_wcsxfrm_l`|  
  
 Im "C"\- Gebietsschema ist die Reihenfolge der Zeichen im Zeichensatz \(ASCII\-Zeichensatz\) mit der lexikografischen Reihenfolge der Zeichen.  In anderen Gebietsschemas, kann die Reihenfolge der Zeichen im Zeichensatz sich von der lexikografischen Reihenfolge.  Beispielsweise in bestimmten europäischen Gebietsschemas, geht das Zeichen "a" \(Wert 0x61\) das Zeichen '&\#x00E4 voran; '\(Wert 0xE4\) im Zeichensatz, in der Zeichen "ä" wird dem Zeichen "a" lexikografisch voran.  
  
 In den Gebietsschemas, für die der Zeichensatz und die lexikografische Reihenfolge unterscheiden, verwenden Sie `strxfrm` auf den Vorlagenzeichenfolgen und `strcmp` auf den Ergebniszeichenfolgen, einen lexikografischen Zeichenfolgenvergleiche anhand der aktuellen `LC_COLLATE` Kategorieneinstellung des Gebietsschemas dann zu erzeugen.  also zwei Zeichenfolgen im obigen Gebietsschema lexikografisch vergleichen, verwenden Sie `strxfrm` für die ursprünglichen Zeichenfolgen, dann `strcmp` auf den Ergebniszeichenfolgen.  Alternativ können Sie `strcoll` statt `strcmp` für die ursprünglichen Zeichenfolgen verwenden.  
  
 `strxfrm` ist im Allgemeinen ein Wrapper um [LCMapString](http://msdn.microsoft.com/library/windows/desktop/dd318700) mit `LCMAP_SORTKEY`.  
  
 Der Wert des folgenden Ausdrucks ist die Größe des Arrays, das erforderlich ist, um die `strxfrm` der Transformation Quellzeichenfolge enthalten:  
  
```  
1 + strxfrm( NULL, string, 0 )  
```  
  
 Nur im "C " \- Gebietsschema, `strxfrm` entspricht dem folgenden Code:  
  
```  
strncpy( _string1, _string2, _count );  
return( strlen( _string1 ) );  
```  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`strxfrm`|\<string.h\>|  
|`wcsxfrm`|\<string.h\> oder \<wchar.h\>|  
|`_strxfrm_l`|\<string.h\>|  
|`_wcsxfrm_l`|\<string.h\> oder \<wchar.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)   
 [strcoll\-Funktionen](../../c-runtime-library/strcoll-functions.md)   
 [strcmp, wcscmp, \_mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [strncmp, wcsncmp, \_mbsncmp, \_mbsncmp\_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)