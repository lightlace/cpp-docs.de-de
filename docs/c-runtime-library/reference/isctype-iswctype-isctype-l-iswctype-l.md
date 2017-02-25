---
title: "_isctype, iswctype, _isctype_l, _iswctype_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_isctype_l"
  - "iswctype"
  - "_iswctype_l"
  - "_isctype"
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
  - "iswctype"
  - "_isctype"
  - "_isctype_l"
  - "_iswctype"
  - "isctype"
  - "iswctype_l"
  - "isctype_l"
  - "_iswctype_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_isctype-Funktion"
  - "_isctype_l-Funktion"
  - "_iswctype-Funktion"
  - "_iswctype_l-Funktion"
  - "isctype-Funktion"
  - "isctype_l-Funktion"
  - "iswctype-Funktion"
  - "iswctype_l-Funktion"
ms.assetid: cf7509b7-12fc-4d95-8140-ad2eb98173d3
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# _isctype, iswctype, _isctype_l, _iswctype_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Testet `c` auf die Eigenschaft, die durch das `desc`\-Argument angegeben wird.  Für jeden gültigen Wert von `desc` gibt es eine entsprechende Breitzeichen\-Klassifizierungsroutine.  
  
## Syntax  
  
```  
int _isctype(  
   int c,  
   _ctype_t desc  
);  
int _isctype_l(  
   int c,  
   _ctype_t desc,  
   _locale_t locale  
);  
int iswctype(  
   wint_t c,  
   wctype_t desc   
);  
int _iswctype_l(  
   wint_t c,  
   wctype_t desc,  
   _locale_t locale  
);  
```  
  
#### Parameter  
 `c`  
 Zu testende ganze Zahl.  
  
 `desc`  
 Eigenschaft, für die der Test durchgeführt werden soll.  Diese wird normalerweise mithilfe von ctype oder [wctype](../../c-runtime-library/reference/wctype.md) abgerufen.  
  
 `locale`  
 Das für alle gebietsschemaabhängigen Tests zu verwendende Gebietsschema.  
  
## Rückgabewert  
 `_isctype` und `iswctype` geben einen Wert ungleich 0 \(null\) zurück, wenn `c` die Eigenschaft aufweist, die von `desc` im aktuellen Gebietsschema angegeben wird, wenn nicht, wird 0 \(null\) zurückgegeben.  Die Versionen dieser Funktionen mit dem `_l`\-Suffix sind beinahe identisch, verwenden jedoch das ihnen übergebene Gebietsschema anstelle des aktuellen Gebietsschemas für ihr vom Gebietsschema abhängiges Verhalten.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
 Das Verhalten von `_isctype` und `_isctype_l` ist nicht definiert, wenn `c` nicht EOF ist oder nicht im Bereich von 0 bis 0xFF liegt.  Wenn eine CRT\-Debugbibliothek verwendet wird und `c` keinem dieser Werte entspricht, lösen die Funktionen eine Assertion aus.  
  
### Zuordnung generischer Textroutinen  
  
|Tchar.h\-Routine|\_UNICODE und \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|------------------------------------------|----------------------|-------------------------|  
|`n/a`|`_isctype`|`n/a`|`_iswctype`|  
|`n/a`|`_isctype_l`|`n/a`|`_iswctype_l`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_isctype`|\<ctype.h\>|  
|`iswctype`|\<ctype.h\> oder \<wchar.h\>|  
|`_isctype_l`|\<ctype.h\>|  
|`_iswctype_l`|\<ctype.h\> oder \<wchar.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Bibliotheken  
 Alle Versionen [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Zeichenklassifizierung](../../c-runtime-library/character-classification.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [is\- und isw\-Routinen](../../c-runtime-library/is-isw-routines.md)