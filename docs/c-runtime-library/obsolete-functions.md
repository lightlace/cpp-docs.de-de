---
title: Veraltete Funktionen
ms.date: 11/04/2016
f1_keywords:
- is_wctype
- _loaddll
- _unloaddll
- _getdllprocaddr
- _seterrormode
- _beep
- _sleep
- _getsystime
- corecrt_wctype/is_wctype
- process/_loaddll
- process/_unloaddll
- process/_getdllprocaddr
- stdlib/_seterrormode
- stdlib/_beep
- stdlib/_sleep
- time/_getsystime
- time/_setsystime
helpviewer_keywords:
- obsolete functions
- _beep function
- _sleep function
- _seterrormode function
ms.assetid: 8e14c2d4-1481-4240-8586-47eb43db02b0
ms.openlocfilehash: 76c7a710b577d0fef4fe2a74dbee2a722c7f98b4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50677421"
---
# <a name="obsolete-functions"></a>Veraltete Funktionen

Bestimmte Bibliotheksfunktionen sind veraltet, und es stehen äquivalente neuere Funktionen zur Verfügung. Wir empfehlen, die aktualisierten Versionen zu verwenden. Andere veraltete Versionen wurden aus der CRT entfernt. In diesem Thema werden die als veraltet eingestuften und die in einer bestimmten Version von Visual Studio entfernten Funktionen aufgelistet.

## <a name="deprecated-as-obsolete-in-visual-studio-2015"></a>In Visual Studio 2015 als veraltet eingestuft

|Veraltete Funktion|Alternative|
|-----------------------|-----------------|
|`is_wctype`|[iswctype](../c-runtime-library/reference/isctype-iswctype-isctype-l-iswctype-l.md)|
|`_loaddll`|[LoadLibrary](/windows/desktop/api/libloaderapi/nf-libloaderapi-loadlibrarya), [LoadLibraryEx](/windows/desktop/api/libloaderapi/nf-libloaderapi-loadlibraryexa)oder [LoadPackagedLibrary](/windows/desktop/api/winbase/nf-winbase-loadpackagedlibrary)|
|`_unloaddll`|[FreeLibrary](/windows/desktop/api/libloaderapi/nf-libloaderapi-freelibrary)|
|`_getdllprocaddr`|[GetProcAddress](../build/getprocaddress.md)|
|`_seterrormode`|[SetErrorMode](https://msdn.microsoft.com/library/windows/desktop/ms680621)|
|`_beep`|[Beep](https://msdn.microsoft.com/library/windows/desktop/ms679277)|
|`_sleep`|[Sleep](/windows/desktop/api/synchapi/nf-synchapi-sleep)|
|`_getsystime`|[GetLocalTime](/windows/desktop/api/sysinfoapi/nf-sysinfoapi-getlocaltime)|
|`_setsystime`|[GetLocalTime](/windows/desktop/api/sysinfoapi/nf-sysinfoapi-setlocaltime)|

## <a name="removed-from-the-crt-in-visual-studio-2015"></a>Aus der CRT in Visual Studio 2015 entfernt

|Veraltete Funktion|Alternative|
|-----------------------|-----------------|
|[_cgets, _cgetws](../c-runtime-library/cgets-cgetws.md)|[_cgets_s, _cgetws_s](../c-runtime-library/reference/cgets-s-cgetws-s.md)|
|[gets, _getws](../c-runtime-library/gets-getws.md)|[gets_s, _getws_s](../c-runtime-library/reference/gets-s-getws-s.md)|
|[_get_output_format](../c-runtime-library/get-output-format.md)|Keiner|
|[_heapadd](../c-runtime-library/heapadd.md)|Keiner|
|[_heapset](../c-runtime-library/heapset.md)|Keiner|
|[inp, inpw](../c-runtime-library/inp-inpw.md)|Keiner|
|[_inp, _inpw, _inpd](../c-runtime-library/inp-inpw-inpd.md)|Keiner|
|[outp, outpw](../c-runtime-library/outp-outpw.md)|Keiner|
|[_outp, _outpw, _outpd](../c-runtime-library/outp-outpw-outpd.md)|Keiner|
|[_set_output_format](../c-runtime-library/set-output-format.md)|Keiner|

## <a name="removed-from-the-crt-in-earlier-versions-of-visual-studio"></a>Aus der CRT in früheren Versionen von Visual Studio entfernt

[_lock](../c-runtime-library/lock.md)

[_unlock](../c-runtime-library/unlock.md)