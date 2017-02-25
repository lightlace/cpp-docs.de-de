---
title: "_scprintf_p, _scprintf_p_l, _scwprintf_p, _scwprintf_p_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_scwprintf_p"
  - "_scprintf_p_l"
  - "_scwprintf_p_l"
  - "_scprintf_p"
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
  - "_scwprintf_p_l"
  - "_sctprintf_p"
  - "scprintf_p_l"
  - "scprintf_p"
  - "_sctprintf_p_l"
  - "scwprintf_p"
  - "_scprintf_p_l"
  - "scwprintf_p_l"
  - "_scprintf_p"
  - "_scwprintf_p"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_scprintf_p-Funktion"
  - "_scprintf_p_l-Funktion"
  - "_sctprintf_p-Funktion"
  - "_sctprintf_p_l-Funktion"
  - "_scwprintf_p-Funktion"
  - "_scwprintf_p_l-Funktion"
  - "scprintf_p-Funktion"
  - "scprintf_p_l-Funktion"
  - "sctprintf_p-Funktion"
  - "sctprintf_p_l-Funktion"
  - "scwprintf_p-Funktion"
  - "scwprintf_p_l-Funktion"
ms.assetid: 8390d1e1-2826-47a4-851f-6635a88087cc
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# _scprintf_p, _scprintf_p_l, _scwprintf_p, _scwprintf_p_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt die Anzahl der Zeichen in der formatierten Zeichenfolge, mit der Möglichkeit, die Reihenfolge anzugeben zurück, in der Parameter in der Formatzeichenfolge verwendet werden.  
  
## Syntax  
  
```  
int _scprintf_p(  
   const char *format [,  
   argument] ...   
);  
int _scprintf_p_l(  
   const char *format,  
   locale_t locale [,  
   argument] ...   
);  
int _scwprintf_p (  
   const wchar_t *format [,  
   argument] ...   
);  
int _scwprintf_p _l(  
   const wchar_t *format,  
   locale_t locale [,  
   argument] ...   
);  
```  
  
#### Parameter  
 `format`  
 Formatsteuerzeichenfolge.  
  
 `argument`  
 Optionale Argumente.  
  
 `locale`  
 Das zu verwendende Gebietsschema.  
  
## Rückgabewert  
 Gibt die Anzahl von Zeichen zurück, die generiert werden, wenn die Zeichenfolge in einer Datei oder einem Puffer mithilfe der angegebenen Formatierungscodes gedruckt werden oder gesendet werden sollen.  Der zurückgegebene Wert enthält nicht das NULL.  `_scwprintf_p` führt die gleiche Aufgabe für Breitzeichen erfüllt.  
  
 Der Unterschied zwischen `_scprintf_p` und `_scprintf` ist, dass `_scprintf_p` positionelle Parameter unterstützt, wodurch festgelegt werden kann, in welcher Reihenfolge die Argumente in der Formatzeichenfolge verwendet werden.  Weitere Informationen finden Sie unter [printf\_p\-Positionsparameter](../../c-runtime-library/printf-p-positional-parameters.md).  
  
 Wenn `format` ein `NULL`\-Zeiger ist, wird der Handler für ungültige Parameter aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, geben diese Funktionen "– 1" zurück und legen `errno` auf `EINVAL` fest.  
  
 Weitere Informationen über diese und andere Fehlercodes finden Sie unter [\_doserrno, errno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 Jedes `argument` \(falls vorhanden\) wird entsprechend der entsprechenden Formatangabe in `format` konvertiert.  Das Format besteht aus normalen Zeichen und hat die gleiche Form und Funktion wie das `format`\-Argument für [printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md).  
  
 Die Versionen dieser Funktionen mit dem `_l`\-Suffix sind beinahe identisch, verwenden jedoch den ihnen übergebenen Gebietsschemaparameter anstelle des aktuellen Threadgebietsschemas.  
  
> [!IMPORTANT]
>  Stellen Sie sicher, dass `format` keine benutzerdefinierte Zeichenfolge ist.  
  
### Zuordnung generischer Textroutinen  
  
|Tchar.h\-Routine|\_UNICODE und \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|------------------------------------------|----------------------|-------------------------|  
|`_sctprintf_p`|`_scprintf_p`|`_scprintf_p`|`_scwprintf_p`|  
|`_sctprintf_p_l`|`_scprintf_p_l`|`_scprintf_p_l`|`_scwprintf_p_l`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_scprintf_p`, `_scprintf_p_l`|\<stdio.h\>|  
|`_scwprintf_p`, `_scwprintf_p_l`|\<stdio.h\> oder \<wchar.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Siehe auch  
 [Stream\-E\/A](../../c-runtime-library/stream-i-o.md)   
 [\_scprintf, \_scprintf\_l, \_scwprintf, \_scwprintf\_l](../../c-runtime-library/reference/scprintf-scprintf-l-scwprintf-scwprintf-l.md)   
 [\_printf\_p, \_printf\_p\_l, \_wprintf\_p, \_wprintf\_p\_l](../../c-runtime-library/reference/printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)