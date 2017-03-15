---
title: "strcat_s, wcscat_s, _mbscat_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "strcat_s"
  - "_mbscat_s"
  - "wcscat_s"
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
  - "strcat_s"
  - "wcscat_s"
  - "_mbscat_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mbscat_s-Funktion"
  - "Anfügen von Zeichenfolgen"
  - "mbscat_s-Funktion"
  - "strcat_s-Funktion"
  - "Zeichenfolgen [C++], Anhängen"
  - "wcscat_s-Funktion"
ms.assetid: 0f2f9901-c5c5-480b-98bc-f8f690792fc0
caps.latest.revision: 30
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 30
---
# strcat_s, wcscat_s, _mbscat_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fügt eine Zeichenfolge an.  Diese Versionen von [strcat, wcscat, \_mbscat](../../c-runtime-library/reference/strcat-wcscat-mbscat.md) enthalten Sicherheitserweiterungen wie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
> [!IMPORTANT]
>  `_mbscat_s` kann nicht in Anwendungen verwendet werden, die in Windows\-Runtime ausgeführt werden.  Weitere Informationen finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
errno_t strcat_s(  
   char *strDestination,  
   size_t numberOfElements,  
   const char *strSource   
);  
errno_t wcscat_s(  
   wchar_t *strDestination,  
   size_t numberOfElements,  
   const wchar_t *strSource   
);  
errno_t _mbscat_s(  
   unsigned char *strDestination,  
   size_t numberOfElements,  
   const unsigned char *strSource   
);  
template <size_t size>  
errno_t strcat_s(  
   char (&strDestination)[size],  
   const char *strSource   
); // C++ only  
template <size_t size>  
errno_t wcscat_s(  
   wchar_t (&strDestination)[size],  
   const wchar_t *strSource   
); // C++ only  
template <size_t size>  
errno_t _mbscat_s(  
   unsigned char (&strDestination)[size],  
   const unsigned char *strSource   
); // C++ only  
```  
  
#### Parameter  
 `strDestination`  
 Auf NULL endender Zielzeichenfolgenpuffer.  
  
 `numberOfElements`  
 Größe des Zielzeichenfolgenpuffers.  
  
 `strSource`  
 Auf NULL endender Quellzeichenfolgepuffer.  
  
## Rückgabewert  
 Null, wenn erfolgreich, ein Fehlercode, wenn ein Fehler auftritt.  
  
### Fehlerbedingungen  
  
|`strDestination`|`numberOfElements`|`strSource`|Rückgabewert|Inhalt von `strDestination`|  
|----------------------|------------------------|-----------------|------------------|---------------------------------|  
|`NULL` oder nicht abgeschlossen|any|any|`EINVAL`|nicht geändert|  
|any|any|`NULL`|`EINVAL`|`strDestination`\[0\] auf 0 festgelegt|  
|any|0 oder zu klein|any|`ERANGE`|`strDestination`\[0\] auf 0 festgelegt|  
  
## Hinweise  
 Die `strcat_s`\-Funktion fügt `strSource` an `strDestination` an und beendet die Ergebniszeichenfolge mit einem Nullzeichen.  Das erste Zeichen von `strSource` überschreibt das abschließende Nullzeichen von `strDestination`.  Wenn sich Quell\- und Zielzeichenfolgen überlappen, ist das Verhalten von `strcat_s` undefiniert.  
  
 Beachten Sie, dass es sich bei dem zweiten Parameter um die Gesamtgröße des Puffers handelt, nicht um die verbleibende Größe:  
  
```  
char buf[16];  
strcpy_s(buf, 16, "Start");  
strcat_s(buf, 16, " End");               // Correct  
strcat_s(buf, 16 – strlen(buf), " End"); // Incorrect  
```  
  
 `wcscat_s` und `_mbscat_s` sind Breitzeichen\- und Multibytezeichenversionen von `strcat_s`.  Die Argumente und der Rückgabewert von `wcscat_s` sind Breitzeichen\-Zeichenfolgen; die von `_mbscat_s` sind Mehrbyte\-Zeichenfolgen.  Diese drei Funktionen verhalten sich andernfalls identisch.  
  
 Wenn `strDestination` ein NULL\-Zeiger ist oder nicht mit NULL endet, oder wenn `strSource` ein `NULL`\-Zeiger ist, oder wenn die Zielzeichenfolge zu klein ist, wird der Handler für ungültige Parameter aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, geben diese Funktionen `EINVAL` zurück und stellen `errno` auf `EINVAL` ein.  
  
 In C\+\+ wird die Verwendung dieser Funktionen durch Vorlagenüberladungen vereinfacht; die Überladungen können automatisch Rückschlüsse auf die Pufferlänge ziehen \(wodurch kein Größenargument mehr angegeben werden muss\), und sie können automatisch die älteren, nicht sicheren Funktionen durch ihre neueren, sicheren Entsprechungen ersetzen.  Weitere Informationen finden Sie unter [Sichere Vorlagenüberladungen](../../c-runtime-library/secure-template-overloads.md).  
  
 Die Debugversionen dieser Funktionen füllen zunächst den Puffer mit "0xFD" auf.  Mit [\_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md) deaktivieren Sie dieses Verhalten.  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_tcscat_s`|`strcat_s`|`_mbscat_s`|`wcscat_s`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`strcat_s`|\<string.h\>|  
|`wcscat_s`|\<string.h\> oder \<wchar.h\>|  
|`_mbscat_s`|\<mbstring.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
 Siehe hierzu das Codebeispiel unter [strcpy\_s, wcscpy\_s, \_mbscpy\_s](../../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md).  
  
## .NET Framework-Entsprechung  
 [System::String::Concat](https://msdn.microsoft.com/en-us/library/system.string.concat.aspx)  
  
## Siehe auch  
 [Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)   
 [strncat, \_strncat\_l, wcsncat, \_wcsncat\_l, \_mbsncat, \_mbsncat\_l](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)   
 [strncmp, wcsncmp, \_mbsncmp, \_mbsncmp\_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [strncpy, \_strncpy\_l, wcsncpy, \_wcsncpy\_l, \_mbsncpy, \_mbsncpy\_l](../../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)   
 [\_strnicmp, \_wcsnicmp, \_mbsnicmp, \_strnicmp\_l, \_wcsnicmp\_l, \_mbsnicmp\_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strrchr, wcsrchr, \_mbsrchr, \_mbsrchr\_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [strspn, wcsspn, \_mbsspn, \_mbsspn\_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)