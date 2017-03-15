---
title: "_setmbcp | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_setmbcp"
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
  - "api-ms-win-crt-locale-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_setmbcp"
  - "setmbcp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_setmbcp-Funktion"
  - "Mehrbytecodepages"
  - "setmbcp-Funktion"
ms.assetid: cfde53b5-0b73-4684-81b1-a8d3aafc85de
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# _setmbcp
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Legt eine neue Mehrbyte\-Codepage fest.  
  
## Syntax  
  
```  
int _setmbcp(  
   int codepage   
);  
```  
  
#### Parameter  
 `codepage`  
 Neue Codepage\-Einstellung für gebietsschemaunabhängige Mehrbyteroutinen.  
  
## Rückgabewert  
 Gibt 0 zurück, wenn die Codepage erfolgreich festgelegt wird.  Wenn ein ungültiger Codepagewert für `codepage` angegeben wurde, kehrt zurück \- 1 und die Codepage\-Einstellung ist unverändert.  Legt `errno` auf `EINVAL` fest, wenn ein Speicherbelegungsfehler auftritt.  
  
## Hinweise  
 Die `_setmbcp`\-Funktion gibt eine neue Mehrbyte\-Codepage an.  Standardmäßig legt das Laufzeitsystem automatisch die Mehrbyte\-Codepage auf die SystemStandard ANSI\-Codepage fest.  Die Mehrbyte\-Codepage\-Einstellung beeinflusst alle Mehrbyteroutinen, die nicht vom Gebietsschema\) sind.  Es ist jedoch möglich, `_setmbcp` anzuweisen, um die Codepage zu verwenden, die für das aktuelle Gebietsschema definiert wird \(siehe folgende Liste der Manifestkonstanten und zugeordneten Verhaltensergebnissen\).  Eine Liste der Mehrbyteroutinen, die von der Codepage eines Gebietsschemas anstatt die Mehrbyte\-Codepage abhängig sind, finden Sie unter [Interpretation von Mehrbytezeichen\-Sequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md).  
  
 Die Mehrbyte\-Codepage beeinflusst auch das Mehrbytezeichen, das durch die folgenden Laufzeitbibliotheksroutinen verarbeitet:  
  
||||  
|-|-|-|  
|[\_exec\-Funktionen](../../c-runtime-library/exec-wexec-functions.md)|[\_mktemp](../../c-runtime-library/reference/mktemp-wmktemp.md)|[\_stat](../../c-runtime-library/reference/stat-functions.md)|  
|[\_fullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)|[\_spawn\-Funktionen](../../c-runtime-library/spawn-wspawn-functions.md)|[\_tempnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)|  
|[\_makepath](../../c-runtime-library/reference/makepath-wmakepath.md)|[\_splitpath](../../c-runtime-library/reference/splitpath-wsplitpath.md)|[tmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)|  
  
 Außerdem nutzen alle Laufzeitbibliotheksroutinen, die Mehrbytezeichen `argv` oder `envp` Programmargumente erhalten, während Parameter \(wie `_exec` und `_spawn` \) alle Familien diese Zeichenfolgen anhand der Mehrbyte\-Codepage verarbeiten.  Deshalb werden diese Routinen auch durch einen Aufruf von `_setmbcp` auswirkt, der die Mehrbyte\-Codepage ändert.  
  
 Das `codepage`\-Argument kann auf eine der folgenden Werte festgelegt werden:  
  
-   `_MB_CP_ANSI` Verwenden Sie die ANSI\-Codepage, die vom Betriebssystem beim Programmstart abgerufen wird.  
  
-   `_MB_CP_LOCALE` Verwenden Sie die aktuelle Codepage des Gebietsschemas, die von einem vorherigen Aufruf erfolgt [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).  
  
-   `_MB_CP_OEM` Verwenden Sie OEM\-Codepage, die vom Betriebssystem beim Programmstart abgerufen wird.  
  
-   `_MB_CP_SBCS` Verwenden Sie Einzelbytecodepage.  Wenn die Codepage auf `_MB_CP_SBCS` festgelegt wird, gibt eine Routine wie [\_ismbblead](../../c-runtime-library/reference/ismbblead-ismbblead-l.md) immer false zurück.  
  
-   Ein beliebiger anderer gültiger Codepagewert, unabhängig davon, ob der Wert ANSI, OEM\- oder eine andere für lassen\-System\-unterstützte Codepage ist \(außer UTF\-7 und UTF\-8, die nicht unterstützt werden\).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_setmbcp`|\<mbctype.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Siehe auch  
 [\_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)