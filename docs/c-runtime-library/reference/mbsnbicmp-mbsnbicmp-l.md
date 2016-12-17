---
title: "_mbsnbicmp, _mbsnbicmp_l"
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
  - "_mbsnbicmp_l"
  - "_mbsnbicmp"
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
apitype: "DLLExport"
f1_keywords: 
  - "_strnicmp"
  - "_wcsnicmp_l"
  - "_mbsnbicmp"
  - "mbsnbicmp"
  - "mbsnbicmp_l"
  - "_tcsnicmp"
  - "_strnicmp_l"
  - "_tcsnicmp_l"
  - "_wcsnicmp"
  - "_mbsnbicmp_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mbsnbicmp-Funktion"
  - "_mbsnbicmp_l-Funktion"
  - "_strnicmp-Funktion"
  - "_strnicmp_l-Funktion"
  - "_tcsnicmp-Funktion"
  - "_tcsnicmp_l-Funktion"
  - "_wcsnicmp-Funktion"
  - "_wcsnicmp_l-Funktion"
  - "mbsnbicmp-Funktion"
  - "mbsnbicmp_l-Funktion"
ms.assetid: ddb44974-8b0c-42f0-90d0-56c9350bae0c
caps.latest.revision: 16
caps.handback.revision: "16"
ms.author: "corob"
manager: "ghogen"
---
# _mbsnbicmp, _mbsnbicmp_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vergleicht `n` Bytes von zwei Multibyte\-Zeichenfolgen und ignoriert die Groß\- und Kleinschreibung.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows\-Runtime ausgeführt werden.  Weitere Informationen finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
int _mbsnbicmp(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count   
);  
```  
  
#### Parameter  
 `string1, string2`  
 Zu vergleichende mit NULL endende Zeichenfolgen.  
  
 `count`  
 Anzahl der zu vergleichenden Bytes.  
  
## Rückgabewert  
 Der Rückgabewert gibt die Beziehung zwischen den untergeordneten Zeichenfolgen an.  
  
|Rückgabewert|Beschreibung|  
|------------------|------------------|  
|\< 0|Die untergeordnete Zeichenfolge `string1` ist kleiner als die untergeordnete Zeichenfolge `string2`.|  
|0|Die untergeordnete Zeichenfolge `string1` ist mit der untergeordneten Zeichenfolge `string2` identisch.|  
|\> 0|Die untergeordnete Zeichenfolge `string1` ist größer als die untergeordnete Zeichenfolge `string2`.|  
  
 Bei einem Fehler gibt `_mbsnbcmp` `_NLSCMPERROR` zurück \(definiert in String.h und Mbstring.h\).  
  
## Hinweise  
 Die `_mbsnbicmp`\-Funktion führt einen Ordinalvergleich von höchstens der ersten `count` Bytes von `string1` und `string2` durch.  Der Vergleich wird ausgeführt, indem jedes Zeichen in Kleinbuchstaben konvertiert wird; `_mbsnbcmp` ist eine Version von `_mbsnbicmp`, bei der die Groß\-\/Kleinschreibung beachtet wird.  Der Vergleich endet, wenn in jeder Zeichenfolge beendende NULL\-Zeichen erreicht wird, bevor `count` Zeichen verglichen wurden.  Wenn beim Erreichen des beendenden NULL\-Zeichens die Zeichenfolgen gleich sind, bevor `count` Zeichen verglichen wurden, ist die kürzere Zeichenfolge kleiner.  
  
 `_mbsnbicmp`  ähnelt `_mbsnicmp`, mit dem Unterschied dass die Zeichenfolgen nicht nach Zeichen, sondern bis zu `count` Bytes verglichen werden.  
  
 Abhängig von der Großschreibung ist der Vergleich von zwei Zeichenfolgen mit Zeichen zwischen "Z" und "a" in der ASCII\-Tabelle \('\[', '\\', '\]', '^', '\_' und '\`'\) unterschiedlich.  Beispielsweise werden die beiden Zeichenfolgen "`ABCDE`" und "`ABCD^`" in eine Richtung verglichen, wenn Kleinschreibung vorliegt \("`abcde`" \> "`abcd^`"\) und in die andere Richtung, wenn Großschreibung vorliegt \("`ABCDE`" \< "`ABCD^`"\).  
  
 `_mbsnbicmp` erkennt Multibyte\-Zeichenfolgen gemäß der aktuellen [Multibyte\-Codepage](../../c-runtime-library/code-pages.md).  Die aktuelle Gebietsschemaeinstellung nimmt dabei keinen Einfluss.  
  
 Wenn `string1` oder `string2` ein NULL\-Zeiger ist, ruft `_mbsnbicmp` den Handler für ungültige Parameter auf, wie unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, gibt die Funktion `_NLSCMPERROR` zurück und setzt `errno` auf `EINVAL`.  
  
### Zuordnung generischer Textroutinen  
  
|Tchar.h\-Routine|\_UNICODE und \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|------------------------------------------|----------------------|-------------------------|  
|`_tcsnicmp`|`_strnicmp`|`_mbsnbicmp`|`_wcsnicmp`|  
|`_tcsnicmp_l`|`_strnicmp_l`|`_mbsnbicmp_l`|`_wcsnicmp_l`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_mbsnbicmp`|\<mbstring.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
 Weitere Informationen finden Sie im Beispiel für [\_mbsnbcmp, \_mbsnbcmp\_l](../../c-runtime-library/reference/mbsnbcmp-mbsnbcmp-l.md).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)   
 [\_mbsnbcat, \_mbsnbcat\_l](../../c-runtime-library/reference/mbsnbcat-mbsnbcat-l.md)   
 [\_mbsnbcmp, \_mbsnbcmp\_l](../../c-runtime-library/reference/mbsnbcmp-mbsnbcmp-l.md)   
 [\_stricmp, \_wcsicmp, \_mbsicmp, \_stricmp\_l, \_wcsicmp\_l, \_mbsicmp\_l](../../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)