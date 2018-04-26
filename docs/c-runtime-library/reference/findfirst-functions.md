---
title: _findfirst, _findfirst32, _findfirst32i64, _findfirst64, _findfirst64i32, _findfirsti64, _wfindfirst, _wfindfirst32, _wfindfirst32i64, _wfindfirst64, _wfindfirst64i32, _wfindfirsti64 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _findfirst
- _wfindfirst
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- findfirst32i64
- wfindfirst32i64
- tfindfirst64
- _findfirst64i32
- _wfindfirst32i64
- _wfindfirsti64
- wfindfirst
- _tfindfirsti64
- findfirst32
- _tfindfirst32
- _findfirsti64
- findfirst
- wfindfirst64
- wfindfirst32
- tfindfirst32
- _wfindfirst64i32
- findfirst64i32
- tfindfirst64i32
- _wfindfirst
- findfirsti64
- _findfirst32i64
- wfindfirst64i32
- _wfindfirst32
- _findfirst32
- _tfindfirst32i64
- tfindfirst
- _tfindfirst64i32
- findfirst64
- _tfindfirst
- _findfirst64
- _tfindfirst64
- tfindfirst32i64
- _findfirst
- _wfindfirst64
dev_langs:
- C++
helpviewer_keywords:
- _tfindfirst64 function
- _wfindfirst64i32 function
- _wfindfirst32i64 function
- wfindfirst32 function
- _findfirst function
- wfindfirst64 function
- _wfindfirst function
- _findfirst64i32 function
- wfindfirst function
- _findfirst64 function
- tfindfirst32 function
- _tfindfirst64i32 function
- findfirst function
- findfirst32i64 function
- tfindfirst64 function
- _tfindfirst32 function
- tfindfirst32i64 function
- tfindfirst64i32 function
- _wfindfirsti64 function
- _findfirst32i64 function
- findfirst32 function
- findfirsti64 function
- findfirst64i32 function
- tfindfirsti64 function
- tfindfirst function
- _wfindfirst32 function
- wfindfirsti64 function
- _tfindfirsti64 function
- _tfindfirst function
- _tfindfirst32i64 function
- findfirst64 function
- _findfirst32 function
- _findfirsti64 function
- wfindfirst32i64 function
- wfindfirst64i32 function
- _wfindfirst64 function
ms.assetid: 9bb46d1a-b946-47de-845a-a0b109a33ead
caps.latest.revision: 25
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ff0827420392744d0cc362b02f87ad093b7ce950
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="findfirst-findfirst32-findfirst32i64-findfirst64-findfirst64i32-findfirsti64-wfindfirst-wfindfirst32-wfindfirst32i64-wfindfirst64-wfindfirst64i32-wfindfirsti64"></a>_findfirst, _findfirst32, _findfirst32i64, _findfirst64, _findfirst64i32, _findfirsti64, _wfindfirst, _wfindfirst32, _wfindfirst32i64, _wfindfirst64, _wfindfirst64i32, _wfindfirsti64

Enthalten Informationen über die erste Instanz eines Dateinamens, die die angegebene Datei entspricht dem *Filespec* Argument.

## <a name="syntax"></a>Syntax

```C
intptr_t _findfirst(
   const char *filespec,
   struct _finddata_t *fileinfo
);
intptr_t _findfirst32(
   const char *filespec,
   struct _finddata32_t *fileinfo
);
intptr_t _findfirst64(
   const char *filespec,
   struct _finddata64_t *fileinfo
);
intptr_t _findfirsti64(
   const char *filespec,
   struct _finddatai64_t *fileinfo
);
intptr_t _findfirst32i64(
   const char *filespec,
   struct _finddata32i64_t *fileinfo
);
intptr_t _findfirst64i32(
   const char *filespec,
   struct _finddata64i32_t *fileinfo
);
intptr_t _wfindfirst(
   const wchar_t *filespec,
   struct _wfinddata_t *fileinfo
);
intptr_t _wfindfirst32(
   const wchar_t *filespec,
   struct _wfinddata32_t *fileinfo
);
intptr_t _wfindfirst64(
   const wchar_t *filespec,
   struct _wfinddata64_t *fileinfo
);
intptr_t _wfindfirsti64(
   const wchar_t *filespec,
   struct _wfinddatai64_t *fileinfo
);
intptr_t _wfindfirst32i64(
   const wchar_t *filespec,
   struct _wfinddata32i64_t *fileinfo
);
intptr_t _wfindfirst64i32(
   const wchar_t *filespec,
   struct _wfinddata64i32_t *fileinfo
);
```

### <a name="parameters"></a>Parameter

*filespec*<br/>
Ziel-Dateispezifikation (kann Platzhalterzeichen enthalten)

*"FileInfo"*<br/>
Puffer für Dateiinformationen.

## <a name="return-value"></a>Rückgabewert

Im Erfolgsfall **_findfirst** gibt eine eindeutige Suchhandle identifizieren die Datei oder eine Gruppe von Dateien, entsprechen die *Filespec* -Spezifikation, die in einem nachfolgenden Aufruf verwendet werden können [_ FindNext](findnext-functions.md) oder [_findclose](findclose.md). Andernfalls **_findfirst** gibt-1 zurück und legt **Errno** auf einen der folgenden Werte.

|errno-Wert|Bedingung|
|-|-|
**EINVAL**|Ungültiger Parameter: *Filespec* oder *"FileInfo"* wurde **NULL**. oder das Betriebssystem hat einen unerwarteten Fehler zurückgegeben.
**ENOENT**|Die Dateispezifikation, die nicht zugeordnet werden konnte
**ENOMEM**|Nicht genügend Arbeitsspeicher.
**EINVAL**|Ungültige Dateinamen oder den angegebenen Dateinamen war größer als **MAX_PATH**.

Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Wenn ein ungültiger Parameter übergeben wird, rufen diese Funktionen den Handler für ungültige Parameter auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben wird.

## <a name="remarks"></a>Hinweise

Rufen Sie [_findclose](findclose.md) nach Beendigung des Vorgangs entweder mit der **_findfirst** oder [_findnext](findnext-functions.md) -Funktion (oder alle Varianten). Auf diese Weise werden Ressourcen frei, die von diesen Funktionen in Ihrer Anwendung verwendet werden.

Die Varianten dieser Funktionen mit dem **w** Präfix sind Breitzeichenversionen; andernfalls, sie sind identisch mit den entsprechenden Einzelbyte-Funktionen.

Varianten dieser Funktionen unterstützen 32-Bit- oder 64-Bit-Zeittypen und 32-Bit- oder 64-Bit-Dateigrößen. Das erste numerische Suffix (**32** oder **64**) gibt die Größe des Typs Zeit; das zweite Suffix ist entweder **i32** oder **i64**, und gibt an, Gibt an, ob die Dateigröße als ganze 32-Bit oder 64-Bit-Zahl dargestellt wird. Informationen darüber, welche Versionen 32-Bit- und 64-Bit-Zeittypen und -Dateigrößen unterstützen, finden Sie in der folgenden Tabelle. Die **i32** oder **i64** Suffix wird weggelassen, ist er identisch mit der Größe des Typs Zeit daher **_findfirst64** unterstützt auch die 64-Bit-Dateilängen und **_findfirst32**  unterstützt nur 32-Bit-Dateilängen.

Diese Funktionen verwenden verschiedene Formen des der **_finddata_t** Struktur für die *"FileInfo"* Parameter. Weitere Informationen zur Struktur finden Sie unter [Dateinamen-Suchfunktionen](../../c-runtime-library/filename-search-functions.md).

In Varianten, die einen 64-Bit-Zeittyp verwenden, kann das Erstellungsdatum der Datei bis 23:59:59 am 31. Dezember 3000 (UTC) ausgedrückt werden. Diejenigen, die 32-Bit-Zeittypen verwenden, stellen Datumsangaben nur bis 23:59:59 am 18. Januar 2038 (UTC) dar. Der 1. Januar 1970 (Mitternacht) ist der älteste mögliche Datumsbereich für all diese Funktionen.

Es sei denn, Sie einen bestimmten Grund haben verwenden Sie die Versionen, die die Größe zur explizit anzugeben, verwenden Sie **_findfirst** oder **_wfindfirst** oder, wenn Sie größer als 3 GB Dateigrößen unterstützen müssen, verwenden Sie **_ findfirsti64** oder **_wfindfirsti64**. All diese Funktionen verwenden den 64-Bit-Zeittyp. In früheren Versionen verwendeten diese Funktionen einen 32-Bit-Zeittyp. Wenn dies eine wichtige Änderung für eine Anwendung ist, können Sie definieren **_USE_32BIT_TIME_T** um zum alten Verhalten zurückzukehren. Wenn **_USE_32BIT_TIME_T** definiert ist, **_findfirst**, **_finfirsti64**, und die entsprechenden Unicode-Versionen verwenden Sie eine 32-Bit-Zeit.

### <a name="time-type-and-file-length-type-variations-of-findfirst"></a>_findfirst-Varianten des Zeittyps und Dateigrößentyps

|Funktionen|**_USE_32BIT_TIME_T** definiert?|Uhrzeittyp|Dateilängentyp|
|---------------|----------------------------------|---------------|----------------------|
|**_findfirst**, **_wfindfirst**|Nicht definiert|64-Bit|32-Bit|
|**_findfirst**, **_wfindfirst**|Definiert|32-Bit|32-Bit|
|**_findfirst32**, **_wfindfirst32**|Nicht von der Makrodefinition betroffen|32-Bit|32-Bit|
|**_findfirst64**, **_wfindfirst64**|Nicht von der Makrodefinition betroffen|64-Bit|64-Bit|
|**_findfirsti64**, **_wfindfirsti64**|Nicht definiert|64-Bit|64-Bit|
|**_findfirsti64**, **_wfindfirsti64**|Definiert|32-Bit|64-Bit|
|**_findfirst32i64**, **_wfindfirst32i64**|Nicht von der Makrodefinition betroffen|32-Bit|64-Bit|
|**_findfirst64i32**, **_wfindfirst64i32**|Nicht von der Makrodefinition betroffen|64-Bit|32-Bit|

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tfindfirst**|**_findfirst**|**_findfirst**|**_wfindfirst**|
|**_tfindfirst32**|**_findfirst32**|**_findfirst32**|**_wfindfirst32**|
|**_tfindfirst64**|**_findfirst64**|**_findfirst64**|**_wfindfirst64**|
|**_tfindfirsti64**|**_findfirsti64**|**_findfirsti64**|**_wfindfirsti64**|
|**_tfindfirst32i64**|**_findfirst32i64**|**_findfirst32i64**|**_wfindfirst32i64**|
|**_tfindfirst64i32**|**_findfirst64i32**|**_findfirst64i32**|**_wfindfirst64i32**|

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|
|--------------|---------------------|
|**_findfirst**|\<io.h>|
|**_findfirst32**|\<io.h>|
|**_findfirst64**|\<io.h>|
|**_findfirsti64**|\<io.h>|
|**_findfirst32i64**|\<io.h>|
|**_findfirst64i32**|\<io.h>|
|**_wfindfirst**|\<io.h> oder \<wchar.h>|
|**_wfindfirst32**|\<io.h> oder \<wchar.h>|
|**_wfindfirst64**|\<io.h> oder \<wchar.h>|
|**_wfindfirsti64**|\<io.h> oder \<wchar.h>|
|**_wfindfirst32i64**|\<io.h> oder \<wchar.h>|
|**_wfindfirst64i32**|\<io.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Systemaufrufe](../../c-runtime-library/system-calls.md)<br/>
[Dateinamen-Suchfunktionen](../../c-runtime-library/filename-search-functions.md)<br/>
