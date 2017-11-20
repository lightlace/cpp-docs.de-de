---
title: _setmbcp | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _setmbcp
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-locale-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _setmbcp
- setmbcp
dev_langs: C++
helpviewer_keywords:
- setmbcp function
- _setmbcp function
- multibyte code pages
ms.assetid: cfde53b5-0b73-4684-81b1-a8d3aafc85de
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1421ff3ab9478577c2f45248d4568b99a8bf2bad
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="setmbcp"></a>_setmbcp
Legt eine neue Multibyte-Codepage fest.  
  
## <a name="syntax"></a>Syntax  
  
```  
int _setmbcp(  
   int codepage   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `codepage`  
 Neue Codepageeinstellung für gebietsschemaunabhängige Multibyte-Routinen.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt 0 zurück, wenn die Codepage erfolgreich festgelegt wurde. Wenn ein ungültiger Codepagewert für angegeben wird `codepage`,-1 und die Codepage-Einstellung wird unverändert zurückgegeben. Legt `errno` auf `EINVAL` fest, wenn ein Fehler beim Reservieren von Speicher auftritt.  
  
## <a name="remarks"></a>Hinweise  
 Die `_setmbcp`-Funktion legt eine neue Multibyte-Codepage fest. Standardmäßig legt das Laufzeitsystem automatisch die Multibyte-Codepage auf die Systemstandard-ANSI-Codepage fest. Die Multibyte-Codepageeinstellung wirkt sich auf alle Multibyteroutinen auf, die nicht vom Gebietsschema abhängig sind. Es ist jedoch möglich, `_setmbcp` anzuweisen, die für das aktuelle Gebietsschema definierte Codepage zu verwenden (Manifestkonstanten und zugeordnete Verhaltensergebnisse finden Sie in der folgenden Liste). Eine Liste der Multibyteroutinen, die von der Gebietsschema-Codepage und nicht von der Multibyte-Codepage abhängig sind, finden Sie unter [Interpretation von Multybite-Zeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md).  
  
 Die Multibyte-Codepage hat auch Auswirkungen auf die Multibyteverarbeitung durch die folgenden Routinen der Laufzeitbibliothek:  
  
||||  
|-|-|-|  
|[_exec-Funktionen](../../c-runtime-library/exec-wexec-functions.md)|[_mktemp](../../c-runtime-library/reference/mktemp-wmktemp.md)|[_stat](../../c-runtime-library/reference/stat-functions.md)|  
|[_fullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)|[_spawn-Funktionen](../../c-runtime-library/spawn-wspawn-functions.md)|[_tempnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)|  
|[_makepath](../../c-runtime-library/reference/makepath-wmakepath.md)|[_splitpath](../../c-runtime-library/reference/splitpath-wsplitpath.md)|[tmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)|  
  
 Darüber hinaus verarbeiten alle Laufzeitbibliotheksroutinen, die Multibyte-Zeichensatz-Programmargumente `argv` oder `envp` als Parameter (z.B. die Familien `_exec` und `_spawn`) erhalten, diese Zeichenfolgen gemäß der Mehrbyte-Codepage. Diese Routinen sind daher ebenfalls durch einen Aufruf von `_setmbcp` betroffen, der die Multibyte-Codepage ändert.  
  
 Das `codepage`-Argument kann auf einen der folgenden Werte festgelegt werden:  
  
-   `_MB_CP_ANSI` Verwenden Sie die vom Betriebssystem beim Programmstart abgerufene ANSI-Codepage.  
  
-   `_MB_CP_LOCALE`Verwenden Sie die Codepage des aktuellen Gebietsschemas, das von einem vorherigen Aufruf von [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md) abgerufen wurde.  
  
-   `_MB_CP_OEM` Verwenden Sie die vom Betriebssystem beim Programmstart abgerufene OEM-Codepage.  
  
-   `_MB_CP_SBCS` Verwenden Sie eine Einzelbyte-Codepage. Wenn die Codepage auf `_MB_CP_SBCS` festgelegt ist, gibt eine Routine, wie z.B. [_ismbblead](../../c-runtime-library/reference/ismbblead-ismbblead-l.md), stets FALSE zurück.  
  
-   Jeder beliebige andere gültige Codepage-Wert unabhängig davon, ob der Wert eine ANSI-, OEM- oder einem anderen Betriebssystem unterstützte Codepage ist (außer UTF-7 und UTF-8, die nicht unterstützt werden).  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_setmbcp`|\<mbctype.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="see-also"></a>Siehe auch  
 [_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)