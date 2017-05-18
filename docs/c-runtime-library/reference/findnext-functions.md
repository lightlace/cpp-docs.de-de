---
title: _findnext, _findnext32, _findnext32i64, _findnext64, _findnext64i32, _findnexti64, _wfindnext, _wfindnext32, _wfindnext32i64, _wfindnext64, _wfindnext64i32, _wfindnexti64 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wfindnext
- _findnext
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
- findnext
- _wfindnext32i64
- _tfindnext64i32
- findnext32
- findnext32i64
- wfindnext64i32
- _wfindnext
- tfindnext64
- findnexti64
- _findnexti64
- _tfindnexti64
- _findnext64i32
- tfindnexti64
- tfindnext32
- _wfindnext64i32
- findnext64i32
- _findnext
- _tfindnext32i64
- _wfindnext64
- wfindnext
- wfindnext32
- tfindnext32i64
- _findnext64
- _tfindnext64
- _wfindnext32
- findnext64
- _findnext32i64
- tfindnext
- wfindnexti64
- tfindnext64i32
- _tfindnext32
- wfindnext32i64
- wfindnext64
- _wfindnexti64
- _tfindnext
- _findnext32
dev_langs:
- C++
helpviewer_keywords:
- _wfindnexti64 function
- _tfindnext32 function
- wfindnexti64 function
- _wfindnext32i64 function
- findnext32i64 function
- tfindnext64i32 function
- _tfindnext64i32 function
- _findnext function
- findnext64i32 function
- _tfindnext function
- findnext32 function
- tfindnext32 function
- _findnext32 function
- _tfindnext32i64 function
- _wfindnext function
- tfindnext function
- _findnext64 function
- findnext64 function
- _findnext64i32 function
- wfindnext32i64 function
- findnext function
- wfindnext32 function
- _wfindnext64i32 function
- findnexti64 function
- _wfindnext64 function
- _findnext32i64 function
- _findnexti64 function
- _tfindnext64 function
- wfindnext64i32 function
- tfindnexti64 function
- wfindnext64 function
- wfindnext function
- tfindnext64 function
- _wfindnext32 function
- tfindnext32i64 function
- _tfindnexti64 function
ms.assetid: 75d97188-5add-4698-a46c-4c492378f0f8
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 58132a9c16f23d7885432b05a459cc348c0bf915
ms.contentlocale: de-de
ms.lasthandoff: 04/01/2017

---
# <a name="findnext-findnext32-findnext32i64-findnext64-findnext64i32-findnexti64-wfindnext-wfindnext32-wfindnext32i64-wfindnext64-wfindnext64i32-wfindnexti64"></a>_findnext, _findnext32, _findnext32i64, _findnext64, _findnext64i32, _findnexti64, _wfindnext, _wfindnext32, _wfindnext32i64, _wfindnext64, _wfindnext64i32, _wfindnexti64
Suchen Sie den nächsten Namen, sofern vorhanden, der dem Argument `filespec` in einem vorherigen Aufruf von [_findfirst](../../c-runtime-library/reference/findfirst-functions.md) entspricht, und ändern Sie dann die Inhalte der `fileinfo`-Struktur entsprechend.  
  
## <a name="syntax"></a>Syntax  
  
```  
int _findnext(  
   intptr_t handle,  
   struct _finddata_t *fileinfo   
);  
int _findnext32(  
   intptr_t handle,  
   struct _finddata32_t *fileinfo   
);  
int _findnext64(  
   intptr_t handle,  
   struct __finddata64_t *fileinfo   
);  
int _findnexti64(  
   intptr_t handle,  
   struct __finddatai64_t *fileinfo   
);  
int _findnext32i64(  
   intptr_t handle,  
   struct _finddata32i64_t *fileinfo   
);  
int _findnext64i32(  
   intptr_t handle,  
   struct _finddata64i32_t *fileinfo   
);  
int _wfindnext(  
   intptr_t handle,  
   struct _wfinddata_t *fileinfo   
);  
int _wfindnext32(  
   intptr_t handle,  
   struct _wfinddata32_t *fileinfo   
);  
int _wfindnext64(  
   intptr_t handle,  
   struct _wfinddata64_t *fileinfo   
);  
int _wfindnexti64(  
   intptr_t handle,  
   struct _wfinddatai64_t *fileinfo   
);  
int _wfindnext32i64(  
   intptr_t handle,  
   struct _wfinddatai64_t *fileinfo   
);  
int _wfindnext64i32(  
   intptr_t handle,  
   struct _wfinddata64i32_t *fileinfo   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `handle`  
 Das Suchhandle, das von einem vorherigen Aufruf von `_findfirst` zurückgegeben wird.  
  
 `fileinfo`  
 Puffer für Dateiinformationen.  
  
## <a name="return-value"></a>Rückgabewert  
 Im Erfolgsfall wird 0 zurückgegeben. Andernfalls gibt-1 zurück und legt `errno` auf einen Wert, der die Art des Fehlers angibt. Mögliche Fehlercodes werden in der folgenden Tabelle dargestellt.  
  
 `EINVAL`  
 Ungültiger Parameter: `fileinfo` entsprach `NULL`, oder das Betriebssystem hat einen unerwarteten Fehler zurückgegeben.  
  
 `ENOENT`  
 Es konnten keine übereinstimmenden Dateien gefunden werden.  
  
 `ENOMEM`  
 Nicht genügend Arbeitsspeicher oder der Dateiname ist größer als `MAX_PATH`.  
  
 Wenn ein ungültiger Parameter übergeben wird, rufen diese Funktionen den Handler für ungültige Parameter auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben wird.  
  
## <a name="remarks"></a>Hinweise  
 Sie müssen [_findclose](../../c-runtime-library/reference/findclose.md) aufrufen, nachdem Sie den Vorgang entweder mit der Funktion `_findfirst` oder der Funktion `_findnext` (oder eine beliebige Variante) beendet haben. Auf diese Weise werden Ressourcen frei, die von diesen Funktionen in Ihrer Anwendung verwendet werden.  
  
 Die Varianten dieser Funktionen, die das Präfix `w` aufweisen, sind Breitzeichenversionen. Andernfalls sind sie identisch mit den entsprechenden Einzelbytefunktionen.  
  
 Varianten dieser Funktionen unterstützen 32-Bit- oder 64-Bit-Zeittypen und 32-Bit- oder 64-Bit-Dateigrößen. Das erste numerische Suffix (`32` oder `64`) gibt die Größe des verwendeten Zeittyps an; das zweite Suffix ist entweder `i32` oder `i64`und gibt an, ob die Dateigröße als ganze Zahl mit 32 Bit oder 64 Bit dargestellt ist. Informationen darüber, welche Versionen 32-Bit- und 64-Bit-Zeittypen und -Dateigrößen unterstützen, finden Sie in der folgenden Tabelle. In Varianten, die einen 64-Bit-Zeittyp verwenden, kann das Erstellungsdatum der Datei bis 23:59:59 am 31. Dezember 3000 (UTC) ausgedrückt werden. Die Varianten, die 32-Bit-Zeittypen verwenden, stellen Datumsangaben nur bis 23:59:59 am 18. Januar 2038 (UTC) dar. Der 1. Januar 1970 (Mitternacht) ist der älteste mögliche Datumsbereich für beide Funktionen.  
  
 Verwenden Sie `_findnext` oder `_wfindnext`, oder `_findnexti64` oder `_wfindnexti64`, wenn Sie Dateigrößen von mehr als 3 GB unterstützen müssen, es sei denn, Sie haben einen bestimmten Grund für die Verwendung der Versionen, die die Zeitgröße explizit angeben. All diese Funktionen verwenden den 64-Bit-Zeittyp. In früheren Versionen verwendeten diese Funktionen einen 32-Bit-Zeittyp. Ist dies eine tiefgreifende Änderung für eine Anwendung, Sie definieren `_USE_32BIT_TIME_T`, um das alte Verhalten wiederherzustellen. Wenn `_USE_32BIT_TIME_T` definiert ist, verwenden `_findnext` und `_finnexti64` und die entsprechenden Unicode-Versionen verwenden einen 32-Bit-Zeittyp.  
  
### <a name="time-type-and-file-length-type-variations-of-findnext"></a>_findnext-Varianten des Uhrzeittyps und Dateilängentyps  
  
|Funktionen|Ist `_USE_32BIT_TIME_T` definiert?|Uhrzeittyp|Dateilängentyp|  
|---------------|----------------------------------|---------------|----------------------|  
|`_findnext`, `_wfindnext`|Nicht definiert|64-Bit|32-Bit|  
|`_findnext`, `_wfindnext`|Definiert|32-Bit|32-Bit|  
|`_findnext32`, `_wfindnext32`|Nicht von der Makrodefinition betroffen|32-Bit|32-Bit|  
|`_findnext64`, `_wfindnext64`|Nicht von der Makrodefinition betroffen|64-Bit|64-Bit|  
|`_findnexti64`, `_wfindnexti64`|Nicht definiert|64-Bit|64-Bit|  
|`_findnexti64`, `_wfindnexti64`|Definiert|32-Bit|64-Bit|  
|`_findnext32i64`, `_wfindnext32i64`|Nicht von der Makrodefinition betroffen|32-Bit|64-Bit|  
|`_findnext64i32`, `_wfindnext64i32`|Nicht von der Makrodefinition betroffen|64-Bit|32-Bit|  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tfindnext`|`_findnext`|`_findnext`|`_wfindnext`|  
|`_tfindnext32`|`_findnext32`|`_findnext32`|`_wfindnext32`|  
|`_tfindnext64`|`_findnext64`|`_findnext64`|`_wfindnext64`|  
|`_tfindnexti64`|`_findnexti64`|`_findnexti64`|`_wfindnexti64`|  
|`_tfindnext32i64`|`_findnext32i64`|`_findnext32i64`|`_wfindnext32i64`|  
|`_tfindnext64i32`|`_findnext64i32`|`_findnext64i32`|`_wfindnext64i32`|  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------|  
|`_findnext`|\<io.h>|  
|`_findnext32`|\<io.h>|  
|`_findnext64`|\<io.h>|  
|`_findnexti64`|\<io.h>|  
|`_findnext32i64`|\<io.h>|  
|`_findnext64i32`|\<io.h>|  
|`_wfindnext`|\<io.h> oder \<wchar.h>|  
|`_wfindnext32`|\<io.h> oder \<wchar.h>|  
|`_wfindnext64`|\<io.h> oder \<wchar.h>|  
|`_wfindnexti64`|\<io.h> oder \<wchar.h>|  
|`_wfindnext32i64`|\<io.h> oder \<wchar.h>|  
|`_wfindnext64i32`|\<io.h> oder \<wchar.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="libraries"></a>Bibliotheken  
 Alle Versionen der [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Systemaufrufe](../../c-runtime-library/system-calls.md)   
 [Dateinamen-Suchfunktionen](../../c-runtime-library/filename-search-functions.md)
