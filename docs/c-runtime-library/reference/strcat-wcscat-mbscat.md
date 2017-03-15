---
title: "strcat, wcscat, _mbscat | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mbscat"
  - "wcscat"
  - "strcat"
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
  - "_mbscat"
  - "_ftcscat"
  - "_tcscat"
  - "strcat"
  - "wcscat"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ftcscat-Funktion"
  - "_mbscat-Funktion"
  - "_tcscat-Funktion"
  - "Anfügen von Zeichenfolgen"
  - "Zeichenfolgen verketten"
  - "ftcscat-Funktion"
  - "mbscat-Funktion"
  - "strcat-Funktion"
  - "Zeichenfolgen [C++], Anhängen"
  - "Zeichenfolgen [C++], Verketten"
  - "tcscat-Funktion"
  - "wcscat-Funktion"
ms.assetid: c89c4ef1-817a-44ff-a229-fe22d06ba78a
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# strcat, wcscat, _mbscat
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fügt eine Zeichenfolge an.  Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [strcat\_s, wcscat\_s, \_mbscat\_s](../../c-runtime-library/reference/strcat-s-wcscat-s-mbscat-s.md).  
  
> [!IMPORTANT]
>  `_mbscat_s` kann nicht in Anwendungen verwendet werden, die in Windows\-Runtime ausgeführt werden.  Weitere Informationen finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
char *strcat(  
   char *strDestination,  
   const char *strSource   
);  
wchar_t *wcscat(  
   wchar_t *strDestination,  
   const wchar_t *strSource   
);  
unsigned char *_mbscat(  
   unsigned char *strDestination,  
   const unsigned char *strSource   
);  
template <size_t size>  
char *strcat(  
   char (&strDestination)[size],  
   const char *strSource   
); // C++ only  
template <size_t size>  
wchar_t *wcscat(  
   wchar_t (&strDestination)[size],  
   const wchar_t *strSource   
); // C++ only  
template <size_t size>  
unsigned char *_mbscat(  
   unsigned char (&strDestination)[size],  
   const unsigned char *strSource   
); // C++ only  
```  
  
#### Parameter  
 `strDestination`  
 Auf NULL endende Zielzeichenfolge.  
  
 `strSource`  
 Mit NULL endende Quellzeichenfolge.  
  
## Rückgabewert  
 Jede dieser Funktionen gibt die Zielzeichenfolge zurück \(`strDestination`\).  Kein Rückgabewert ist zur Fehleranzeige reserviert.  
  
## Hinweise  
 Die `strcat`\-Funktion fügt `strSource` an `strDestination` an und beendet die Ergebniszeichenfolge mit einem Nullzeichen.  Das erste Zeichen von `strSource` überschreibt das abschließende Nullzeichen von `strDestination`.  Wenn sich Quell\- und Zielzeichenfolgen überlappen, ist das Verhalten von `strcat` undefiniert.  
  
> [!IMPORTANT]
>  Da `strcat` vor dem Anfügen von `strSource``strDestination` nicht auf genügend Speicherplatz überprüft, kann es so zu Pufferüberläufen kommen.  Verwenden Sie eventuell stattdessen [strncat](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md).  
  
 `wcscat` und `_mbscat` sind Breitzeichen\- und Multibytezeichenversionen von `strcat`.  Die Argumente und der Rückgabewert von `wcscat` sind Breitzeichen\-Zeichenfolgen; die von `_mbscat` sind Mehrbyte\-Zeichenfolgen.  Diese drei Funktionen verhalten sich andernfalls identisch.  
  
 In C\+\+ haben diese Funktionen Vorlagenüberladungen, mit denen die neueren, sicheren Entsprechungen dieser Funktionen aufgerufen werden.  Weitere Informationen finden Sie unter [Sichere Vorlagenüberladungen](../../c-runtime-library/secure-template-overloads.md).  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_tcscat`|`strcat`|`_mbscat`|`wcscat`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`strcat`|\<string.h\>|  
|`wcscat`|\<string.h\> oder \<wchar.h\>|  
|`_mbscat`|\<mbstring.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
 Betrachten Sie das Beispiel für [strcpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md).  
  
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