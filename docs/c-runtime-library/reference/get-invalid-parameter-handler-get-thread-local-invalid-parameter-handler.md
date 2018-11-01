---
title: _get_invalid_parameter_handler, _get_thread_local_invalid_parameter_handler
ms.date: 11/04/2016
apiname:
- _get_invalid_parameter_handler
- _get_thread_local_invalid_parameter_handler
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _get_invalid_parameter_handler
- stdlib/_get_invalid_parameter_handler
- _get_thread_local_invalid_parameter_handler
- stdlib/_get_thread_local_invalid_parameter_handler
helpviewer_keywords:
- _get_thread_local_invalid_parameter_handler function
- _get_invalid_parameter_handler function
ms.assetid: a176da0e-38ca-4d99-92bb-b0e2b8072f53
ms.openlocfilehash: 7d1a87f9ade0845994918d5a4d59dc56e190d2b6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50623976"
---
# <a name="getinvalidparameterhandler-getthreadlocalinvalidparameterhandler"></a>_get_invalid_parameter_handler, _get_thread_local_invalid_parameter_handler

Ruft die Funktion auf, die aufzurufen ist, wenn CRT ein ungültiges Argument erkennt.

## <a name="syntax"></a>Syntax

```C
_invalid_parameter_handler _get_invalid_parameter_handler(void);
_invalid_parameter_handler _get_thread_local_invalid_parameter_handler(void);
```

## <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die derzeit festgelegte Funktion für ungültige Parameterhandler oder ein NULL-Zeiger, wenn keine festgelegt wurde.

## <a name="remarks"></a>Hinweise

Die **_get_invalid_parameter_handler** Funktion ruft den derzeit festgelegten globalen ungültigen parameterhandler auf. Sie gibt einen NULL-Zeiger zurück, wenn kein globaler Handler für ungültige Parameter festgelegt wurde. Auf ähnliche Weise die **_get_thread_local_invalid_parameter_handler** Ruft den aktuelle Thread-lokalen ungültige parameterhandler des Threads, die es für aufgerufen wird, oder ein null-Zeiger, wenn kein Handler festgelegt wurde. Informationen zum Festlegen von globalen und Thread-lokalen ungültigen Parameterhandlern finden Sie unter [_set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md).

Der zurückgegebene Funktionszeiger des ungültigen Parameterhandlers hat den folgenden Typ:

```C
typedef void (__cdecl* _invalid_parameter_handler)(
    wchar_t const*,
    wchar_t const*,
    wchar_t const*,
    unsigned int,
    uintptr_t
    );
```

Mehr Informationen über ungültige Parameterhandler finden sie unter dem Prototyp in [set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_get_invalid_parameter_handler**, **_get_thread_local_invalid_parameter_handler**|C: \<stdlib.h><br /><br /> C++: \<cstdlib> oder \<stdlib.h>|

Die **_get_invalid_parameter_handler** und **_get_thread_local_invalid_parameter_handler** Funktionen sind Microsoft-spezifisch. Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[_set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)<br/>
[CRT-Funktionsversionen mit erweiterter Sicherheit](../../c-runtime-library/security-enhanced-versions-of-crt-functions.md)<br/>
